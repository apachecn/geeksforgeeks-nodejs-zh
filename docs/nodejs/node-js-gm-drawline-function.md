# Node.js GM drawLine()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-drawline-function/](https://www.geeksforgeeks.org/node-js-gm-drawline-function/)

**画线()函数**是 GraphicsMagick 库中的一个内置函数，用于绘制指定坐标的直线。该函数在成功时返回真值。

**语法:**

```js
drawLine( x0, y0, x1, y1 )
```

**参数:**该函数接受上面提到的和下面描述的四个参数:。

*   **x0:** 该参数存储初始点的 x 坐标值。
*   **y0:** 该参数存储初始点的 y 坐标值。
*   **x1:** 该参数存储最终点的 x 坐标值。
*   **y1:** 该参数存储最终点的 y 坐标值。

**返回值:**该函数返回 GraphicsMagick 对象。

**原图:**
![](img/cc57d2786304222491542e08aad0db5b.png)

**例 1:**

```js
// Include gm library
var gm = require('gm').subClass({imageMagick: true});

// Import the image
gm('1.png')

// Set the color for the stroke
.stroke("#000000", 20)

// Invoke drawLine function with x0 as 100,
// y0 as 45, x1 as 100, y1 as 89, r0 as 50
// and r1 as 40
.drawLine(100, 30, 400, 80)

// Process and write the image 
.write("drawLine1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/db381a5f1800b168231b24fa742ec4dc.png)

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

// Invoke drawLine function with
// x0 as 100, y0 as 45, x1 as 100,
// y1 as 200
.drawLine(100, 45, 100, 200)

// Invoke drawLine function with
// x0 as 100, y0 as 45, x1 as 500,
// y1 as 45
.drawLine(100, 45, 500, 45)

// Invoke drawLine function with
// x0 as 500, y0 as 45, x1 as 500,
// y1 as 200
.drawLine(500, 45, 500, 200)

// Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Process and write the image 
.write("drawLine1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/6fb817816ef4f76035f5ed5774c23be4.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html #详情-绘制](http://www.graphicsmagick.org/GraphicsMagick.html#details-draw)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)