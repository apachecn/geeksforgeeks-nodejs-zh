# Node.js GM 中位数()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-median-function/](https://www.geeksforgeeks.org/node-js-gm-median-function/)

**中值()**函数是 GraphicsMagick 库中的一个内置函数，用于对图像应用中值滤波器。该函数在成功时返回真值。

**注意:**此功能在**复合()**功能后不起作用。

**语法:**

```
median(radius)
```

**参数:**该函数接受单个参数**半径**，即像素的半径。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke Median function
.median(2)

// Process and Write the image
.write("median1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/e4d44c7a2d1e5b6ed20d021a7196cdc3.png)

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

// Invoke median function
.median(5)

// Process and write the image 
.write("median2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/18dc38b011b2066b79f70a1f8953452a.png)

**参考:**

*   [http://www.graphicsmagick.org/GraphicsMagick.html](http://www.graphicsmagick.org/GraphicsMagick.html)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)