# Shallow & Deep Clone

## 面试问题
> 如何实现*深拷贝*？  
> 深拷贝和浅拷贝有什么区别？ 
> 开发中如何避免发生浅拷贝？  
> 为什么展开运算符是浅拷贝?  
> js有哪些数据类型？哪些是基本数据类型？哪些是引用类型？ 
> 待补充...  


# js中如何实现深拷贝？深拷贝和浅拷贝的区别？开发中如何避免发生浅拷贝？
在 JavaScript 中，理解深拷贝和浅拷贝的区别及其实现方式对于管理复杂数据结构非常重要。以下是深拷贝和浅拷贝的区别和实现方法的详细解释：

### 深拷贝与浅拷贝的区别
1. **浅拷贝（Shallow Copy）**：
   - 浅拷贝只复制对象的第一层属性。如果属性值是基本数据类型，拷贝的是值；如果属性值是引用数据类型（如对象或数组），拷贝的是内存地址（引用），因此原始数据和拷贝数据会共享相同的引用对象。
   - 修改引用数据类型的属性时，原始对象和拷贝对象都会受到影响。
2. **深拷贝（Deep Copy）**：
   - 深拷贝会递归复制所有层级的属性，确保原始数据和拷贝数据在内存中完全独立。修改拷贝对象不会影响原始对象。
   - 实现深拷贝通常需要递归调用或使用特定的库函数。

### 如何实现深拷贝
1. **使用 JSON 方法**：
   - 最简单的深拷贝实现可以通过 JSON 的序列化和反序列化完成。但这种方法不能复制函数、`undefined`、`Symbol` 等特殊类型的数据，也无法处理循环引用的情况。
   ```javascript
   const obj = {
       a: 1,
       b: {
           c: 2
       }
   };
   const deepCopy = JSON.parse(JSON.stringify(obj));
   deepCopy.b.c = 3;
   console.log(obj.b.c); // 输出 2
   ```
2. **使用库（如 Lodash 的 `cloneDeep` 方法）**：
   - 一些 JavaScript 库如 Lodash 提供了深拷贝的实现。这些实现通常更为完整，能处理各种数据类型和复杂的数据结构。
   ```javascript
   import _ from 'lodash';
   const obj = {
       a: 1,
       b: {
           c: 2
       }
   };
   const deepCopy = _.cloneDeep(obj);
   deepCopy.b.c = 3;
   console.log(obj.b.c); // 输出 2
   ```
3. **手动实现递归深拷贝**：
   - 你可以手动编写一个递归函数来实现深拷贝。这种方法需要处理各种数据类型和循环引用的问题。
   ```javascript
   function deepClone(obj, hash = new WeakMap()) {
       if (obj === null) return null; 
       if (typeof obj !== 'object') return obj;
       if (obj instanceof Date) return new Date(obj);
       if (obj instanceof RegExp) return new RegExp(obj);
       if (hash.has(obj)) return hash.get(obj);
       
       const cloneObj = new obj.constructor();
       hash.set(obj, cloneObj);
       
       for (const key in obj) {
           if (obj.hasOwnProperty(key)) {
               cloneObj[key] = deepClone(obj[key], hash);
           }
       }
       return cloneObj;
   }
   ```

### 避免浅拷贝的方法
- 在处理复杂的数据结构时，尤其是包含嵌套对象或数组时，避免使用如 `Object.assign()` 或展开运算符（`...`）这样的浅拷贝方法。
- 使用深拷贝方法（如上述的 JSON 方法或 Lodash 的 `cloneDeep`）来确保数据的完整独立性。
- 在不需要完整拷贝对象的情况下，明确你的需求，选择合适的拷贝策略。

通过理解和正确应用深拷贝与浅拷贝的区别和技术，可以有效避免在 JavaScript 开发中遇到的许多常见问题。


# 为什么展开运算符是浅拷贝？
展开运算符（spread operator）在 JavaScript 中用于“展开”数组或对象的元素。当用于对象或数组时，展开运算符仅复制第一层的元素到新的数组或对象中。
这意味着如果原始数据结构中包含嵌套的对象或数组，这些嵌套的结构不会被真正地复制，而是复制它们的引用。因此，展开运算符实际上进行的是浅拷贝。

### 示例说明：
#### 对象的浅拷贝
```javascript
const original = {
    a: 1,
    b: {
        c: 2
    }
};
const copied = { ...original };
copied.a = 3; // 修改基本类型值
copied.b.c = 3; // 修改引用类型值
console.log(original); // 输出：{ a: 1, b: { c: 3 } }
console.log(copied);  // 输出：{ a: 3, b: { c: 3 } }
```
在这个例子中，修改 `copied.b.c` 同时也改变了 `original.b.c`，因为 `b` 属性的值（一个对象）通过引用被复制到了 `copied` 对象中。
#### 数组的浅拷贝
```javascript
const originalArray = [1, { b: 2 }, 3];
const copiedArray = [...originalArray];
copiedArray[1].b = 3; // 修改数组中对象的属性
console.log(originalArray); // 输出：[1, { b: 3 }, 3]
console.log(copiedArray);  // 输出：[1, { b: 3 }, 3]
```
这个例子同样展示了修改 `copiedArray` 中的对象属性 `b` 时，`originalArray` 中相应的属性也被改变了。这是因为数组中的对象是通过引用被复制的。

### 结论
展开运算符是浅拷贝，因为它仅复制数据的第一层。对于基本数据类型（如数字、字符串、布尔值等），这意味着它们的值被复制。对于对象和数组，这意味着它们的引用（而不是实际的对象或数组）被复制，所以原始数据和拷贝数据会共享这些嵌套的对象和数组。这在处理多层嵌套结构时尤其需要注意，因为对拷贝数据的修改可能会影响到原始数据。


# js有哪些数据类型？
在 JavaScript 中，数据类型分为两大类：基本数据类型（Primitive types）和引用数据类型（Reference types）。理解这两种类型的区别对于掌握 JavaScript 的数据操作和性能优化非常重要。

### 基本数据类型（Primitive types）
基本数据类型直接存储在栈（Stack）中，它们的值是不可变的。
当你对基本数据类型的变量进行操作时，实际上是在操作它的值的副本，而不是原始值本身。JavaScript 中的基本数据类型包括：
1. **Number**: 用于表示整数或浮点数，也包括特殊的数值如 `Infinity`, `-Infinity`, 和 `NaN`。
2. **BigInt**: 用于表示非常大的整数，超出了 `Number` 类型能够表示的范围。
3. **String**: 由字符组成的序列，用于表示文本数据，使用单引号、双引号或反引号表示。
4. **Boolean**: 表示逻辑实体，只有两个值，`true` 和 `false`，用于逻辑判断。
5. **Undefined**: 一个变量被声明了，但没有赋值时，它的值就是 `undefined`。
6. **Null**: 表示没有值或空值。通常用来表示变量将不会存储任何值。
7. **Symbol**: ES6 引入的新的基本数据类型，每个 `Symbol` 的值都是唯一的，常用于创建对象的私有成员。

### 引用数据类型（Reference types）
引用数据类型的值是对象，存储在堆（Heap）中，变量实际上存储的是一个指向堆内存中实际对象的指针。这意味着当你操作一个对象时，你是在操作对象的引用而不是实际的对象。引用数据类型包括：
1. **Object**: 基本的对象类型，几乎所有的 JavaScript 对象都是 `Object` 类型的实例。
   - **Date**: 用于处理日期和时间。
   - **RegExp**: 用于定义正则表达式。
   - **Array**和**Function**也都是对象。
   - 其他如 `Map`, `Set`, `WeakMap`, `WeakSet` 等也属于对象。  
2. **Array**: 用于存储有序集合的对象。  
3. **Function**: 函数实际上是一种特殊类型的对象，它具有可被执行的功能。

### 特殊提及
- **BigInt**: ES2020 引入的一种新的数字类型，可以表示非常大的整数。传统的 `Number` 类型只能安全地表示 `-2^53 + 1` 到 `2^53 - 1` 之间的整数，而 `BigInt` 可以表示任意大的整数。

### 类型检测
可以使用 `typeof` 操作符来检查一个变量的类型，除了 `null` 返回的是 `"object"`。
对于更复杂的类型判断，通常使用 `instanceof` 操作符或者 `Object.prototype.toString.call()` 方法。


### 总结
- **基本数据类型**：Number, String, Boolean, Undefined, Null, Symbol, BigInt
- **引用数据类型**：Object (包括 Array, Function, Date, RegExp 等)

JavaScript 的灵活性在很大程度上来自于它的动态类型系统和对各种数据类型的支持。
理解这些数据类型及其使用场景对于编写有效和高效的 JavaScript 代码至关重要。
了解这些类型及其分类有助于更好地理解 JavaScript 的内存管理和性能优化，以及如何在代码中有效地处理数据。
