---
title: JavaScript学习——JavaScript(数据类型)
date: 2023/09/16  19:40:00
categories:
- [JavaScript]
tags:
- 前端
---

第二次前端JS的学习记录。

<!-- more -->

## 数据类型

JavaScript中的值都具有特定的类型。

在JavaScript中有8种基本的数据类型（7种原始类型和1种引用类型）。

我们可以将任何类型的值存入变量。（JavaScript是一种 类型的编程语言）

前一刻的变量值是字符串，可能下一个就存储一个数字：

```javascript
// 没有错误
let message = "hello";
message = 123456;
```


### Number类型

```javascript
let n = 123;
n = 12.345;
```

*number* 类型代表整数和浮点数。

数字可以有很多操作，比如，乘法 `*`、除法 `/`、加法 `+`、减法 `-` 等等。

除了常规的数字，还包括所谓的“特殊数值（“special numeric values”）”也属于这种类型：`Infinity`、`-Infinity` 和 `NaN`。

- `Infinity` 代表数学概念中的 [无穷大](https://en.wikipedia.org/wiki/Infinity) ∞。是一个比任何数字都大的特殊值。

  我们可以通过除以 0 来得到它：

  ```javascript
  alert( 1 / 0 ); // Infinity
  ```

  或者在代码中直接使用它：

  ```javascript
  alert( Infinity ); // Infinity
  ```

- `NaN` 代表一个计算错误。它是一个不正确的或者一个未定义的数学操作所得到的结果，比如：

  ```javascript
  alert( "not a number" / 2 ); // NaN，这样的除法是错误的
  ```

  `NaN` 是粘性的。任何对 `NaN` 的进一步数学运算都会返回 `NaN`：

  ```javascript
  alert( NaN + 1 ); // NaN
  alert( 3 * NaN ); // NaN
  alert( "not a number" / 2 - 1 ); // NaN
  ```

  所以，如果在数学表达式中有一个 `NaN`，会被传播到最终结果（只有一个例外：`NaN ** 0` 结果为 `1`）。

### BigInt类型

在 JavaScript 中，“number” 类型无法安全地表示大于 `(253-1)`（即 `9007199254740991`），或小于 `-(253-1)` 的整数。

更准确的说，“number” 类型可以存储更大的整数（最多 `1.7976931348623157 * 10308`），但超出安全整数范围 `±(253-1)` 会出现精度问题，因为并非所有数字都适合固定的 64 位存储。因此，可能存储的是“近似值”。

例如，这两个数字（正好超出了安全整数范围）是相同的：

```javascript
console.log(9007199254740991 + 1); // 9007199254740992
console.log(9007199254740991 + 2); // 9007199254740992
```

也就是说，所有大于 `(253-1)` 的奇数都不能用 “number” 类型存储。

在大多数情况下，`±(253-1)` 范围就足够了，但有时候我们需要整个范围非常大的整数，例如用于密码学或微秒精度的时间戳。

`BigInt` 类型是最近被添加到 JavaScript 语言中的，用于表示任意长度的整数。

可以通过将 `n` 附加到整数字段的末尾来创建 `BigInt` 值。

```javascript
// 尾部的 "n" 表示这是一个 BigInt 类型
const bigInt = 1234567890123456789012345678901234567890n;
```

**注意：IE浏览器不支持BigInt**

### String类型

JavaScript中的字符串必须被包括在引号里。

```javascript
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed another ${str}`;
```

在 JavaScript 中，有三种包含字符串的方式。

1. 双引号：`"Hello"`.
2. 单引号：`'Hello'`.
3. 反引号：``Hello``.

双引号和单引号都是“简单”引用，在 JavaScript 中两者几乎没有什么差别。

反引号是**功能扩展**引号。它允许我们通过将变量或者表达式包装在`${...}`中，来将它们嵌入到字符串中。例如:

```javascript
let name = "John";

// 嵌入一个变量
alert( `Hello, ${name}!` ); // Hello, John!

// 嵌入一个表达式
alert( `the result is ${1 + 2}` ); // the result is 3
```

`${…}` 内的表达式会被计算，计算结果会成为字符串的一部分。可以在 `${…}` 内放置任何东西：诸如名为 `name` 的变量，或者诸如 `1 + 2` 的算数表达式，或者其他一些更复杂的。

**需要注意的是，这仅仅在反引号内有效，其他引号不允许这种嵌入。**

```javascript
alert( "the result is ${1 + 2}" ); // the result is ${1 + 2}（使用双引号则不会计算 ${…} 中的内容）

```

### Boolean 类型

boolean类型仅仅包含两个值：`true`和`false`。

布尔值可以作为比较结果：

```javascript
let isGreater = 4 > 1;

alert( isGreater);//输出true
```

### null值

特殊的null值并不属于上述的任何一种类型。

它自己是一个独立的类型，只包含`null`值:

```javascript
let age = null;
```

相比较于其他编程语言，JavaScript 中的 `null` 不是一个“对不存在的 `object` 的引用”或者 “null 指针”。

JavaScript 中的 `null` 仅仅是一个代表“无”、“空”或“值未知”的特殊值。

### undefined值

`undefined`值和上述`null`值一样自成类型。

`undefined`的含义是**未被赋值**。

```javascript
let age;

alert(age); // 弹出 "undefined"
```

### Object类型

`object` 类型是一个特殊的类型。

其他所有的数据类型都被称为“原始类型”，因为它们的值只包含一个单独的内容（字符串、数字或者其他）。相反，`object` 则用于储存数据集合和更复杂的实体。

`symbol` 类型用于创建对象的唯一标识符。我们在这里提到 `symbol` 类型是为了完整性，但我们要在学完 `object` 类型后再学习它。

### typeof运算符

`typeof` 运算符返回参数的类型。当我们想要分别处理不同类型值的时候，或者想快速进行数据类型检验时，非常有用。

对 `typeof x` 的调用会以字符串的形式返回数据类型：

```javascript
typeof undefined // "undefined"

typeof 0 // "number"

typeof 10n // "bigint"

typeof true // "boolean"

typeof "foo" // "string"

typeof Symbol("id") // "symbol"

typeof Math // "object"  (1)

typeof null // "object"  (2)

typeof alert // "function"  (3)
```

最后三行可能需要额外的说明：

1. `Math` 是一个提供数学运算的内建 `object`。我们会在 [数字类型](https://zh.javascript.info/number) 一节中学习它。此处仅作为一个 `object` 的示例。
2. `typeof null` 的结果为 `"object"`。这是官方承认的 `typeof` 的错误，这个问题来自于 JavaScript 语言的早期阶段，并为了兼容性而保留了下来。`null` 绝对不是一个 `object`。`null` 有自己的类型，它是一个特殊值。`typeof` 的行为在这里是错误的。
3. `typeof alert` 的结果是 `"function"`，因为 `alert` 在 JavaScript 语言中是一个函数。我们会在下一章学习函数，那时我们会了解到，在 JavaScript 语言中没有一个特别的 “function” 类型。函数隶属于 `object` 类型。但是 `typeof` 会对函数区分对待，并返回 `"function"`。这也是来自于 JavaScript 语言早期的问题。从技术上讲，这种行为是不正确的，但在实际编程中却非常方便。

**`typeof(x)` 语法**

你可能还会遇到另一种语法：`typeof(x)`。它与 `typeof x` 相同。

简单点说：`typeof` 是一个操作符，不是一个函数。这里的括号不是 `typeof` 的一部分。它是数学运算分组的括号。

通常，这样的括号里包含的是一个数学表达式，例如 `(2 + 2)`，但这里它只包含一个参数 `(x)`。从语法上讲，它们允许在 `typeof` 运算符和其参数之间不打空格，有些人喜欢这样的风格。

有些人更喜欢用 `typeof(x)`，尽管 `typeof x` 语法更为常见。

---

注意：本文的内容一部分是我自己总结的，一部分是直接copy[现代JavaScript教程](https://zh.javascript.info/)，本文仅作个人学习用途。如有侵权，请与我联系！