# Node.js GM 高斯()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-gaussian-function/](https://www.geeksforgeeks.org/node-js-gm-gaussian-function/)

**高斯()**函数是 GraphicsMagick 库中的一个内置函数，用于通过高斯算子模糊图像。它使用半径和标准偏差值，称为西格玛。该函数在成功时返回真值。

**语法:**

```js
gaussian(radius, sigma)
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **半径:**保存图像半径应该模糊的半径。
*   **σ:**表示图像模糊的标准偏差(σ)。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke gaussian function with
// radius 12 and sigma as 3
.gaussian(12, 3)

// Process and Write the image
.write("gaussian1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/d27a872d745e1a419eb44a9214bbb11a.png)

**例 2:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm(600, 300, 'white')

// Set the color for the stroke
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

// Invoke gaussian function
.gaussian(8, 6)

// Process and Write the image
.write("gaussian2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/d0c6363651ca5418936018bc60e81b07.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-Gaussian](http://www.graphicsmagick.org/GraphicsMagick.html#details-gaussian)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)