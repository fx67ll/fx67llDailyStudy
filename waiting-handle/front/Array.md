# Array
`js-array-work`

## 面试问题  
> 你知道哪些*js数组操作*？  
> 工作中常用哪些方法？  
> 如何判断一个变量是否是数组？有哪些判断方式？  
> if条件中空数组是`false`还是`true`？还有哪些变量值被判断为`false`的情况？  
> 待补充...  


# 你知道哪些js数组操作?  
1. **`push()`** - 向数组的末尾添加一个或多个元素，并返回新的长度。
2. **`pop()`** - 删除数组的最后一个元素并返回该元素。
3. **`shift()`** - 删除数组的第一个元素并返回该元素，数组中的其他元素向前移动。
4. **`unshift()`** - 向数组的开头添加一个或多个元素，并返回新的长度。
5. **`slice()`** - 返回数组的一个片段或子数组。
6. **`splice()`** - 用于插入、删除或替换数组的元素。
7. **`map()`** - 创建一个新数组，其结果是该数组中的每个元素都调用一个提供的函数后的返回值。
8. **`filter()`** - 创建一个新数组，包含通过所提供函数实现的测试的所有元素。
9. **`reduce()`** - 对累加器和数组中的每个元素（从左到右）应用一个函数，将其减少为单个值。
10. **`forEach()`** - 对数组的每个元素执行一次提供的函数。
11. **`find()`** - 返回数组中满足提供的测试函数的第一个元素的值，否则返回 `undefined`。
12. **`findIndex()`** - 返回数组中满足提供的测试函数的第一个元素的索引，否则返回 `-1`。
13. **`sort()`** - 对数组的元素进行排序，并返回数组。
14. **`reverse()`** - 颠倒数组中元素的顺序。
15. **`concat()`** - 用于合并两个或多个数组。
16. **`join()`** - 把数组的所有元素放入一个字符串。
17. **`includes()`** - 判断一个数组是否包含一个指定的值，根据情况返回 true 或 false。
18. **`some()`** - 测试数组中是不是至少有一个元素通过了被提供的函数测试。
19. **`every()`** - 测试一个数组内的所有元素是否都能通过某个指定函数的测试。


# 工作中常用哪些数组方法?
在实际开发中，以下几种数组方法尤为常用：
- **`map()`**：当需要对数组的每个元素执行同一操作时，如转换数据格式或计算数组元素的值。
- **`filter()`**：用于从数组中选出符合特定条件的元素，非常适合用于数据筛选。
- **`reduce()`**：适用于累加操作，例如计算总和或将数组元素组合成单个值。
- **`forEach()`**：用于执行数组中每个元素的侧效操作，例如打印或修改外部变量。
- **`sort()`**：在需要对数组进行排序时使用，可以自定义排序逻辑。
- **`find()`** 和 **`findIndex()`**：当需要查找数组中符合条件的第一个元素或其索引时使用。
- **`splice()`**：在需要同时对数组进行元素的删除和添加操作时非常有用。
- **`concat()`**：用于合并多个数组成一个新数组，常用于不改变原数组的情况下创建新的数组集合。


# 如何判断一个变量是否是数组？有哪些判断方式？
在JavaScript中，判断一个变量是否是数组可以通过多种方式实现。这些方法各有优缺点，适用于不同的场景。以下是几种常见的判断数组的方法：

### 1. 使用 `Array.isArray()` 方法（推荐）
`Array.isArray()` 是 ECMAScript 5 新增的方法，它提供了一种简单、可靠的方式来判断一个变量是否是数组。这是判断数组的最推荐方式。
```javascript
let arr = [1, 2, 3];
console.log(Array.isArray(arr)); // 输出：true
```

### 2. 使用 `instanceof` 操作符
`instanceof` 操作符用于测试一个对象在其原型链中是否存在一个构造函数的 `prototype` 属性。
```javascript
let arr = [1, 2, 3];
console.log(arr instanceof Array); // 输出：true
```
但是，`instanceof` 可能在不同的执行环境（如不同的iframe或window对象）中不一定可靠，因为数组的构造器可能不同。

### 3. 使用 `Object.prototype.toString.call()`
这是一个更加通用的方法，可以用来获取任意对象的类型。对于数组，`Object.prototype.toString.call()` 返回 `"[object Array]"`。
```javascript
let arr = [1, 2, 3];
console.log(Object.prototype.toString.call(arr) === '[object Array]'); // 输出：true
```
这种方法相对可靠，并且在不同的执行环境中也能保持一致性。

### 4. 使用构造函数属性 `constructor`
每个数组都有一个 `constructor` 属性，指向它的构造函数。如果这个属性是 `Array`，那么对象通常是数组。但这种方法不是非常可靠，因为 `constructor` 属性可以被改写。
```javascript
let arr = [1, 2, 3];
console.log(arr.constructor === Array); // 输出：true
```

### 5. 使用 `Array.prototype.isPrototypeOf()`
这个方法可以用来检查 `Array.prototype` 是否存在于某个对象的原型链上。
```javascript
let arr = [1, 2, 3];
console.log(Array.prototype.isPrototypeOf(arr)); // 输出：true
```

### 总结
- **最推荐的方法**：`Array.isArray()`，因为它简单且总是可靠的。
- **较可靠的方法**：`Object.prototype.toString.call()`，尤其是在涉及多个执行环境时。
- **其他方法**：虽然 `instanceof`、`constructor` 和 `isPrototypeOf` 可以用来判断数组，但它们在某些情况下可能不够可靠或容易受到环境的影响。

在实际开发中，选择合适的方法取决于你的具体需求和执行环境。


# if条件中空数组是false还是true？还有哪些变量值被判断为false的情况？
在 JavaScript 中，空数组（`[]`）在 `if` 条件判断中被视为 `true`。这是因为所有对象，包括数组（无论是否为空），在布尔上下文中都被视为 `true`。
这意味着即使数组没有任何元素，它仍然被认为是真值。

### 为什么空数组是 `true`？
在 JavaScript 中，只有少数特定的值被认为是 "falsy"（即在布尔上下文中被视为 `false`）。对象（包括数组和函数）不在这些 falsy 值之中，因此它们在布尔上下文中被转换为 `true`。

### Falsy 值
以下是 JavaScript 中被认为是 `false` 的 "falsy" 值列表：
1. **`false`** - 布尔值 `false` 本身自然是 falsy。
2. **`0`** 和 **`-0`** - 数字零和负零。
3. **`""`**（空字符串） - 双引号或单引号中没有任何字符。
4. **`null`** - 表示无值。
5. **`undefined`** - 变量已声明但未赋值时的默认值。
6. **`NaN`** - 表示 "不是一个数字" 的特殊值。

### 示例
这里有一些示例，显示如何在 `if` 条件中测试这些 falsy 值：
```javascript
if (false) {} // 不执行
if (0) {} // 不执行
if (-0) {} // 不执行
if ("") {} // 不执行
if (null) {} // 不执行
if (undefined) {} // 不执行
if (NaN) {} // 不执行
if ([]) {} // 执行，因为空数组是 true
```

在实际的编程实践中，了解哪些值是 falsy 非常重要，因为它们会影响条件语句的行为。