# Node.js GM chop()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-chop-function/](https://www.geeksforgeeks.org/node-js-gm-chop-function/)

**chop()函数**是 GraphicsMagick 库中的一个内置函数，用于移除图像内部的像素。该函数在成功时返回真值。

**语法:**

```
chop( width, height, x, y )
```

**参数:**该功能接受四个参数，如上所述，描述如下:

*   **宽度:**该参数用于指定图像被剪切的宽度。
*   **高度:**该参数用于指定图像被剪切的高度。
*   **x:** 此参数用于指定从宽度开始的 x 坐标。
*   **y:** 此参数用于指定从高度开始的 y 坐标。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke borderColor() function
// and set border color to green
.borderColor('Green')

// Invoke resize function
.border(10, 30)

// Invoke chop() function
.chop(100, 30, 40, 50)

// Process and Write the image
.write("chop1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/5f845415a9e2f62c8c4d8bc952824e17.png)

**例 2:**

```
// Include gm library
var gm = require('gm');

//Import the image
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

// Invoke chop() function
.chop(300, 180, 10, 50)

// Process and write the image 
.write("chop2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/040e10576a008bc84b93af472976d7b7.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-chop](http://www.graphicsmagick.org/GraphicsMagick.html#details-chop)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)