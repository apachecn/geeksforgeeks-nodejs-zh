# node . js GM draw elliplex()函数

> 原文:[https://www . geesforgeks . org/node-js-GM-draw elliplex-function/](https://www.geeksforgeeks.org/node-js-gm-drawellipse-function/)

**绘制椭圆()函数**是 GraphicsMagick 库中的一个内置函数，用于绘制具有指定坐标的椭圆。该函数在成功时返回真值。

**语法:**

```
drawEllipse( x0, y0, x1, y1, r0, r1 )
```

**参数:**该函数接受六个参数，如上所述，如下所述:。

*   **x0:** 该参数存储初始点的 x 坐标值。
*   **y0:** 该参数存储初始点的 y 坐标值。
*   **x1:** 该参数存储最终点的 x 坐标值。
*   **y1:** 该参数存储最终点的 y 坐标值。
*   **r0:** 此参数存储椭圆的 x 半径值。
*   **r1:** 此参数存储椭圆的 y 半径值。

**返回值:**该函数返回 GraphicsMagick 对象。

**原图:**
![](img/cc57d2786304222491542e08aad0db5b.png)

**例 1:**

```
// Include gm library
var gm = require('gm').subClass({imageMagick: true});

// Import the image
gm('1.png')

// Set the color for the stroke
.stroke("#ffffff")

// Invoke drawEllipse function with
// x0 as 230, y0 as 45, x1 as 100,
// y1 as 89, r0 as 50 and r1 as 40
.drawEllipse(230, 45, 300, 89, 50, 40)

// Process and write the image 
.write("drawEllipse1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/f6905fe981c01c7a87250cf221c3da77.png)

**例 2:**

```
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

// Invoke drawEllipse function with x0
// as 230, y0 as 45, x1 as 100, y1 as
// 89, r0 as 50 and r1 as 40
.drawEllipse(290, 15, 300, 210, 20, 160)

// Process and write the image 
.write("drawEllipse1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/f3b80f6c0e0a3964b535d579fb9a06d6.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html #详情-绘制](http://www.graphicsmagick.org/GraphicsMagick.html#details-draw)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)