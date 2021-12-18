# Node.js GM spread()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-spread-function/](https://www.geeksforgeeks.org/node-js-gm-spread-function/)

**spread()** 函数是 GraphicsMagick 库中的一个内置函数，用于随机替换图像像素。该函数在成功时返回真值。

**语法:**

```js
spread(amount)
```

**参数:**该函数接受单个参数**量**，用于指定图像像素应位移的值。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke spread function
.spread(3)

// Process and Write the image
.write("spread1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/0607f460334beab8a0214e2ad61713d8.png)

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

// Invoke spread function
.spread(45)

// Process and Write the image
.write("spread2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/c2937871179794e7b0553c9d37408898.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-spread](http://www.graphicsmagick.org/GraphicsMagick.html#details-spread)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)