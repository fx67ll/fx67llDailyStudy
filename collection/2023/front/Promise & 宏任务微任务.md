# Promise & 宏任务微任务  
`js-event-loop-promise`

## 面试问题
> 什么是 *js事件循环*（`Event Loop`）？  
> 什么是 *宏任务* 和 *微任务*？ 
> *宏任务* 和 *微任务* 有什么区别？  
> 为什么 `Promise` 比 `setTimeout` 快？  
> 如何模拟手写一个简易的 `Promise` 方法?  
> Vue中如何销毁定时器？React中如何销毁定时器？为什么要销毁定时器？  
> 待补充...  


### 总结一下
1. JS 是单线程的，也就是同一个时刻只能做一件事情，那么思考：为什么浏览器可以同时执行异步任务呢？
	+ 因为浏览器是多线程的，当 JS 需要执行异步任务时，浏览器会另外启动一个线程去执行该任务  
2. 浏览器异步任务的执行原理背后其实是一套事件驱动的机制，事件触发、任务选择和任务执行都是由事件驱动机制来完成的  
3. 浏览器中的时间循环  
	+ JS 在解析一段代码时，会将同步代码按顺序排在某个地方，即执行栈，然后依次执行里面的函数。
	+ 当遇到异步任务时就交给其他线程处理，待当前执行栈所有同步代码执行完成后，会从一个队列中去取出已完成的异步任务的回调加入执行栈继续执行，
	+ 遇到异步任务时又交给其他线程，.....，如此循环往复。而其他异步任务完成后，将回调放入任务队列中待执行栈来取出执行。
4. 宏任务和微任务  
	+ 事件循环的过程中，执行栈在同步代码执行完成后，优先检查微任务队列是否有任务需要执行，如果没有，再去宏任务队列检查是否有任务执行，如此往复。
	+ 微任务一般在当前循环就会优先执行，而宏任务会等到下一次循环，因此，微任务一般比宏任务先执行，并且微任务队列只有一个，宏任务队列可能有多个。
	+ 我们常见的点击和键盘等事件属于宏任务。  
5. 常见宏任务  
	+ 用于设置定时器，在指定的时间间隔后执行任务  
	+ `setTimeout()`  
	+ `setInterval()`  
	+ `setImmediate()`  
	+ IO操作：例如文件读写、网络请求等  
	+ UI渲染：浏览器需要重新渲染页面时触发的任务 
	+ `requestAnimationFrame`
6. 常见微任务  
	+ Promise回调：当Promise状态改变时，会执行相应的回调函数  
	+ `promise.then()`/`promise.catch()`  
	+ 使用async函数和await关键字进行异步操作时，await后面的代码会作为微任务执行  
	+ `async`/`await`
	+ 用于观察DOM树的变化，当DOM发生变化时触发微任务  
	+ `new MutaionObserver()`  
	+ `process.nextTick()`  
7. 微任务和宏任务的本质区别  
	+ 宏任务特征：有明确的异步任务需要执行和回调；需要其他异步线程支持。  
	+ 微任务特征：没有明确的异步任务需要执行，只有回调；不需要其他异步线程支持。  
	+ 存放位置：宏任务中的事件放在`callback queue`中，由事件触发线程维护；微任务的事件放在微任务队列中，由js引擎线程维护  
8. 定时器误差  
	+ 事件循环中，总是先执行同步代码后，才会去任务队列中取出异步回调来执行。
	+ 同步代码耗时越长，计时器的误差就越大。  
9. `Promise.all` 和 `Promise.race` 的区别 
	> `Promise.all` 可以将多个实例组装个成一个新实例，成功的时候返回一个成功的数组；失败的时候则返回最先被reject失败状态的值。
	> `Promise.all` 中的子任务是并发执行的，适用于前后没有依赖关系的。
	> 适用场景：比如当一个页面需要在很多个模块的数据都返回回来时才正常显示，否则loading。
	> `Promise.race` 意为赛跑的意思，也就是数组中的任务哪个获取的块，就返回哪个，不管结果本身是成功还是失败。
	> 适用场景： 一般用于和定时器绑定，比如将一个请求和三秒的定时器包装成Promise实例，加入到Promise队列中，请求三秒中还没有回应时，给用户一些提示或相应的操作。


#### 参考资料
1. [JS 事件循环（Event Loop）](https://segmentfault.com/a/1190000043365558)  
2. [面试官：为什么 Promise 比setTimeout() 快？](https://segmentfault.com/a/1190000043362955)  


## 如何自己模拟一个`Promise`方法？ 如何编写一个简易的`Promise`方法？（*曾经面试非常尴尬没有回答出来*）  
```
function SimplePromise(executor) {
  let onResolve, onReject;
  let fulfilled = false;
  let rejected = false;
  let called = false; // 防止resolve和reject被多次调用
  let value;
  let reason;

  // resolve函数
  function resolve(val) {
    if (!called) {
      value = val;
      fulfilled = true;
      called = true;
      if (onResolve) {
        onResolve(val);
      }
    }
  }

  // reject函数
  function reject(err) {
    if (!called) {
      reason = err;
      rejected = true;
      called = true;
      if (onReject) {
        onReject(err);
      }
    }
  }

  // then方法
  this.then = function(callback) {
    onResolve = callback;
    if (fulfilled) {
      onResolve(value);
    }
    return this; // 支持链式调用
  };

  // catch方法
  this.catch = function(callback) {
    onReject = callback;
    if (rejected) {
      onReject(reason);
    }
    return this; // 支持链式调用
  };

  // 立即执行传入的executor函数
  try {
    executor(resolve, reject);
  } catch (error) {
    reject(error);
  }
}

// 使用示例
let promise = new SimplePromise((resolve, reject) => {
  setTimeout(() => {
    resolve("Success!");
    // reject("Error!"); // 也可以测试reject情况
  }, 1000);
});

promise.then(result => {
  console.log(result); // 输出 "Success!"
}).catch(error => {
  console.log(error);
});
```


## js中为什么要销毁定时器？Vue中如何销毁定时器？React中如何销毁定时器？
在JavaScript中，销毁定时器是一个重要的操作，主要是为了避免不必要的资源占用和潜在的内存泄漏。定时器如果不被适当销毁，可能会导致一些问题，如：
1. **继续执行不必要的操作**：如果定时器触发的函数不再需要执行，定时器仍然活跃会导致额外的计算，这可能影响程序性能。
2. **内存泄漏**：在某些情况下，定时器的回调函数可能引用了外部变量或者大型数据结构，如果定时器没有被销毁，这些引用关系可能导致所涉及的内存无法被垃圾回收，从而造成内存泄漏。

### Vue中销毁定时器
在Vue中，通常我们会在组件的生命周期钩子中设置和销毁定时器。最常见的做法是在`mounted`钩子中创建定时器，并在`beforeDestroy`（Vue 2.x）或`beforeUnmount`（Vue 3.x）钩子中销毁定时器。例如：
```javascript
export default {
  mounted() {
    this.timer = setInterval(() => {
      console.log('Interval triggered');
    }, 1000);
  },
  beforeDestroy() { // Vue 2.x
    clearInterval(this.timer);
  },
  beforeUnmount() { // Vue 3.x
    clearInterval(this.timer);
  }
}
```

### React中销毁定时器
在React中，定时器通常在组件的生命周期方法或者钩子中设置和清除。使用类组件时，你可以在`componentDidMount`中设置定时器，并在`componentWillUnmount`中清除。如果使用函数组件和Hooks，可以在`useEffect`钩子中处理定时器：
```js
import React, { useEffect } from 'react';

function MyComponent() {
  useEffect(() => {
    const timer = setInterval(() => {
      console.log('Interval triggered');
    }, 1000);

    // 清理函数
    return () => clearInterval(timer);
  }, []); // 空依赖数组表示这个effect只在组件挂载时运行一次

  return <div>Check the console.</div>;
}
```
在这个例子中，`useEffect`钩子的返回函数负责清除定时器，这个函数会在组件卸载时被调用，从而确保定时器被适当销毁。
通过这些方法，可以确保在组件或应用的生命周期结束时，相关的定时器也被正确清除，避免潜在的问题。