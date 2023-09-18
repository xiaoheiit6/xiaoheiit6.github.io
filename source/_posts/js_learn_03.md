---
title: JavaScript学习——JavaScript(交互)
date: 2023/09/18  18:00:00
categories:
- [JavaScript]
tags:
- 前端
---

第三次前端JS的学习记录。

<!-- more -->

## 交互：alert、prompt和confirm

我们使用浏览器作为演示环境，看几个与用户交互的函数：alert、prompt和confirm

### alert

这个函数将会显示一条信息，等待用户按下“OK”。

```javascript
alert("hello");
```

弹出的这个带有信息的小窗口叫做**模态窗（modal window）**。“modal”意味着用户不能点击页面其他部分进行交互，必须处理这个模态窗。

### prompt

```javascript
result = prompt(title,[default]);
```

浏览器会显示一个带有文本消息的模态窗口，还有 input 框和确定/取消按钮。

- `title`

  显示给用户的文本

- `default`

  **可选**的第二个参数，指定 input 框的初始值。

访问者可以在提示输入栏中输入一些内容，然后按“确定”键。然后我们在 `result` 中获取该文本。或者他们可以按取消键或按 Esc 键取消输入，然后我们得到 `null` 作为 `result`。

`prompt` 将返回用户在 `input` 框内输入的文本，如果用户取消了输入，则返回 `null`。

举个例子：

```javascript
let age = prompt('How old are you?', 100);

alert(`You are ${age} years old!`); // You are 100 years old!
```

**注意**：IE浏览器会默认给第二个参数传值，如果我们不提供默认输入值，IE会把undefined插入到prompt。

我们可以将第二个参数值为空：

```javascript
let test = prompt("Title","");
```

### confirm

语法：

```javascript
result = confirm(question);
```

`confirm`函数显示一个带有`question`以及带有确定和取消按钮的模态窗口。

点击确定返回值为`true`点击取消则返回`false`。

例如：

```javascript
let isBoss = confirm("Are you the boss?");

alert( isBoss ); // 如果“确定”按钮被按下，则显示 true
```

## 总结

- `alert`

  显示信息。

- `prompt`

  显示信息要求用户输入文本。点击确定返回文本，点击取消或按下 Esc 键返回 `null`。

- `confirm`

  显示信息等待用户点击确定或取消。点击确定返回 `true`，点击取消或按下 Esc 键返回 `false`。

**这些方法都是模态的：它们暂停脚本的执行，并且不允许用户与该页面的其余部分进行交互，直到窗口被解除。**

上述所有方法共有两个限制：

1. **模态窗口的确切位置由浏览器决定。通常在页面中心。**
2. **窗口的确切外观也取决于浏览器。我们不能修改它。**

这就是简单的代价。还有其他一些方式可以显示更漂亮的窗口，并与用户进行更丰富的交互，但如果“花里胡哨”不是非常重要，那使用本节讲的这些方法也挺好。