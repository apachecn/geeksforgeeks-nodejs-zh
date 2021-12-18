# Node.js GM scale()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-scale-function/](https://www.geeksforgeeks.org/node-js-gm-scale-function/)

**裁剪()**函数是 GraphicsMagick 库中的一个内置函数，用于缩放图像。该函数在成功时返回真值。

**语法:**

```
crop(width, height)
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **宽度:**此参数用于指定图像缩放的宽度。
*   **高度:**此参数用于指定图像缩放的高度。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke scale function
.scale(130, 230)

// Process and Write the image
.write("scale1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/a843c0e72df5f3c19ca1370e30783968.png)

**例 2:**

```
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
.scale(300, 200)

// Process and Write the image
.write("scale2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/d66fa9a858f22522361ca7c57cb6616d.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html #详情-比例尺](http://www.graphicsmagick.org/GraphicsMagick.html#details-scale)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)