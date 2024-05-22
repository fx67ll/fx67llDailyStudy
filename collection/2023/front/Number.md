# Number  
`js-number-work`

## 面试问题
> 你平时工作中如何处理*数值操作*的相关需求？  
> 你工作中如何实现四舍五入的需求？  
> 你工作中是否遇到过精度丢失的问题，如何解决的？  
> 待补充...  


### 总结一下
1. 常见数值取整操作
+ 向上取整：Math.ceil  
+ 向下取整：Math.floor  
+ 四舍五入：Math.round  
+ 固定精度：toFixed  
+ 固定长度：toPrecision  


#### 参考资料
1. [JS用最简单的方法实现四舍五入](https://blog.csdn.net/shen516/article/details/118598916)  


## 你平时工作中如何处理**数值操作**的相关需求
在前端开发中，处理数值操作是一个常见的需求，涉及到各种场景，如计算、数据转换、动画处理等。以下是一些常见的数值操作需求及如何处理它们：

### 1. 精确的数值计算
JavaScript 中的数值是基于 IEEE 754 标准的双精度浮点数，这意味着在进行小数运算时可能会遇到精度问题。例如，`0.1 + 0.2` 不等于 `0.3`。为了处理这种问题，可以使用以下方法：
- **使用第三方库**：如 `decimal.js` 或 `big.js`，这些库提供了更精确的数值计算能力。
- **整数转换方法**：将小数转换为整数进行计算，例如，`(0.1 * 10 + 0.2 * 10) / 10`。

### 2. 货币和金融数据的格式化
在处理金融相关的应用时，通常需要对数值进行格式化，如添加千分位分隔符、货币符号等：
- **使用 `Intl.NumberFormat` API**：这是一个内置的国际化API，可以用来格式化数字，包括货币格式化。
  ```javascript
  const formatter = new Intl.NumberFormat('en-US', {
    style: 'currency',
    currency: 'USD',
  });
  console.log(formatter.format(1234567.89)); // "$1,234,567.89"
  ```

### 3. 数值转换
在前端开发中，经常需要将字符串转换为数字，或者反过来：
- **String to Number**：使用 `parseInt()`, `parseFloat()` 或简单的 `+` 操作符。
  ```javascript
  const num = parseInt("123", 10);
  const floatNum = parseFloat("123.45");
  const anotherNum = +"456";
  ```
- **Number to String**：使用 `toString()` 方法或字符串模板。
  ```javascript
  const num = 123;
  const str = num.toString();
  const str2 = `${num}`;
  ```

### 4. 处理大数值
JavaScript 中安全的整数范围是 `Number.MIN_SAFE_INTEGER` 到 `Number.MAX_SAFE_INTEGER`。超出这个范围的整数可能会失去精度。对于需要处理超大数值的情况：
- **使用 `BigInt`**：在 ES2020 引入了 `BigInt`，可以用来安全地处理非常大的整数。
  ```javascript
  const bigNumber = BigInt("1234567890123456789012345678901234567890");
  ```

### 5. 动画中的数值计算
在实现动画效果时，可能需要根据时间计算数值的变化：
- **使用 `requestAnimationFrame`**：这是一个浏览器API，用于在下一次重绘之前调用指定的回调函数，确保动画的平滑性。
  ```javascript
  let start = null;
  const element = document.getElementById('animate');
  function step(timestamp) {
    if (!start) start = timestamp;
    const progress = timestamp - start;
    element.style.transform = 'translateX(' + Math.min(progress/10, 200) + 'px)';
    if (progress < 2000) {
      requestAnimationFrame(step);
    }
  }
  requestAnimationFrame(step);
  ```

### 总结
在前端开发中，处理数值操作时需要注意精度问题、数据格式化、大数值处理以及动画效果中的实时计算等方面。根据具体需求选择合适的方法和工具是关键。