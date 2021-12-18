# Node.js GM 放大()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-magnify-function/](https://www.geeksforgeeks.org/node-js-gm-magnify-function/)

**放大()**函数是 GraphicsMagick 库中的一个内置函数，用于放大图像。该函数在成功时返回真值。

**语法:**

```
magnify( factor )
```

**参数:**该功能接受如上所述的单个参数，描述如下:

*   **因子:**该参数用于指定图像需要放大的因子。

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

// Invoke magnify function
.magnify(3)

// Process and Write the image
.write("magnify1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/092f6863ab3e5694011f96733fb2e667.png)

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

// Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Invoke borderColor() function
// and set border color to green
.borderColor("Green")

// Invoke border function
.border(62, 32)

// Invoke magnify() function
.magnify(2)

// Process and write the image 
.write("magnify2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/7a37df8d8925b768bd72bd4d0bc276dd.png)

**参考:**

*   [http://www.graphicsmagick.org/GraphicsMagick.html](http://www.graphicsmagick.org/GraphicsMagick.html)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)