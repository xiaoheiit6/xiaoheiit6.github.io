---
title: JavaScript学习——初识JavaScript
date: 2023/09/16  18:15:00
categories:
- [JavaScript]
tags:
- 前端
---

一次前端JS的学习记录。

<!-- more -->

## JavaScript介绍

*JavaScript* 最初被创建的目的是“使网页更生动”。

这种编程语言写出来的程序被称为 **脚本**。它们可以被直接写在网页的 HTML 中，在页面加载的时候自动执行。

脚本被以纯文本的形式提供和执行。它们不需要特殊的准备或编译即可运行。

↑来自[现代JavaScript](https://zh.javascript.info/intro)

## HelloWorld!

- 第一种方式：在html文件中直接写入JavaScript脚本

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
  </head>
  <body>
      <script>
      alert("Hello World!"); //弹出一个窗口，显示Hello World!
      console.log("Hello World!");//在控制台上打印Hello World!
      </script>
  </body>
  </html>
- 第二种方式：在与html文件同级目录下写js脚本，然后进行引用

  html文件：

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
  </head>
  <body>
      <script src = "Hello.js"></script>
  </body>
  </html>
  ```

  同级目录下的hello.js文件：

  ```javascript
  alert("Hello World!"); //弹出一个窗口，显示Hello World!
  console.log("Hello World!");//在控制台上打印Hello World!

## 变量

在JavaScript中，变量的声明非常简单，只需要使用`let`关键字即可。

下面的语句创建了一个变量,并用赋值运算符 = 为其添加数据：

```javascript
let s;
s = 123;
//同时可以用下面的语句来进行定义及赋值：
let a = 123;
```

**注意：声明两次变量会触发error**

```javascript
let message = "hello";
let message = "world"; //error: SyntaxError: 'message' has already been declared
```

因此，对于同一个变量应该只声明一次，之后不能再用`let`对其引用。

### 变量命名规则

JavaScript中，变量的命名有几个限制：

1. 变量名必须仅包含字母、数字、符号$和_。
2. 首字符必须是非数字。
3. 严格区分大小写
4. 变量名不能以数字开始
5. 连字符"-"不允许用于变量命名
6. 不允许使用保留字来命名

如果命名包含多个单词，我们一般使用驼峰式命名法(camelCase)。除了第一个单词，其他每个单词都以大写字母开头：`myVeryLongName`。 
## 常量

声明一个常数（不变）变量，可以使用 `const` 而非 `let`：

```js
const myAge = 18;
```

使用 `const` 声明的变量称为“常量”。它们不能被修改，如果你尝试修改就会发现报错。

### [大写形式的常数](https://zh.javascript.info/variables#da-xie-xing-shi-de-chang-shu)

一个普遍的做法是将常量用作别名，以便记住那些在执行之前就已知的难以记住的值。

使用大写字母和下划线来命名这些常量。

例如，让我们以所谓的“web”（十六进制）格式为颜色声明常量：

```javascript
const COLOR_RED = "#F00";
const COLOR_GREEN = "#0F0";
const COLOR_BLUE = "#00F";
const COLOR_ORANGE = "#FF7F00";

// ……当我们需要选择一个颜色
let color = COLOR_ORANGE;
alert(color); // #FF7F00
```

什么时候应该用大写命名，什么时候又该用常规命名呢？

作为一个“常数”，意味着值永远不变。但是有些常量在执行之前就已知了（比如红色的十六进制值），还有些在执行期间被“计算”出来，但初始赋值之后就不会改变。

例如：

```javascript
const pageLoadTime = /* 网页加载所需的时间 */;
```

`pageLoadTime` 的值在页面加载之前是未知的，所以采用常规命名。但是它仍然是个常量，因为赋值之后不会改变。

换句话说，大写命名的常量仅用作“硬编码（hard-coded）”值的别名。
