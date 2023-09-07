# one question every day night

#### 前言————每日提醒  
1. ***节省开支***，在家的时候为下半年中级软考准备，**11月4/5**日考试  
2. 少食多餐，每日一小时运动，**11月30日**之前需要体检，目标降到 *(80kg)*  
3. 每日至少一小时面试题 *(可以是口述提，也可以是笔试题：sql题、java题、js题)*  
4. `SpringBoot`敏捷开发，每日尝试推进一个小功能  

<span id="page-home"></span>

### 目录
+ *2023-09-21*  
	> 你是如何**捕获前端错误**的？  
	> 是否了解**前端安全**问题？  
	> [查看解析](#js-save-error)
+ *2023-09-20*  
	> 你是如何**优化前端内存开销**的？  
	> [查看解析](#js-memory-optimize)
+ *2023-09-19*  
	> 你是如何处理**前端稳定性监控**问题的？  
	> 或者说你是如何监控**首屏加载性能**的？  
	> [查看解析](#js-stability)
+ *2023-09-18*  
	> 你是如何处理**前端性能优化**问题的？  
	> [查看解析](#js-performance)
+ *2023-09-15*  
	> 你平时工作中如何处理**数值操作**的相关需求？
	> [查看解析](#js-number)
+ *2023-09-14*  
	> 你知道哪些**http响应码**？  
	> [查看解析](#js-http-code)
+ *2023-09-13*  
	> 什么是js**事件循环**（`Event Loop`）？  
	> 什么是**宏任务**和**微任务**？
	> 宏任务和微任务有什么区别？  
	> 为什么 `Promise` 比 `setTimeout` 快？  
	> **如何自己写一个Promise？**（*曾经面试非常尴尬没有回答出来*）  
	> [查看解析](#js-event-loop)  
+ *2023-09-12*  
	> 你知道哪些js**数组操作**？  
	> 工作中常用哪些方法？  
	> [查看解析](#js-array)  
+ *2023-09-11*  
	> js**继承**有哪些方式？  
	> 你是如何在工作中应用的？  
	> [查看解析](#js-inherit)  
+ *2023-09-08*  
	> js有哪些**数据类型**？  
	> 如何实现**深拷贝**（`Deep Clone`）？  
	> 深拷贝和浅拷贝有什么区别？  
	> [查看解析](#js-deep-clone)  
+ *2023-09-07*  
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


## 2023年8月21日  
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


## 2023年8月20日  
<span id="js-memory-optimize"></span>
> 你是如何**优化前端内存开销**的？  
### 解答思路（*待补充完善*）  
#### 参考资料
1. [前端面试真题宝典（二）———— 前端内存处理](https://blog.csdn.net/shadowfall/article/details/127660228)  
### 返回目录
[点击此处一键返回目录](#page-home)  


## 2023年8月19日  
<span id="js-stability"></span>
> 你是如何处理**前端稳定性监控**问题的？  
> 或者说你是如何监控**首屏加载性能**的？  
### 解答思路（*待补充完善*）  
#### 参考资料
1. [前端面试真题宝典（二）———— 前端稳定性监控](https://blog.csdn.net/shadowfall/article/details/127660228)  
### 返回目录
[点击此处一键返回目录](#page-home)  


## 2023年9月18日  
<span id="js-performance"></span>
> 你是如何处理**前端性能优化**问题的？  
### 解答思路（*待补充完善*）  
#### 参考资料
1. [前端面试真题宝典（一）———— 前端性能优化](https://blog.csdn.net/shadowfall/article/details/127287451)  
### 返回目录
[点击此处一键返回目录](#page-home)  


## 2023年9月15日  
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


## 2023年9月14日  
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


## 2023年9月13日  
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


## 2023年9月12日  
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


## 2023年9月11日  
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


## 2023年9月8日  
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


## 2023年9月7日  
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
参考自己总结的[博文](https://fx67ll.xyz/archives/js-debounce-throttle)  
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
