# one question every day night

#### 前言————每日提醒  
1. ***省钱***，在家的时候为下半年中级软考准备，**11月4/5**日考试  
2. 少食多餐，每日一小时运动，**11月30日**之前需要体检，目标降到 *(80kg)*  
3. 每日至少一小时面试题 *(可以是口述提，也可以是笔试题：sql题、java题、js题)*  
4. `SpringBoot`敏捷开发，每天只花一个小时完成一个小功能  

<span id="page-home"></span>

### 目录
1. *2023-08-01* ———— js如何创建对象？[查看解析](#js-create-object)  


## 2023年8月1日  
**JavaScript 如何创建对象？**
<span id="js-create-object"></span>
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
### 参考资料
1. chatGPT
2. [js创建对象的三种方法](https://blog.csdn.net/qq_73599840/article/details/128177248)  
#### 返回目录
[点击此处一键返回目录](#page-home)  