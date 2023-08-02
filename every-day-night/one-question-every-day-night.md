# one question every day night

#### 前言————每日提醒  
1. ***节省开支***，在家的时候为下半年中级软考准备，**11月4/5**日考试  
2. 少食多餐，每日一小时运动，**11月30日**之前需要体检，目标降到 *(80kg)*  
3. 每日至少一小时面试题 *(可以是口述提，也可以是笔试题：sql题、java题、js题)*  
4. `SpringBoot`敏捷开发，每日尝试推进一个小功能  

<span id="page-home"></span>

### 目录
+ *2023-08-13*  
	> 你是如何**捕获前端错误**的？  
	> 是否了解**前端安全**问题？  
	> [查看解析](#js-save-error)
+ *2023-08-12*  
	> 你是如何**优化前端内存开销**的？  
	> [查看解析](#js-memory-optimize)
+ *2023-08-11*  
	> 你是如何处理**前端稳定性监控**问题的？  
	> 或者说你是如何监控**首屏加载性能**的？  
	> [查看解析](#js-stability)
+ *2023-08-10*  
	> 你是如何处理**前端性能优化**问题的？  
	> [查看解析](#js-performance)
+ *2023-08-09*  
	> 你平时工作中如何处理**数值操作**的相关需求？
	> [查看解析](#js-number)
+ *2023-08-08*  
	> 你知道哪些**http响应码**？  
	> [查看解析](#js-http-code)
+ *2023-08-07*  
	> 什么是js**事件循环**（`Event Loop`）？  
	> 什么是**宏任务**和**微任务**？
	> 宏任务和微任务有什么区别？  
	> 为什么 `Promise` 比 `setTimeout` 快？  
	> **如何自己写一个Promise？**（*曾经面试非常尴尬没有回答出来*）  
	> [查看解析](#js-event-loop)  
+ *2023-08-06*  
	> 你知道哪些js**数组操作**？  
	> 工作中常用哪些方法？  
	> [查看解析](#js-array)  
+ *2023-08-05*  
	> js**继承**有哪些方式？  
	> 你是如何在工作中应用的？  
	> [查看解析](#js-inherit)  
+ *2023-08-04*  
	> js有哪些**数据类型**？  
	> 如何实现**深拷贝**（`Deep Clone`）？  
	> 深拷贝和浅拷贝有什么区别？  
	> [查看解析](#js-deep-clone)  
+ *2023-08-03*  
	> 什么是js**闭包**？  
	> 工作中用到过闭包吗？  
	> [查看解析](#js-closure)  
+ *2023-08-02*  
	> 什么是js的**防抖**（`Debounce`）和**节流**（`Throttle`）？  
	> 你是如何在工作中应用的？  
	> [查看解析](#js-debounce-throttle)  
+ *2023-08-01*   
	> js如何**创建对象**？  
	> js有哪些**创建对象**的方式？
	> [查看解析](#js-create-object)  



*=======================模板========================*
## 2023年xx月xx日  
<span id="xxx"></span>
> xxx  
### 解答思路（*待补充完善*）  
#### 参考资料
### 返回目录
[点击此处一键返回目录](#page-home)  
*===================================================*


## 2023年8月13日  
<span id="js-save-error"></span>
> 你是如何**捕获前端错误**的？  
> 是否了解**前端安全**问题？  
### 解答思路（*待补充完善*）  
```
XSS（跨站脚本攻击）和 CSRF（跨站请求伪造）
```
#### 参考资料
1. [前端面试真题宝典（二）———— 错误捕捉](https://blog.csdn.net/shadowfall/article/details/127660228)  
2. [前端面试真题宝典（一）———— 前端安全xss和csrf](https://blog.csdn.net/shadowfall/article/details/127287451)  
3. [前端安全系列（二）：如何防止CSRF攻击？](https://www.freebuf.com/articles/web/186880.html)，同源策略以及添加token校验  
### 返回目录
[点击此处一键返回目录](#page-home)  


## 2023年8月12日  
<span id="js-memory-optimize"></span>
> 你是如何**优化前端内存开销**的？  
### 解答思路（*待补充完善*）  
#### 参考资料
1. [前端面试真题宝典（二）———— 前端内存处理](https://blog.csdn.net/shadowfall/article/details/127660228)  
### 返回目录
[点击此处一键返回目录](#page-home)  


## 2023年8月11日  
<span id="js-stability"></span>
> 你是如何处理**前端稳定性监控**问题的？  
> 或者说你是如何监控**首屏加载性能**的？  
### 解答思路（*待补充完善*）  
#### 参考资料
1. [前端面试真题宝典（二）———— 前端稳定性监控](https://blog.csdn.net/shadowfall/article/details/127660228)  
### 返回目录
[点击此处一键返回目录](#page-home)  


## 2023年8月10日  
<span id="js-performance"></span>
> 你是如何处理**前端性能优化**问题的？  
### 解答思路（*待补充完善*）  
#### 参考资料
1. [前端面试真题宝典（一）———— 前端性能优化](https://blog.csdn.net/shadowfall/article/details/127287451)  
### 返回目录
[点击此处一键返回目录](#page-home)  


## 2023年8月9日  
<span id="js-number"></span>
> 你平时工作中如何处理**数值操作**的相关需求？  
### 解答思路（*待补充完善*） 
1. 常见数值取整操作
+ 向上取整：Math.ceil  
+ 向下取整：Math.floor  
+ 四舍五入：Math.round  
+ 固定精度：toFixed  
+ 固定长度：toPrecision  
+ 取整：parseInt、位运算  
#### 参考资料
1. [JS用最简单的方法实现四舍五入](https://blog.csdn.net/shen516/article/details/118598916)  
### 返回目录
[点击此处一键返回目录](#page-home)  


## 2023年8月8日  
<span id="js-http-code"></span>
> 你知道哪些**http响应码**？  
### 解答思路（*待补充完善*）  
```
404 请求失败，请求所希望得到的资源未被在服务器上发现
502 服务器作为网关需要得到一个处理这个请求的响应，但是得到一个错误的响应  
301 被请求的资源已永久重定向到新位置  
```
#### 参考资料
1. [常见的62种http响应代码整理](https://zhuanlan.zhihu.com/p/459501342)  
### 返回目录
[点击此处一键返回目录](#page-home)  


## 2023年8月7日  
<span id="js-event-loop"></span>
> 什么是js**事件循环**（`Event Loop`）？  
> 什么是**宏任务**和**微任务**？
> 宏任务和微任务有什么区别？  
> 为什么 `Promise` 比 `setTimeout` 快？  
> `Promise.all` 和 `Promise.race` 的区别?  
> **如何自己写一个Promise？**（*曾经面试非常尴尬没有回答出来*）  
### 解答思路（*待补充完善*）  
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
### 返回目录
[点击此处一键返回目录](#page-home)  


## 2023年8月6日  
<span id="js-array"></span>
> 你知道哪些js**数组操作**？  
> 工作中常用哪些方法？  
### 解答思路（*待补充完善*）  
1. 常用数组操作  
+ `push` => 尾部添加  
+ `unshift` => 头部添加  
+ `pop` => 尾部删除  
+ `shift` => 头部删除  
+ `concat(arr1, arr2)` => 两个数组拼接  
+ `splice(startIndex, deleteCount, item1, item2, ...)` => 如果有item，则为替换，否则直接删除指定长度  
+ `slice(beginIndex, endIndex)` => 浅拷贝，包括beginIndex，不包括endIndex   
+ `split('')` => 指定字符分割  
+ `join('')` => 指定字符拼接  
+ `reverse` => 数组反转  
+ `sort` => 数组排序  
+ `forEach` => for替代，但是不容易退出循环  
+ `map` => 返回一个处理后的数组  
+ `filter` => 返回一个符合过滤规则的数组  
+ `find` => 返回符合过滤规则的第一个元素，否则返回undefined  
#### 参考资料
1. [js数组的常用方法：在头部插入，删除，尾部插入，删除等等](https://blog.csdn.net/qq_41619796/article/details/111414765) 
2. [js将字符串数组转化为数字数组（互换）的方式](https://www.cnblogs.com/Samuel-Leung/p/13962322.html)  
3. [js数组对象去重](https://blog.csdn.net/weixin_43045869/article/details/125884799)  
4. [js中的reduce()函数讲解](https://www.jb51.net/article/154881.htm)  
5. [js 将一个数组添加到另一个数组中](https://blog.csdn.net/qq_43649223/article/details/125659634)  
6. [JS数组常用的操作方法](https://blog.csdn.net/qq_41926416/article/details/121137061)  
### 返回目录
[点击此处一键返回目录](#page-home)  


## 2023年8月5日  
<span id="js-inherit"></span>
> js**继承**有哪些方式？  
> 你是如何在工作中应用的？ 
### 解答思路（*待补充完善*）  
```
原型链继承
借用构造函数继承（伪造对象、经典继承）
实例继承（原型式继承）
组合式继承
寄生组合继承
es6继承 extends
```
#### 参考资料
### 返回目录
[点击此处一键返回目录](#page-home)  


## 2023年8月4日  
<span id="js-deep-clone"></span>
> js有哪些**数据类型**？  
> 如何实现**深拷贝**（`Deep Clone`）？  
> 深拷贝和浅拷贝有什么区别？  
### 解答思路（*待补充完善*）  
```
基本数据类型：string、number、boolean、undefined、null
引用数据类型：object、array、function
JS数据类型分为基本数据类型和引用数据类型，基本数据类型保存的是值，引用类型保存的是引用地址(this指针)。浅拷贝共用一个引用地址，深拷贝会创建新的内存地址。

Object.assign：对象的合并 （第一级属性深拷贝，第一级以下的级别属性浅拷贝。）
ES6中的 Object.assign()，第一个参数必须是个空对象。
Object.assign() 方法可以把任意多个的源对象自身的可枚举属性拷贝给目标对象，然后返回目标对象。
```
#### 参考资料
### 返回目录
[点击此处一键返回目录](#page-home)  


## 2023年8月3日  
<span id="js-closure"></span>
> 什么是js**闭包**？  
> 工作中用到过闭包吗？  
### 解答思路（*待补充完善*）  
1. `函数` 和 `函数内部能访问到的变量`（也叫环境）的总和，就是一个闭包  
2. 闭包是能够读取其他函数内部变量的函数，由于在JavaScript中，只有函数内部的子函数才能读取局部变量，所以说，闭包可以简单理解为定义在一个函数内部的函数  
3. 闭包的作用就是保护变量不被污染，在实际开发中，经常使用到闭包的地方就是封装，如：vue组件、网络请求二次封装等  
#### 参考资料
1. [什么是闭包？在实际开发中是如何使用闭包？](https://blog.csdn.net/return_o/article/details/128252191)  
### 返回目录
[点击此处一键返回目录](#page-home)  


## 2023年8月2日  
<span id="js-debounce-throttle"></span>
> 什么是js的**防抖**（`Debounce`）和**节流**（`Throttle`）？  
> 你是如何在工作中应用的？  
### 解答思路
#### 自行查询资料的结果
1. 防抖是什么？在工作中的主要应用场景？  
	- 在规定时间内多次触发函数，只执行最后一次（可以理解为LOL回城计时，打断后需要重新计时）  
	- 在事件被触发n秒后再执行回调函数，如果在这n秒内又被触发，则重新计时  
	- 场景一：用户在输入框中连续输入一串字符后，只会在输入完后去执行最后一次的查询ajax请求，这样可以有效减少请求次数，节约请求资源  
	- 场景二：window的resize、scroll事件，不断地调整浏览器的窗口大小、或者滚动时会触发对应事件，防抖让其只触发一次  
2. 节流是什么？在工作中的主要应用场景？
	- 在规定时间内多次触发函数，只执行第一次  
	- 规定一个单位时间，在这个单位时间内，只能有一次触发事件的回调函数执行，如果在同一个单位时间内某事件被触发多次，只有一次能生效  
	- 场景一：鼠标连续不断地触发某事件（如点击），只在单位时间内只触发一次  
	- 场景二：在页面的无限加载场景下，需要用户在滚动页面时，每隔一段时间发一次 ajax 请求，而不是在用户停下滚动页面操作时才去请求数据  
3. 防抖和节流的区别？
	- 函数防抖是某一段时间内只执行一次  
	- 而函数节流是间隔时间执行，不管事件触发有多频繁，都会保证在规定时间内一定会执行一次真正的事件处理函数  
	- 防抖是维护一个计时器，规定在delay时间后触发函数，但是在delay时间内再次触发的话，都会清除当前的 timer 然后重新设置超时调用，即重新计时。这样一来，只有最后一次操作能被触发  
	- 节流是通过判断是否到达一定时间来触发函数，若没到规定时间则使用计时器延后，而下一次事件则会重新设定计时器  
#### chatGPT的回答
1. 什么是js的防抖和节流?
```
在 JavaScript 中，防抖（debounce）和节流（throttle）是用来限制函数执行频率的两种常见技术。

防抖（debounce）是指在某个时间段内，只执行最后一次触发的函数调用。如果在这个时间段内再次触发该函数，会重新计时，直到等待时间结束才会执行函数。
这个技术通常用于处理频繁触发的事件，比如窗口大小调整、搜索框输入等。防抖可以避免函数执行过多次，减少性能负担。

节流（throttle）是指在一段时间内限制函数的执行频率，保证一定时间内只执行一次函数调用。无论触发频率多高，都会在指定时间间隔内执行一次函数。
这个技术通常用于处理连续触发的事件，比如滚动事件、鼠标移动事件等。节流可以控制函数的执行频率，
```
2. 用js写一个防抖的工具函数
```
function debounce(func, delay) {
  let timeoutId;
  
  return function() {
    const context = this;
    const args = arguments;
    
    clearTimeout(timeoutId);
    
    timeoutId = setTimeout(function() {
      func.apply(context, args);
    }, delay);
  };
}

这个防抖函数接受两个参数：func表示需要进行防抖的函数，delay表示延迟的时间间隔（以毫秒为单位）。函数内部使用了一个timeoutId变量来保存定时器的标识。
当调用防抖函数返回的新函数时，会清除之前的定时器，并设置一个新的定时器。只有在延迟时间内没有再次调用该新函数时，才会触发最终的函数执行。

以下是一个示例用法：

function handleScroll() {
  console.log('Scroll event debounced');
}
const debouncedScroll = debounce(handleScroll, 200);
window.addEventListener('scroll', debouncedScroll);
```
3. 用js写一个节流的工具函数
```
function throttle(func, delay) {
  let timeoutId;
  let lastExecTime = 0;

  return function(...args) {
    const currentTime = Date.now();
    const remainingTime = delay - (currentTime - lastExecTime);

    clearTimeout(timeoutId);

    if (remainingTime <= 0) {
      func.apply(this, args);
      lastExecTime = currentTime;
    } else {
      timeoutId = setTimeout(() => {
        func.apply(this, args);
        lastExecTime = Date.now();
      }, remainingTime);
    }
  };
}

这个节流函数接受两个参数：func 是要执行的函数，delay 是延迟时间（以毫秒为单位）。
它返回一个新的函数，该函数在调用时会根据指定的延迟时间来限制原始函数的执行频率。

以下是一个示例用法：
该示例中，handleScroll 函数将被限制为每 200 毫秒执行一次，即使滚动事件触发频率更高。

function handleScroll() {
  console.log('Scrolled');
}

const throttledScroll = throttle(handleScroll, 200);

window.addEventListener('scroll', throttledScroll);
```
4. 工作中哪些场景可以使用防抖函数？
```
在工作中，防抖函数可以提升性能并减少网络开销。

用户输入：当用户在表单输入框中频繁输入时，可以使用防抖函数来延迟处理用户输入，避免频繁的请求或操作，提高性能和用户体验。

搜索框：在搜索框中，当用户连续输入关键字时，可以使用防抖函数来延迟发送搜索请求，以避免请求过多。

窗口调整：当窗口大小调整时，会触发resize事件，可以使用防抖函数来限制resize事件的触发次数，避免频繁执行调整相关的代码。

按钮点击：当按钮被频繁点击时，可以使用防抖函数来限制按钮点击的触发次数，
```
5. 工作中哪些场景可以使用节流函数？
```
在工作中，节流函数可以用来控制频繁触发的事件，以减少资源消耗和提高性能。下面是一些应用节流函数的场景和步骤：

用户输入事件：当用户在文本框中输入时，触发搜索功能。使用节流函数可以限制搜索请求的频率，以避免频繁的网络请求。例如，可以设置一个定时器，在用户输入后的一小段时间内不触发搜索请求，只在定时器结束后才进行搜索。

页面滚动事件：当用户滚动页面时，触发加载更多数据的操作。使用节流函数可以限制加载操作的频率，以提高页面的响应性能。例如，可以设置一个定时器，在用户滚动过程中只触发加载操作的最后一次滚动事件。

频繁点击事件：当用户频繁点击某个按钮时，触发某个操作。使用节流函数可以限制点击操作的频率，以避免重复操作或者混乱的界面状态。例如，可以设置一个定时器，在用户点击后的一小段时间内不触发重复操作。

在实际应用中，可以使用不同编程语言或框架提供的节流函数库或实现自定义的节流函数。例如，在JavaScript中，可以使用lodash库提供的throttle函数来实现节流功能。

总结起来，通过应用节流函数，可以控制事件的触发频率，避免频繁的操作并提高系统性能。在不同的应用场景中，根据具体需求选择合适的节流函数，
```
### 返回目录
[点击此处一键返回目录](#page-home)  


## 2023年8月1日  
<span id="js-create-object"></span>
> js如何**创建对象**？  
> js有哪些**创建对象**的方式？
### 解答思路  
1. 使用花括号  `{}` 直接创建对象 
```
const obj = {};
const obj = {
	key: value
}
```
2. 使用构造函数创建对象
```
const newObj = (valueA, valueB) => {
	this.keyA = valueA;
	this.keyB = valueB;
	this.testMethod = valueC => {
		console.log('valueC:', valueC);
	}
}
const obj = new newObj(A, B);
```
3. 使用 `new Object()` 创建对象  
```
const obj = new Object;
obj.key = value;
obj.testMethod = () => {
	console.log('new obj');
}
```
4. 使用 `Object.create()` 创建对象  
```
const obj = Object.create(null);
obj.key1 = value1;
obj.key2 = value2;
```
5. 使用 `class` 关键字创建对象（*ES6及以上版本*）
```
class MyClass {
  constructor(key1, key2) {
    this.key1 = key1;
    this.key2 = key2;
  }
  testMethod() {
    console.log('new obj');
  }
}
const obj = new MyClass(value1, value2);
```
### 返回目录
[点击此处一键返回目录](#page-home)  