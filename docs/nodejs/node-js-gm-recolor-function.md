# node . js GM recorer()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-recolor-function/](https://www.geeksforgeeks.org/node-js-gm-recolor-function/)

**重新着色()函数**是 GraphicsMagick 库中的一个内置函数，用于将颜色转换矩阵应用于图像通道。该函数在成功时返回真值。

**语法:**

```js
recolor( matrix )
```

**参数:**该函数接受如上所述的单个参数，如下所述:

*   **矩阵:**该参数用于将值指定为矩阵的字符串，该字符串被解码为颜色变换矩阵。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke recolor function
.recolor('4 0 0, 0 6 0, 9 0 1')

// Process and Write the image
.write("recolor1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/135f03f42abc34674728c6ae33b4cff4.png)

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

// Invoke recolor function
.recolor('10 0 0, 2 6 0, 9 0 5')

// Process and write the image 
.write("recolor2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/7309b52810c8d46f386921758e1a3836.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-recolor](http://www.graphicsmagick.org/GraphicsMagick.html#details-recolor)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)