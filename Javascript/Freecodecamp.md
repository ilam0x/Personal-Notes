# 变量

```javascript
var a=9;
//字符串（String）的值是不可变的（immutable）
str[0]='a'//err
//倒数第几个字符-几，所以第一位设置为0
 push() 函数：将数据添加到数组末尾，接受一个或多个参数
 .pop() 函数：移除一个数组末尾的值
 .shift()：移除一个数组开头的值
 .unshift() ：添加数组在开头

```

# 函数

```javascript
函数调用中充当传入函数的输入占位符（也叫形参）
function func(形参1，形参2){}
## 全局作用域和函数
在函数外定义的变量具有 **全局** 作用域。
具有相同名称的局部变量 和全局变量。局部变量将会优先于全局变量。

函数也可以返回 undefined

队列（queue）是一个抽象的数据结构
function nextInLine(arr, item) {
  arr.push(item);
  return arr.shift();
}    //把数字添加到数组的结尾，然后移出数组的第一个元素。最后 nextInLine 函数应该返回被删除的元素。
    
相等运算符
相对相等操作符 1 == '1' true

当且仅当运算符的左边和右边都是 true，逻辑与运算符（&&）才会返回 true。

在 switch 语句中添加默认选项
在 switch 语句中，你可能无法用 case 枚举出所有可能的值。 相反，你可以添加 default 语句，它会在找不到相匹配的 case 语句之后执行。 你可以把它看作是 if/else 链中最后的那个 else 语句。
function switchOfStuff(val) {
  var answer = "";
  // 用一个 Switch 语句来替代多个 if else 语句
  switch (val){
    case "a":
    answer="apple";
    break;
    case 'b':
    answer='bird';
    break;
    case 'c':
    case 'd'; //不同条件相同结果
    answer='cat';
    break;
    default:
    answer='stuff';
    break;
  }
    
function isLess(a, b) {
// 有比较操作符都会返回 boolean：要么是 true 要么是 false
return a<b;
}
```

# 对象

和 `arrays` 类似，区别在于数组使用索引来访问和修改数据，而对象中的数据是通过 `properties` 访问的，且所有的属性都被纯属为字符串。

` var lookup = {}`

访问属性 `obj.prop1 || obj[有空格的属性 ] || 变量访问（应用：属性名动态）`

更新、添加属性 `obj.prop1 = "new value"`

删除`delete obj.prop`;

查找 用形参当属性`result = obj.`形参

测试对象的属性 `obj.hasOwnProperties(属性名)`返回true

**操作复杂对象** JavaScript 对象是一种灵活的数据结构。 它可以储存字符串（strings）、数字（numbers）、布尔值（booleans）、数组（arrays）、函数（functions）和对象（objects）以及这些值的任意组合。

-  [JavaScript Object Notation](http://www.json.org/) 简称 `JSON` 是可以用于存储数据的数据交换格式。数组中有多个 JSON 对象的时候，对象与对象之间要用逗号隔开。

  ```javascript
  var jsonObj = [
      {
      "a":1,
      "b":{"e":4,}
  	},
      {
          "c":"3",
          "d":[a,b],
      }
  ]
  ```

  

- 点号表示法和方括号表示法来访问对象的嵌套属性。

  `jsonObj[b][e];`

# 循环

**while 循环** () {循环部分} #忘记括弧

`for (a; b; c)`，其中 `a` 为初始化语句，`b` 是循环条件语句，`c` 是终止循环条件表达式initialization、condition 和 final-expression。初始化语句只会在执行循环开始之前执行一次。 它通常用于定义和设置你的循环变量。

**使用 For 循环遍历数组**

Array = [1,2,3];

for (var i = 0; i<Array.length; i++){} //%for括号内定义var,分号

**循环嵌套**

二维数组，可以使用相同的逻辑，先遍历外面的数组，再遍历里面的子数组

```javascript
function multiplyAll(arr) {
  var product = 1;
  // 只修改这一行下面的代码
    for (var i=0;i<arr.length;i++){ //%分号
      for (var j=0; j<arr[i].length;j++){
      product *= arr[i][j];
      }
    }
  // 只修改这一行上面的代码
  return product;
```

**do...while 循环**

`do...while` 循环确保循环内的代码至少运行一次

## **使用递归代替循环**

` if {不满足base case} else return 函数自身 运算方法 和对应的n-1`元素

```javascript
  function multiply(arr, n) {
    if (n <= 0) {
      return 1;
    } else {
      return multiply(arr, n - 1) * arr[n - 1];
    }
  }
```

有个列表里有多个json对象，需要遍历找对应属性的值，没有姓名或者prop属性的就return"No such contact

<img src="file:///D:\Program Files\Tencent Files\2567794883\Image\Group2\W}\A0\W}A0C2UN[VA8EL]QH6O@0[A.png" alt="img" style="zoom: 67%;" />

<img src="C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210821170451282.png" alt="image-20210821170451282" style="zoom:67%;" />

#if只执行一次，

栈溢出，调用函数放在栈里，返回时取出，调用超过栈内存的函数都不返回就叫溢出

**使用 JavaScript 生成随机数**

```javascript
Math.random()` 生成一个在`0`（包括 0）到 `1`（不包括 1）之间的随机小数。 因此 `Math.random()` 可能返回 `0`，但绝不会返回 `1
return Math.floor(Math.random()*10);

返回一个在 myMin（包括 myMin）和 myMax（包括 myMax）之间的随机整数
return Math.floor(Math.random()* (myMax-myMin+1))+myMin;
```

**parseInt 函数**

- 函数解析一个字符串返回一个整数 `parseInt("007"); output: 7`

- 传入一个基数 `parseInt(string, radix表示当前进制);`

**使用三元运算符 ternary operator**

`return a==b ? "=" :"!=";`

- 替代if`，`else if` 和 `else，

- ```javascript
  function checkSign(num) {
    return (num > 0) ? "Positive" 
    : (num <0) ? "Negative"
  //#  : (num = 0)? "zero"; 最后一个相当于else不加条件
  }
  
  checkSign(10);
  ```

**使用递归创建一个倒计时**

```javascript
用 n = 5 调用函数应该返回数组 [5, 4, 3, 2, 1]
function countdown(n){
  if (n < 1){
    return [];
  } else {
    const arr = countdown(n-1); // 递归调用返回之后，才调用 push
    arr.unshift(n);
    return arr;
  }
 
}
```

**使用递归来创建一个数字序列**

已经定义好了 `rangeOfNumbers` 函数，包含两个参数。 函数应该返回一个连续数字数组，`startNum` 参数开始 `endNum` 参数截止。 开始的数字小于或等于截止数字。 函数必需递归调用自身，不能使用任意形式的循环。 要考虑到 `startNum` 和 `endNum` 相同的情况。

```javascript
function rangeOfNumbers(startNum, endNum) {
 	if (startNum > endNum){
		return [];
	} else {
	if (startNum == endNum){
		return [startNum];
	} else {
	
    const arr = rangeOfNumbers(startNum + 1, endNum);
    arr.unshift(startNum);  
    return arr;
}}}
```

# ES6

**比较 var 和 let 关键字的作用域**

如果你创建一个函数，将它存储起来，稍后在使用 `i` 变量的 `for` 循环中使用。这么做可能会出现问题。 这是因为存储的函数会总是指向更新后的全局 `i` 变量的值。

```javascript
var printNumTwo;
for (var i = 0; i < 3; i++) { //#i is declared globally. 
  if (i === 2) {
    printNumTwo = function() {
      return i;
    };
  }
}
console.log(printNumTwo());//这里控制台将显示值 3。

function checkScope() {
  let i = 'function scope';
  if (true) {
    i = 'block scope'; //statement
    console.log('Block scope i is: ', i);
  }
  console.log('Function scope i is: ', i);
  return i;
}
```

**`const` are read-only**

重命名用 const 声明的变量以符合常见做法，这意味着常量应该全部大写。

```javascript
  const SENTENCE = str + " is cool!";
  for (let i = 0; i < str.length; i+=2) {
    console.log(SENTENCE);
  }
应用1：
objects (including arrays and functions) assigned to a variable using const are still mutable. Using the const declaration only prevents reassignment of the variable identifier.

Object.freeze //Prevent Object Mutation

const magic =()=> new Date(); //Use Arrow Functions to Write Concise Anonymous Functions

const myConcat = (arr1=1, arr2)=> arr1.concat(arr2);//Parameters and default value
```

**rest 操作符**

`const sum = (...args) => {return args.reduce((a, b) => a + b, 0);`}`

**spread 运算符展开数组项**

下面的 ES5 代码使用了 `apply()` 来计算数组的最大值：

```js
var arr = [6, 89, 3, 45];
var maximus = Math.max.apply(null, arr);
```

`...arr` 返回一个解压的数组，只能够在函数的参数中或者数组中使用

```js
const arr = [6, 89, 3, 45];
const maximus = Math.max(...arr);
//复制数组
arr=[1,2,3];
arr2=[...arr];
```

## **解构赋值**

**来获取对象的值 Destructuring Assignment to Extract Values from Objects**

```js
//ES5
const user = { name: 'John Doe', age: 34 };
const name = user.name;
const age = user.age;
//ES6
const {name,age} = user;
```

**Assign Variables from Objects** 从对象分配变量

```js
const user = { name: 'John Doe', age: 34 };

const { name: userName, age: userAge } = user;
```

**Assign Variables from Nested Objects** 从嵌套对象分配变量

```javascript
const LOCAL_FORECAST = {
  yesterday: { low: 61, high: 75 },
  today: { low: 64, high: 77 },
  tomorrow: { low: 68, high: 80 }
};

// {属性：{属性：变量}}
  
const {today:{low:lowToday, high:highToday}} = LOCAL_FORECAST;
```

**Assign Variables from Arrays** 从数组分配变量

使用数组解构来交换变量 `a` 与 `b` 的值，使 `a` 接收 `b` 的值，而 `b` 接收 `a` 的值。

let a,b;

[a,b]=[b,a];

使用解构赋值以及 rest 操作符来进行和 `Array.prototype.slice()` 相同的操作，使 `arr` 是原数组 `source` 除开前两个元素的子数组。

```javascript
const source = [1,2,3,4,5,6,7,8,9,10];
function removeFirstTwo(list) {
  const [,,...arr] = list; // 解构数组 
  return arr;
}
const arr = removeFirstTwo(source);
```

**将对象作为函数的参数传递**

你可以在函数的参数里直接解构对象

```js
const profileUpdate = (profileData) => {
  const { name, age, nationality, location } = profileData;
}
const profileUpdate = ({ name, age, nationality, location }) => {
}

对 half 的参数进行解构赋值，仅将 max 与 min 的值传进函数。
const half = ({max,min}) => {(max+min)/2.0};
//# half(stats) = undefined
const half = ({max,min}) => (max+min)/2.0;
```

## **模板字面量创建字符串**

模板字符串可以使用多行字符串和字符串插值功能。



```js
 for (let element of arr) //%遍历
      failure.push(`<li class="text-warning">${element}</li>`);
    } 

  for (var i=0;i<arr.length;i++){
    const failureItems = [];
      failureItems.push(`<li class="text-warning">${arr}</li>`); %输出全部数组
  }
//%ReferenceError: failureItems is not defined

const failureItems = [];
  for (var i=0;i<arr.length;i++){
      failureItems.push(`<li class="text-warning">${arr[i]}</li>`);
  }
```

**使用简单字段编写简洁的对象字面量声明**

```javascript
效果相同
const getMousePosition = (x, y) => ({
  x: x,
  y: y
});
const getMousePosition = (x, y) => ({ x, y });

请使用简单属性对象的语法来创建并返回一个具有 name、age 和 gender 属性的对象。
const createPerson = (name, age, gender) => {
  return {name,age,gender};
};
```

**用 ES6 编写简洁的函数声明**

在对象中定义一个函数时，用 ES6 的语法在对象中定义函数的时候，可以删除 `function` 关键词和冒号

```javascript
效果相同
const person = {
  name: "Taylor",
  sayHello: function() {
    return `Hello! My name is ${this.name}.`;
  }
};
const person = {
  name: "Taylor",
  sayHello() {
    return `Hello! My name is ${this.name}.`;
  }
};
```

## **使用 class 语法定义构造函数**

%Class创建包括构造函数的对象

在 ES5 里面，我们通常会定义一个构造函数 `constructor` this，然后使用 `new` 关键字来实例化一个对象

```javascript
var SpaceShuttle = function(targetPlanet){
  this.targetPlanet = targetPlanet;
}
var zeus = new SpaceShuttle('Jupiter');

//class 语法只是简单地替换了构造函数 constructor 的写法：
class SpaceShuttle {
  constructor(targetPlanet) {
    this.targetPlanet = targetPlanet;
  }
}
const zeus = new SpaceShuttle('Jupiter');

//使用 class 关键词，写一个 constructor 来创建 Vegetable class。Vegetable 这个 class 可以创建 vegetable 对象，这个对象拥有一个在 constructor 中赋值的 name 属性。

//constructor 方法是一个特殊方法，用于创建和初始化 class 创建的对象。
class Vegetable { //%大小写
  constructor(name){
    this.name = name;
  }
}
```

**使用 getter 和 setter 来控制对象的访问**

从对象中获得一个值，也可以给对象的属性赋值。

使用 `class` 关键字创建一个 `Thermostat` class。 `constructor` 接收一个华氏温度。

在 class 中，创建一个 `getter` 来获取摄氏温度和一个 `setter` 来设置温度值。

```javascript
class Thermostat {
  constructor(hua) {
    this._she = 5/9 * (hua - 32); 
    //通常会在私有变量前添加下划线（_）。
    //getter让对象返回一个私有变量（只能在类内部访问的变量），而不需要直接去访问私有变量.
  }
  get temperature(){
    return this._she;
  }
    //Setter 函数的作用是可以基于传进的参数来修改对象中私有变量。 这些修改可以是计算，或者是直接替换之前的值。
  set temperature(newTemp){
    this._she = newTemp;
  }
}
// 只修改这一行上面的代码

const thermos = new Thermostat(76); // 设置为华氏刻度
let temp = thermos.temperature; // 24.44 摄氏度
thermos.temperature = 26;
temp = thermos.temperature; 
```

**创建一个模块脚本**

```html
<script type="module" src="filename.js"> 
// `module` 类型的脚本可以使用 `import` 和 `export` 特性。
</script>
```

**用 export 来重用代码块**

```js
export const add = (x, y) => {return x + y;}
或
const add = (x, y) => {return x + y;}
export { add }; //对象
export { add, subtract };//到处多个函数

```

**通过 import 复用 JavaScript 代码**

```js
import { add } from './math_functions.js';
```

**用 \* 从文件中命名导入所有内容**

```js
import * as myMathModule from "./math_functions.js";

```

**用 export default 创建一个默认导出**

只有一个值需要导出的时候，通常会使用这种语法。 它也常常用于给文件或者模块创建返回值。

`export default` 用于为模块或文件声明一个返回值，在每个文件或者模块中应当只默认导出一个值。 此外，你不能将 `export default` 与 `var`、`let` 或 `const` 同时使用。

```javascript
export default function subtract(x, y) {return x - y;}
```

**导入一个默认的导出**

```js
import subtract from "./math_functions.js";
subtract(7,4);
```

**创建一个 JavaScript Promise**

Promise 是异步编程的一种解决方案 - 它在未来的某时会生成一个值。 任务完成，分执行成功和执行失败两种情况。 `Promise` 是构造器函数，需要通过 `new` 关键字来创建。 构造器参数是一个函数，该函数有两个参数 - `resolve` 和 `reject`。 通过它们来判断 promise 的执行结果。 用法如下：

```js
const myPromise = new Promise((resolve, reject) => {});

//创建一个名为 `makeServerRequest` 的 promise。 给构造器函数传入 `resolve` 和 `reject` 两个参数。
const makeServerRequest = new Promise((resolve,reject)) =>{}); //% `Promise` 是构造器函数


```

------

**通过 resolve 和 reject 完成 Promise**

Promise 有三个状态：`pending`、`fulfilled` 和 `rejected`

使 promise 可以处理成功和失败情况。 如果 `responseFromServer` 是 `true`，调用 `resolve` 方法使 promise 成功。 给 `resolve` 传递值为 `We got the data` 的字符串。 如果 `responseFromServer` 是 `false`， 使用 `reject` 方法并传入值为 `Data not received` 的字符串。

```js
const makeServerRequest = new Promise((resolve, reject) => {
  // responseFromServer 表示从服务器获得一个响应 True or False
  let responseFromServer;

  if(responseFromServer) {
    resolve("We got the data");
  } else {  
    reject("Data not received")
  }
});
```

**用 then 处理 Promise 完成的情况**

当 promise 完成 `resolve` 时会触发 `then` 方法。

 用 `result` 做为回调函数的参数并将 `result` 打印在控制台。

应该打印 `result` 到控制台。

```js
myPromise.then(result => {}); //`then` 方法应该有一个回调函数，回调函数参数为 `result`。
makeServerRequest.then(result=> {console.log(result)}); //等待promise完成resolve后执行
```

**使用 catch 处理 Promise 失败的情况**

```js
makeServerRequest.then(result => {
  console.log(result);
});
makeServerRequest.catch(error => {
  console.log(error);
});
```

# Regular Expression

## 正则

**使用test方法测试正则**

`Regex.test(Str)`// 匹配返回true

大小写敏感，`/i`忽略大小写

**匹配文字字符串**

literal patterns (`/literal/`)

**提取匹配项**

` result = Str.match(Regex)` 方法来提取找到的实际匹配项。

`全局匹配 /g` `通配符wildcard character .`

方括号（`[` 和 `]`）之间来定义一组需要匹配的字符串

> you want to match `bag`, `big`, and `bug` but not `bog`. You can create the regex `/b[aiu]g/` to do this. The `[aiu]` is the character class that will only match the characters `a`, `i`, or `u`.

% /[a-z0-5]/ 方括号，ig在斜杠外

多次匹配

```
/a+/g` would find one match in `abc` and return `["a"]
If it were instead checking the string abab, it would find two matches and return ["a", "a"]
```

匹配出现零次或多次的字符

`/Aa*/ = Aaaaaaaaa`

惰性匹配

```js
let text = "<h1>Winter is coming</h1>";
let myRegex = /<h*?[0-9]>/; // 范围要方括号
let result = text.match(myRegex);
```

**在狩猎中找到一个或多个罪犯** `/C+/`

**限制可能的用户名**

用户名规则。

1. 用户名只能是数字字母字符。
2. 用户名中的数字必须在最后。 数字可以有零个或多个。 用户名不能以数字开头。
3. 用户名字母可以是小写字母和大写字母。
4. 用户名长度必须至少为两个字符。 两位用户名只能使用字母。

`let userCheck = /^[a-z]([0-9]{2,}|[a-z]+[0-9]*)$/i;`

**指定匹配的上限和下限** {3,4}

**Lookaheads** `(?=...)`

**重用**

在 `reRegex` 中使用捕获组来匹配一个只由相同的数字重复三次组成的由空格分隔字符串。

```js
let repeatNum = "42 42 42";
let reRegex = /^(\d+) \1 \1 \1$/; //标记起始和结束
```

> 搜索和替换
>
> 你还可以使用美元符号（`$`）访问替换字符串中的捕获组。
>
> ```js
> let str = "one two three";
> let fixRegex = /(\w+) (\w+) (\w+)/; // 修改这一行
> let replaceText = '$3 $2 $1'; // 修改这一行
> let result = str.replace(fixRegex, replaceText);
> ```

去除空格

等效`String.prototype.trim()`

```js
let hello = "   Hello, World!  ";
let wsRegex = /^(\s+)(.+[^\s])(\s+)$/;
let result = hello.replace(wsRegex, '$2');
```

# Debugging

`console.log()`

`console.clear()`

`typeof ""`

JavaScript recognizes six primitive (immutable) data types: `Boolean`, `Null`, `Undefined`, `Number`, `String`, and `Symbol` (new with ES6) and one type for mutable items: `Object`. Note that in JavaScript, arrays are technically a type of object.

## 常见错误

1. 找拼写错误
2. 未关闭的括号（列表，函数...）
3. 引号内使用相同的引号
4. 等号和赋值
5. 无参数的函数调用没带（）
6. 参数调用顺序，
7. 循环条件里：索引错误导致错误关闭Off by one errors (OBOE)，
8. 循环初始变量
9. 使用终止条件防止无限循环

# basic data structure

1. 定义 ` let arr = [1,a,true,'s',{}]`

2. 索引访问 `arr[1]`

3. 添加 `前：arr.unshift` `后：arr.push`

4. 删除 `前: arr.shift` `后：arr.pop()`

5. 切片 `arr.splice(2,2)`

   ```js
   const arr = [2, 4, 5, 1, 7, 5, 2, 1];
   // Only change code below this line
   arr.splice(0,1)+arr.splice(3)
   // Only change code above this line
   console.log(arr);
   ```

   添加 `splice(startIndex, amountTodelete,replacingValue)` //第二个参数是数量不是截止index

   复制 slice(起始，不包含的结束)

   **ES6 `spread operator` : [...arr];**

   ```js
   //添加列表 
   newArr = newArr.push([...arr]); //TypeError: newArr.push is not a function
   newArr.push([...arr]);//&直接改原来的列表
   
   //合并列表
   [1,2,3,...arr]
   ```

6. `indexOf()` 获取元素下标，不存在返回 -1

7. 列表循环遍历

   1. `every()` 检查每个数字是否符合条件

      - 不改变原始数组
      - 

   2. `forEach()`接受函数作为参数，只用于数列且每个元素执行一次，返回undefined

   3. `map()` 接受函数作为参数，并将每个元素映射的结果，返回新的列表

   4. ```js
      function filteredArray(arr, elem) {
        let newArr = [];
        for (let i = 0; i<arr.length; i++) {
          if (arr[i].indexOf(elem) < 0) {
            newArr.push(arr[i]); //&直接操作列表不赋值
          }
        }
        return newArr;
      }
      ```

8. 嵌套列表 ` ['unshift',['deep',['deeper',['deepest']]],false, 1, 2, 3, 'complex', 'nested'], `

9. 给JS对象添加键值对
   1. `obj.prop = 'value';`
   2. `obj['prop name'] = 'value';` //有空格的名称或者变量
   3. `obj.prop.prop.prop = value ` 、//修改嵌套对象的值
   4. ` delete obj.prop `  // 删除
   
10. 判断内有没有某种属性

    - `obj.hasOwnProperty('propName');`

    - `'propName' in obj`

    - 判断多个

      ```js
      function isEveryoneHere(userObj){
        let names = ['Alan','Jeff','Sarah','Ryan']
        if (names.every(user => userObj.hasOwnProperty(user))){
          return true
        } //报错
          
      function isEveryoneHere(userObj){
        return [
          'Alan',
          'Jeff',
          'Sarah',
          'Ryan'
        ].every(user => userObj.hasOwnProperty(user));
      }

11. 用for循环根据对象关键字

12. 根据输入的json判断属性种包含某种子属性的数量

    ```js
    function countOnline(usersObj) {
      // Only change code below this line
    let i=0;
    for (let names in usersObj){
      if (usersObj[names].online == true){
        i +=1;
      }
    }
    return i   // Only change code above this line
    }
    
    //input
    {
      Alan: {
        online: false
      }
    ```

13. `Object.keys()`  列出对象所有属性

# Basic algorithm Scripting

1. 逆向输出 reverse str

   ```js
   let arr = str.split(""); //将string内按字母拆成数组
   let r = arr.reverse().join("");//翻转，拼合
   return r;
   ```

2. Return the factorial of the provided integer阶乘

   ```js
   function factorialize(num) {
     let r = 1;
     for (let i=1;i <= num; i++){
      r = r * i;
     }
     return r;
   }
   
   function factorialize(num) {
     return num < 1 ? 1 : num * factorialize(num - 1);
   }
   
   factorialize(5);
   ```

3. 获取字符串中最长单词长度

   `.sort()` //&

   没有传参的情况下按照0-9排序，也就是

   > (10) [1, 10, 19, 2, 2, 2, 3, 4, 4, 4]

   ```js
   function findLongestWordLength(str) {
     let arr = str.split(' ');
     let arrNum = []
     for ( let i=0;i<arr.length;i++){
       arrNum.push(arr[i].length);  
     }
     arrNum.sort((a,b) => a-b);  
     return arrNum.pop();
   }
   
   function findLongestWordLength(str) {
     return str.split(' ').sort((a, b) => b.length - a.length)[0].length;
   }
   ```

4. **Return Largest Numbers in Arrays**

   ```js
   Math.max(data); //&Nah,需要换成下面的写法
   Math.max.apply(Math, data);
   //输出包含最大值的数组
   function largestOfFour(arr) {
     let arr2 = [...arr].flat(), max = Math.max.apply(Math,arr2)
     for (var i=0; i<arr.length;i++){
       if (arr[i].includes(max)){
         return arr[i];
       }
     }
   }
   
   //提取每个嵌套数组的最大值凑成新的数组
   function largestOfFour(arr) {
     let max = [];
     for (var i=0; i<arr.length;i++){
       max.push(Math.max.apply(Math,arr[i]))   
       }
     return max;
     }
   
   function largestOfFour(arr) {
     return arr.map(subArr => Math.max.apply(null, subArr));
   }
   ```

5. `.endsWith()` 等效

   `.substring(start,end*)`

   ```js
   function confirmEnding(str, target) {
     if (str.substring(str.length-target.length) == target){
     return true;
     }else{
       return false;
     }
   } // 只return布尔值的可以简写
   
    return str.substring(str.length - target.length) === target;
   ```

6. `.repeat()`

   ```js
   function repeatStringNumTimes(str, num) {
     if (num>0){
     return str + repeatStringNumTimes(str,num-1);}
   }else{
       return"";
   }
   repeatStringNumTimes("abc", 3);
   //"abcabcabcundefined"
   
   function repeatStringNumTimes(str, num) {
     if (num>0){
     return str + repeatStringNumTimes(str,num-1);
   } else {
     return "";
   }}
   ```

   

7. Truncate a string

   ```js
   function truncateString(str, num) {
     if (num >= str.length){
       return str;
     } else {
     return str.substring(0,num)+"...";
   }}
   
   truncateString("A-tisket a-tasket A green and yellow basket", "A-tisket a-tasket A green and yellow basket".length);
   ```

8. `.filter()` 根据filter的条件建立新的数组

9. **Finders Keepers**，找偶数

   ```js
   function findElement(arr, func) {     
     return arr.filter(func);
   }
   findElement([1, 2, 3, 4], num => num % 2 === 0);
   //[2,4]
   ```

   

10. 判断类型

    ```js
    function booWho(bool) {
      return typeof(bool) === "boolean";
    }
    
    booWho(null);
    ```

11. 首字母大写

    ```js
    function titleCase(str) {
      return str.split(" ").map(item => item.substring(0,1).toUpperCase()+ item.substring(1).toLowerCase()).join(" ");
    }
    
    titleCase("I'm a little tea pot");
    ```

12. Slice and splice

    ```js
    function frankenSplice(arr1, arr2, n) {
      let a =arr2.slice(0,n); //把2拆分成两段和1拼接
      let result = a.concat(arr1).concat(arr2.slice(n));
      return result;
    }
    frankenSplice([1, 2, 3], [4, 5, 6], 1);
    
    function frankenSplice(arr1, arr2, n) {
      // It's alive. It's alive!
      let result = arr2.slice();//将arr2作为基准变换，把1插入数组
      for (let i = 0; i < arr1.length; i++) {
        result.splice(n+i, 0, arr1[i]);
      }
      return result;
    }
    ```

13. Falsy Bouncer

    ```js
    arr.filter(Boolean);
    
    arr.filter(e=>e);
    ```

    

14. Where do I belong

    ```js
    function getIndexToIns(arr, num) {
      arr.push(num);
      arr.sort((a,b)=>a-b);
      return arr.indexOf(num);
    }
    getIndexToIns([40, 60], 50);
    
    function getIndexToIns(arr, num) {
      arr.sort((a,b)=>a-b)
      for (let i = 0; i < arr.length; i++) {
        if (arr[i] >= num) {
          return i;
        }}
      return arr.length
    }
    
    
    getIndexToIns([40, 60], 50);
    ```

15. 匹配两个数组，是否包含

    ```python
    function mutation(arr) {
      let a = arr[0].toLowerCase().split("");
    
      let b = arr[1].toLowerCase().split("");
      let r = b.map(item=>a.includes(item));
      if (r.includes(false)){
        return false;
      } else{
        return true;
      }
    }
    
    mutation(["hello", "hey"]);
    
    function mutation(arr) {
      let hash = Object.create(null);
    
      arr[0].toLowerCase().split('').forEach(c => hash[c] = true);
    
      return !arr[1].toLowerCase().split('').filter(c => !hash[c]).length;
    }
    
    mutation(["hello", "hey"]);
    ```

    

