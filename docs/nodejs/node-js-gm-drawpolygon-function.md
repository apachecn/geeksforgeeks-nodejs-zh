# Node.js GM drawPolygon()函数

> 原文:[https://www . geesforgeks . org/node-js-GM-draw polygon-function/](https://www.geeksforgeeks.org/node-js-gm-drawpolygon-function/)

**绘制多边形()函数**是 GraphicsMagick 库中的一个内置函数，用于绘制具有指定坐标的多边形。该函数在成功时返回真值。

**语法:**

```
drawPolygon( [x0, y0], ... ,[xn, yn] )
```

**参数:**这个函数接受 x 和 y 坐标的数组。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm(500, 200, 'white')

// Set the color for the stroke
.stroke("green", 3)

// Set font as 'Helvetica'
.font("Helvetica.ttf", 60)

// Use drawText() Function
.drawText(30, 160, "GeeksforGeeks!")

// Invoke drawPolygon function
// with array of points
.drawPolygon([12, 60], [45, 79], 
        [80, 120], [300, 32], [300, 98])

// Process and write the image 
.write("drawPolygon1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/39168df4551c15f27dd0105c325fc2e2.png)

**例 2:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm('https://media.geeksforgeeks.org/wp-content/uploads/20200227114541/1406-3.png')

// Set the color for the stroke
.stroke("#000000", 5)

// Invoke drawPolygon function with array of points
.drawPolygon([12, 60], [45, 79], [80, 120], [300, 32])

// Process and write the image 
.write("drawPolygon1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/6ade869b38768bee865ebfa7dc32ddd1.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html #详情-绘制](http://www.graphicsmagick.org/GraphicsMagick.html#details-draw)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)