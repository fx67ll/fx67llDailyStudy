# Inherit
`js-inherit-work`

## 面试问题
> js*继承*有哪些方式？
> 不同继承方式有什么区别？
> 如何在工作中应用继承？  
> 待补充...  


# js继承有哪些方式？不同方式有什么区别？如何在工作中应用的？   
JavaScript 中的继承机制是多样的，每种方式有其特点和适用场景。以下是几种常见的继承方式，它们的区别，以及如何在工作中应用：

### 1. 原型链继承
**原理**：子类型的原型对象设置为父类型的一个实例。
```javascript
function Parent() {
    this.name = 'Parent';
}
Parent.prototype.getName = function() {
    return this.name;
};

function Child() {
    this.age = 18;
}
Child.prototype = new Parent();
```
**优点**：简单易懂。
**缺点**：所有实例共享父类实例属性，一个实例的修改可能影响所有实例。
**应用场景**：适合基本的继承需求，不涉及多实例共享属性的场景。

### 2. 构造函数继承（经典继承）
**原理**：在子类型构造函数中调用父类型构造函数。
```javascript
function Parent(name) {
    this.name = name;
}
function Child(name, age) {
    Parent.call(this, name);
    this.age = age;
}
```
**优点**：避免了原型链继承的引用属性共享问题，可以向父类型传递参数。
**缺点**：方法都在构造函数中定义，每次创建实例都会创建一遍方法。
**应用场景**：需要多个实例独立维护状态时使用，适用于属性不需要共享，且子类需要传递参数给父类的场景。

### 3. 组合继承（原型链 + 构造函数）
**原理**：使用原型链继承原型上的属性和方法，使用构造函数继承实例属性。
```javascript
function Parent(name) {
    this.name = name;
}
Parent.prototype.getName = function() {
    return this.name;
};

function Child(name, age) {
    Parent.call(this, name);
    this.age = age;
}
Child.prototype = new Parent();
```
**优点**：结合了原型链继承和构造函数继承的优点。
**缺点**：调用了两次父类构造函数（一次是设置子类型原型，一次是子类型构造函数内部），可能导致效率稍低。
**应用场景**：需要同时继承父类的属性和方法的场景。

### 4. 原型式继承
**原理**：使用一个对象作为另一个对象的基础。
```javascript
var parent = {
    name: 'Parent',
    getName: function() {
        return this.name;
    }
};
var child = Object.create(parent);
```
**优点**：简单，适合不需要单独创建构造函数的场景。
**缺点**：同原型链继承，共享引用类型属性的问题。
**应用场景**：快速创建一个与另一对象类似的对象时使用。

### 5. 寄生式继承
**原理**：创建一个仅用于封装继承过程的函数，该函数在内部以某种方式增强对象，最后返回对象。
```javascript
function createAnother(original) {
    var clone = Object.create(original);
    clone.sayHi = function() {
        console.log('hi');
    };
    return clone;
}
```
**优点**：可以在不影响对象的情况下，为对象添加方法和属性。
**缺点**：跟构造函数模式一样，每次创建对象都会创建一遍方法。
**应用场景**：需要扩展一个现有对象时使用。

### 6. 寄生组合式继承
**原理**：通过寄生方式来继承父类原型，然后再将结果指定给子类型的原型。
```javascript
function inheritPrototype(childObj, parentObj) {
    var prototype = Object.create(parentObj.prototype);
    prototype.constructor = childObj;
    childObj.prototype = prototype;
}
function Parent(name) {
    this.name = name;
}
Parent.prototype.getName = function() {
    return this.name;
};
function Child(name, age) {
    Parent.call(this, name);
    this.age = age;
}
inheritPrototype(Child, Parent);
```
**优点**：只调用一次父类构造函数，效率更高，避免在子类型的原型上创建不必要的、多余的属性。
**缺点**：实现较为复杂。
**应用场景**：适用于需要最优继承方式的复杂场景。

### 应用建议
在实际工作中，选择合适的继承方式取决于具体需求：  
- 如果需要简单的原型继承且不关心属性共享，可以使用原型链继承。  
- 如果需要实例具有独立的属性，可以使用构造函数继承。  
- 如果需要完整的继承解决方案，则组合继承和寄生组合式继承是更好的选择。  
- 对于不需要专门构造函数，只需扩展现有对象的场合，原型式继承或寄生式继承可以快速实现。  
