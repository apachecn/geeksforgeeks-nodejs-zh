# Node.js GM 边框()功能

> 原文:[https://www.geeksforgeeks.org/node-js-gm-border-function/](https://www.geeksforgeeks.org/node-js-gm-border-function/)

**边框()**函数是 GraphicsMagick 库中的一个内置函数，用于用颜色边框包围图像。该函数在成功时返回真值。

**语法:**

```js
border( width, height )
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **宽度:**此参数用于指定图像周围边框的宽度。
*   **高度:**此参数用于指定图像周围边框的高度。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke border function with 10*40
.border(10, 40)

// Process and Write the image
.write("border1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/d13c4e17f1e425a1b2ca4cc37bb915b7.png)

**例 2:**

```js
// Include gm library
var gm = require('gm');

//Import the image
gm(600, 300, 'white')

// set the color for the stroke
.stroke("green", 3)

// Set the font 
.font("Helvetica.ttf", 60)

//Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Invoke border function with 62 * 32
.border(62, 32)

// Process and write the image 
.write("border2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/cc0b0a48d3cd6fe10f091b07e80a0a1e.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-border](http://www.graphicsmagick.org/GraphicsMagick.html#details-border)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)