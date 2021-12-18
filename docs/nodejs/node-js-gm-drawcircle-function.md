# Node.js GM drawCircle()函数

> 原文:[https://www . geesforgeks . org/node-js-GM-draw circle-function/](https://www.geeksforgeeks.org/node-js-gm-drawcircle-function/)

**绘制圆()函数**是 GraphicsMagick 库中的一个内置函数，用于绘制指定坐标的圆。该函数在成功时返回真值。

**语法:**

```js
drawCircle( x0, y0, x1, y1 )
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

// set the color for the stroke
.stroke("#ffffff")

// Invoke drawCircle function with
// x0 as 30, y0 as 45, x1 as 300
// and y1 as 89
.drawCircle(30, 45, 300, 89)

// Process and write the image 
.write("drawCircle1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/aac0d05f77d4bb435c8b75e3f27b629c.png)

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

// Invoke drawCircle function with
// x0 as 10, y0 as 145, x1 as 200
// and y1 as 199
.drawCircle(10, 145, 200, 199)

// Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Process and write the image 
.write("drawCircle1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/121f8b176e238b5f9d9b3339facf0f78.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html #详情-绘制](http://www.graphicsmagick.org/GraphicsMagick.html#details-draw)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)