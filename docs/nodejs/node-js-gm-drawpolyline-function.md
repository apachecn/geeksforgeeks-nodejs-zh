# node . js GM draw 折线()函数

> 原文:[https://www . geesforgeks . org/node-js-GM-draw polyline-function/](https://www.geeksforgeeks.org/node-js-gm-drawpolyline-function/)

**绘制折线()函数**是 GraphicsMagick 库中的一个内置函数，用于绘制具有指定坐标的折线。该函数在成功时返回真值。

**语法:**

```js
drawPolyline( [x0, y0], ..., [xn, yn] )
```

**参数:**这个函数接受 x 和 y 坐标的数组。

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
.stroke("#000000")

// Invoke drawPolyline function with array of points
.drawPolyline([12, 60], [45, 79], [80, 120], [300, 32])

// Process and write the image 
.write("drawPolyline1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/9ccbf38f96c0a48eb3c862b31ea68b1c.png)

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

// Invoke drawPolyline function with
// array of points
.drawPolyline([12, 60], [45, 79], [80, 120],
          [300, 32], [400, 150], [500, 200])

// Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Process and write the image 
.write("drawPolyline1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/e57bf37ae288d40d59693b5df15e2042.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html #详情-绘制](http://www.graphicsmagick.org/GraphicsMagick.html#details-draw)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)