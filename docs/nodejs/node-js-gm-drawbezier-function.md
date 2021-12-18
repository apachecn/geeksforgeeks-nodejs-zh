# Node.js GM drawBezier()函数

> 原文:[https://www . geesforgeks . org/node-js-GM-draw bezier-function/](https://www.geeksforgeeks.org/node-js-gm-drawbezier-function/)

**绘制贝塞尔()函数**是 GraphicsMagick 库中的一个内置函数，用于绘制指定坐标的贝塞尔曲线。该函数在成功时返回真值。

**语法:**

```js
drawBezier( [x0, y0], ..., [xn, yn] )
```

**参数:**该函数接受具有 x 和 y 坐标的点的数组。

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

// Invoke Bezier function
.drawBezier([30, 20], [390, 70], [140, 110],
         [45, 56], [98, 45], [123, 65])

// Process and write the image 
.write("drawBezier1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/27edf0bd6fd31d721d7468b8de26118a.png)

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

// Invoke Bezier function
.drawBezier([30, 20], [390, 70], [140, 110],
     [45, 56], [98, 45], [123, 65], [500, 250])

// Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Process and write the image 
.write("drawBezier1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/82f09a57594114ba69f92fb71422556b.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html #详情-绘制](http://www.graphicsmagick.org/GraphicsMagick.html#details-draw)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)