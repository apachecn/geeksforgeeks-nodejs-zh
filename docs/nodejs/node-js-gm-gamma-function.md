# Node.js GM gamma()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-gamma-function/](https://www.geeksforgeeks.org/node-js-gm-gamma-function/)

**伽马()**函数是 GraphicsMagick 库中的一个内置函数，用于伽马校正级别。该函数在成功时返回真值。
**语法:**

```js
gamma(red, green, blue)
```

**参数:**该功能接受红、绿、蓝三个参数，分别修正红、绿、蓝三种颜色的伽玛等级。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke gamma function
.gamma(1, 3.4, 6)

// Process and Write the image
.write("gamma1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/02e39c4e37a5ae02a1c9cb772587f44e.png)

**例 2:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm(600, 300, 'white')

// set the color for the stroke
.stroke("green", 3)

// Set the font 
.font("Helvetica.ttf", 60)

// Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Invoke borderColor() function
// and set border color to green
.borderColor("Green")

// Invoke border function
.border(62, 32)

// Invoke gamma function
.gamma(3, 45, 10)

// Process and Write the image
.write("gamma2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/bad59aa16168524a79fa67d5b48db880.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-gamma](http://www.graphicsmagick.org/GraphicsMagick.html#details-gamma)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)