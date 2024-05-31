# Closure  
`js-closure-work`

## 面试问题  
> 什么是js*闭包*？  
> 工作中闭包的使用场景有哪些？
> 工作中遇到过闭包陷阱吗？  
> Vue开发中如何避免闭包陷阱？  
> 详细说说如何在Vue中正确使用箭头函数和普通函数，用来避免闭包陷阱？
> React开发中如何避免闭包陷阱？  
> React开发过程中遇到的闭包陷阱有哪些？可否举例说明下？  
> 待补充...  


### 总结一下
1. `函数` 和 `函数内部能访问到的变量`（也叫环境）的总和，就是一个闭包  
2. 闭包是能够读取其他函数内部变量的函数，由于在JavaScript中，只有函数内部的子函数才能读取局部变量，所以说，闭包可以简单理解为定义在一个函数内部的函数  
3. 闭包的作用就是保护变量不被污染，在实际开发中，经常使用到闭包的地方就是封装，如：vue组件、网络请求二次封装等  


#### 参考资料
1. [什么是闭包？在实际开发中是如何使用闭包？](https://blog.csdn.net/return_o/article/details/128252191)  


## 什么是js的闭包？工作中闭包的使用场景有哪些？
闭包（Closure）是JavaScript的一个重要概念，它允许一个函数访问并操作该函数之外的变量。在技术上，闭包是：
- 当一个函数被创建时，它会记住自己被创建时的环境。
- 即使外部函数已经执行完毕，闭包也使得内部函数仍然可以访问外部函数的变量。

闭包的形成通常与以下几个JavaScript的特性有关：
1. **函数作为一等公民**：在JavaScript中，函数可以像任何其他值一样被传递和返回。
2. **函数作用域**：函数内部声明的变量只在函数内部可见。
3. **词法作用域**：函数的执行依赖于变量的作用域，这个作用域是在函数定义时决定的，而不是在函数调用时。

### 创建闭包的例子
```javascript
function outer() {
  let count = 0;  // 一个在outer函数中定义的变量
  function inner() {
    count++;
    console.log(count);
  }
  return inner;
}
const myFunction = outer();  // 创建闭包
myFunction();  // 输出: 1
myFunction();  // 输出: 2
```
在这个例子中，即使`outer`函数的执行已经完成，`inner`函数仍然可以访问和修改`outer`函数中的`count`变量。这就是闭包的作用。

### 工作中闭包的使用
#### 1. **数据封装和私有化**
闭包可以用来封装私有变量，提供公共的方法来操作这些私有变量，而不暴露细节。
```javascript
function createCounter() {
  let count = 0;
  return {
    increment: () => { count++; },
    decrement: () => { count--; },
    getCount: () => count
  };
}
const counter = createCounter();
counter.increment();
console.log(counter.getCount());  // 输出: 1
counter.decrement();
console.log(counter.getCount());  // 输出: 0
```
#### 2. **模块模式**
在模块模式中，闭包常用于创建模块的公共接口，同时隐藏内部的细节。
```javascript
const myModule = (function() {
  let privateVar = 'I am private';
  return {
    publicMethod: () => `The private variable is: ${privateVar}`
  };
})();
console.log(myModule.publicMethod());  // 可以访问公共方法，但不能直接访问私有变量
```
#### 3. **防抖和节流函数**
在事件处理和性能优化中，闭包用于实现防抖和节流函数，控制函数的执行频率。
```javascript
function debounce(func, wait) {
  let timeout;
  return function() {
    const context = this, args = arguments;
    clearTimeout(timeout);
    timeout = setTimeout(() => func.apply(context, args), wait);
  };
}
window.addEventListener('resize', debounce(() => {
  console.log('Resize event handler called');
}, 200));
```
#### 4. **函数柯里化**
闭包使得函数柯里化成为可能，柯里化是将接受多个参数的函数转换成接受一个单一参数的函数，并返回接受余下参数且返回结果的新函数的技术。
```javascript
function curry(fn) {
  return function curried(...args) {
    if (args.length >= fn.length) {
      return fn.apply(this, args);
    } else {
      return function(...args2) {
        return curried.apply(this, args.concat(args2));
      }
    }
  };
}
```

闭包是JavaScript中一个非常强大的特性，它不仅能帮助我们写出更优雅的代码，还能实现数据隐藏和封装等设计模式。正确使用闭包可以极大地提高代码的可维护性和可扩展性。


## 工作中遇到过闭包陷阱吗？
在面试中回答关于工作中遇到的闭包陷阱的问题时，可以采用以下步骤来构建你的回答：

### 1. 确认和理解闭包陷阱
首先，确认你对闭包陷阱的理解。闭包陷阱通常指的是因闭包导致的内存泄漏、性能问题或者意外的行为（如捕获过时的变量状态）。

### 2. 描述一个具体的例子
选择一个具体的例子来描述你在工作中如何遇到闭包陷阱。这个例子应该清晰地展示问题的发生以及它如何影响到了项目。
#### 示例回答：
在一个项目中，我们需要实现一个功能，当用户进行某些操作后，系统会延迟一段时间自动保存数据。我最初使用了闭包来实现一个防抖函数，以确保连续操作不会触发多次保存动作。
```javascript
function debounce(func, wait) {
  let timeout;
  return function() {
    clearTimeout(timeout);
    timeout = setTimeout(func, wait);
  };
}
const saveData = debounce(() => {
  console.log('Data saved');
}, 2000);
```
这段代码看似没有问题，但在实际使用中，我们发现即使用户已经离开了当前页面，由于闭包中的`setTimeout`，保存数据的操作仍然会在后台执行。这不仅影响了性能，还可能导致用户数据在不适当的时间被修改。

### 3. 解释你是如何解决这个问题的
在你的回答中，展示你的问题解决能力是非常重要的。描述你是如何识别问题、分析问题并最终解决问题的。
#### 示例续答：
为了解决这个问题，我首先确认了闭包中`setTimeout`的调用是问题的根源。我修改了代码，增加了一个标志位来检查用户是否仍在当前页面。如果用户已经离开，我会清除定时器，阻止数据保存操作的执行。
```javascript
function debounce(func, wait) {
  let timeout;
  let isPageActive = true;
  window.onblur = () => isPageActive = false;
  window.onfocus = () => isPageActive = true;
  return function() {
    clearTimeout(timeout);
    if (isPageActive) {
      timeout = setTimeout(func, wait);
    }
  };
}
const saveData = debounce(() => {
  console.log('Data saved');
}, 2000);
```

### 4. 概括闭包的优点和注意事项
最后，可以总结一下闭包的优点以及在使用时需要注意的事项，显示出你对技术的全面理解。
#### 示例总结：
闭包是一个非常强大的特性，它允许我们访问函数外部的变量，帮助我们编写更加模块化和可重用的代码。
然而，使用闭包时我们需要特别注意内存使用和性能问题，例如避免不必要的内存占用和确保及时清理不再需要的资源。正确使用闭包可以极大地提高我们代码的质量和效率。
通过这样的结构来回答，你不仅展示了对闭包的深入理解，还展示了你解决实际问题的能力，这对面试是非常有帮助的。


## Vue中有闭包陷阱吗？如何避免？
在Vue.js中，闭包陷阱主要出现在组件的方法、计算属性或者观察者中，特别是当这些功能涉及到外部变量时。
闭包陷阱可能导致意外的行为，尤其是在涉及异步操作或外部作用域变量时。这些陷阱通常源于对JavaScript闭包行为的误解。

### Vue中闭包陷阱的常见场景：
1. **异步操作中的闭包**：在Vue组件的方法中使用例如setTimeout、setInterval或者异步请求时，如果引用了循环中的变量，可能不会按预期工作，因为闭包会捕获变量的最后状态。
2. **循环引用闭包**：在使用v-for创建列表并且为每个列表项绑定事件处理器时，如果处理器是一个闭包并且依赖循环变量，可能会导致每个处理器实际上都绑定了循环的最后一个元素。

### 如何避免这些陷阱：
1. **使用立即执行函数（IIFE）**：在循环中创建闭包时，可以使用立即执行函数来捕获每次迭代的正确值。
   ```javascript
   for (var i = 0; i < 5; i++) {
     (function(j) {
       setTimeout(function() {
         console.log(j);
       }, 1000 * j);
     })(i);
   }
   ```
2. **使用let代替var**：在循环中使用`let`声明变量，因为`let`具有块级作用域，可以保证每次迭代的变量独立。
   ```javascript
   for (let i = 0; i < 5; i++) {
     setTimeout(function() {
       console.log(i);
     }, 1000 * i);
   }
   ```
3. **使用函数工厂**：创建一个返回函数的工厂函数，这样可以为每个闭包生成独立的作用域。
   ```javascript
   function createHandler(index) {
     return function() {
       console.log("Item index: " + index);
     };
   }

   for (var i = 0; i < 5; i++) {
     document.getElementById('item' + i).onclick = createHandler(i);
   }
   ```
4. **在Vue中正确使用箭头函数和普通函数**：箭头函数不绑定自己的`this`，而是继承父作用域中的`this`。这在Vue的生命周期钩子或方法中使用时要小心，以确保`this`指向预期的Vue实例。

通过理解闭包和作用域的工作原理，可以有效避免在Vue.js以及其他JavaScript环境中出现闭包相关的问题。确保在编码时考虑到闭包对变量作用域的影响，特别是在处理异步代码或事件处理器时。


## 详细说说如何在Vue中正确使用箭头函数和普通函数，用来避免闭包陷阱？
在Vue.js中，正确使用箭头函数和普通函数是管理闭包、`this` 绑定和作用域的关键。理解它们的行为差异有助于避免常见的闭包陷阱和其他相关错误。

### 箭头函数 vs 普通函数
**箭头函数**：
- 不拥有自己的 `this`、`arguments`、`super` 或 `new.target`。
- 继承其封闭作用域的 `this` 值，这通常指向定义它的上下文。
- 适合用在不需要独立 `this` 上下文的场合，如纯函数、简单的回调。

**普通函数**：
- 拥有自己的 `this` 值，根据如何调用函数，`this` 值可以不同。
- 可以作为构造函数使用，使用 `new` 关键字创建对象实例。
- 适合用在需要独立的 `this` 上下文的场合，如对象方法、构造函数。

### 在Vue中使用箭头函数和普通函数
#### 1. **生命周期钩子和方法**：
在Vue组件的生命周期钩子和方法中，通常应使用普通函数而不是箭头函数。因为生命周期钩子和方法中的 `this` 应指向Vue实例，以便访问组件的数据、计算属性和方法。
```javascript
export default {
  data() {
    return {
      name: 'Vue.js'
    };
  },
  created: function() {
    console.log(this.name);  // 正确：this 指向 Vue 实例
  },
  mounted() {
    this.fetchData();
  },
  methods: {
    fetchData: function() {
      console.log('Fetching data...');
    }
  }
}
```
使用箭头函数可能会导致 `this` 指向错误，因为箭头函数会捕获定义时的上下文的 `this` 值。
#### 2. **事件处理器**：
在事件处理器中，通常应使用普通函数。这是因为Vue自动绑定事件处理器中的 `this` 到当前组件实例。
```html
<template>
  <button @click="handleClick">Click me</button>
</template>

<script>
export default {
  methods: {
    handleClick: function() {
      this.doSomething();
    },
    doSomething: function() {
      console.log('Done something');
    }
  }
}
</script>
```
#### 3. **在回调函数中使用箭头函数**：
当你需要在Vue方法中使用回调函数，特别是在涉及异步操作时（如 `setTimeout`、`fetch` 等），使用箭头函数可以帮助你保持 `this` 的正确指向。
```javascript
export default {
  methods: {
    fetchData: function() {
      setTimeout(() => {
        console.log(this.name);  // 正确：箭头函数使得 this 仍然指向 Vue 实例
      }, 1000);
    }
  }
}
```

### 总结
在Vue中，通常应避免在生命周期钩子和方法中使用箭头函数，以保证 `this` 正确指向Vue实例。在需要维持上下文的回调函数中使用箭头函数可以避免闭包陷阱。理解这些差异和适当的使用场合是避免错误和提高代码质量的关键。


## React中有闭包陷阱吗？如何避免？
在React中，闭包陷阱同样存在，尤其是在使用函数组件和Hooks时。由于React的函数组件每次渲染都会重新执行，闭包中捕获的变量可能不是最新的状态，这可能导致意外的行为和bug。

### React中常见的闭包陷阱
1. **在事件处理器或异步函数中使用旧的状态或props**：
   由于闭包的特性，一个函数可能捕获了旧的状态或props值，而不是最新的。这在异步操作或设置事件处理器时尤其常见。
2. **在useEffect中使用过时的state或props**：
   当依赖项未正确指定时，useEffect中的闭包可能会捕获过时的state或props，导致逻辑错误。

### 如何避免React中的闭包陷阱
#### 1. **使用最新的state和props**
- 使用函数形式的setState来确保总是使用最新的state值。
 ```javascript
 const [count, setCount] = useState(0);
 const handleIncrement = () => {
   setCount(prevCount => prevCount + 1);
 };
 ```
- 使用useRef来保持对最新值的引用。
 ```javascript
 const latestCount = useRef(count);
 useEffect(() => {
   latestCount.current = count;
 });
 const handleSomething = () => {
   setTimeout(() => {
	 console.log(latestCount.current);  // 总是日志最新的count
   }, 3000);
 };
 ```
#### 2. **在useEffect中正确设置依赖项**
- 确保useEffect的依赖项数组中包括了所有外部变量和props，这样可以保证在依赖更新时重新运行effect。
 ```javascript
 useEffect(() => {
   const id = setInterval(() => {
	 console.log(count);
   }, 1000);
   return () => clearInterval(id);
 }, [count]);  // 依赖项数组包括count
 ```
#### 3. **使用useCallback**
- 使用useCallback来缓存函数，避免在每次渲染时都创建新的函数实例。确保依赖项列表正确无误。
 ```javascript
 const memoizedCallback = useCallback(() => {
   doSomething(a, b);
 }, [a, b]);  // a和b改变时，函数会更新
 ```
#### 4. **避免在循环或条件语句中定义Hooks**
- React Hooks应在组件的最顶层使用，不应在循环、条件或嵌套函数中调用。

通过上述方法，可以有效避免React中的闭包陷阱，确保应用的性能和正确性。理解每个Hook的工作原理和生命周期是关键，这有助于开发更稳定和高效的React应用。


## React开发过程中遇到的闭包陷阱有哪些？可否举例说明下？
在 React 中使用闭包时，开发者经常会遇到一些陷阱，尤其是在函数组件和 Hooks 的上下文中。
闭包在 JavaScript 中是一个非常强大的特性，但如果不正确使用，可能会导致意外的行为，特别是在涉及到状态和副作用时。
以下是一些常见的闭包陷阱以及如何避免它们：

### 1. 旧状态或道具的引用
在 React 的函数组件中，每次组件重新渲染时，函数本身及其内部的所有变量都会被重新创建。
因此，任何闭包（例如事件处理器或 useEffect 的回调函数）都可能捕获到这些变量的“旧”版本。
**示例问题**：
```javascript
function Counter() {
    const [count, setCount] = useState(0);

    useEffect(() => {
        const interval = setInterval(() => {
            console.log(count); // 总是打印初始值 0
        }, 1000);

        return () => clearInterval(interval);
    }, []); // 空依赖数组意味着这个 effect 只会在挂载时运行一次

    return (
        <div>
            <p>{count}</p>
            <button onClick={() => setCount(count + 1)}>Increment</button>
        </div>
    );
}
```
**解决方案**：
- 使用 `setCount` 的函数形式来获取最新的状态。
- 将状态或道具作为依赖添加到 useEffect 或 useCallback 的依赖数组中。

### 2. 事件处理器中的闭包陷阱
如果在事件处理器中使用了闭包，可能会捕获到事件添加时的道具和状态的快照。
**示例问题**：
```javascript
function MyComponent({ onSomething }) {
    const [value, setValue] = useState("initial");

    useEffect(() => {
        const handler = () => {
            console.log(value); // 总是打印 "initial"
        };
        window.addEventListener("resize", handler);
        return () => window.removeEventListener("resize", handler);
    }, []); // 空依赖数组

    return <button onClick={() => setValue("updated")}>Update</button>;
}
```
**解决方案**：
- 更新依赖数组，包括所有应该触发更新的变量。
- 使用 `useRef` 来持久化最新的值。

### 3. 与 `useCallback` 和 `useMemo` 的交互
使用 `useCallback` 和 `useMemo` 时，如果依赖项没有正确指定，可能会导致使用旧的道具或状态。
**示例问题**：
```javascript
const memoizedCallback = useCallback(() => {
    doSomething(a, b);
}, [a]); // 如果 b 发生变化，这个回调不会更新
```
**解决方案**：
- 确保所有相关依赖都被包括在依赖数组中。

### 总结
理解闭包和它们如何工作是避免这些陷阱的关键。在 React 中，你需要确保你的闭包总是能够访问到最新的状态、道具或其他依赖项。这通常意味着需要正确地使用依赖数组，或者考虑使用其他的钩子如 `useRef` 来维持对最新值的引用。

