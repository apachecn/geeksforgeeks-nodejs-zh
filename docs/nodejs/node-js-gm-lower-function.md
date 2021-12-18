# node . js GM low()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-lower-function/](https://www.geeksforgeeks.org/node-js-gm-lower-function/)

**lower()** 函数是 GraphicsMagick 库中的一个内置函数，用于创建图像边缘的伪 3D 降低效果。该函数在成功时返回真值。

**语法:**

```
lower(width, height)
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **宽度:**该参数用于指定图像降低的宽度。
*   **高度:**此参数用于指定图像要降低的高度。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke lower function
.lower(45, 78)

// Process and Write the image
.write("lower1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/9c3d736e8a872e5e76d7cb3348d2ecf7.png)

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

// Invoke lower function
.lower(13, 56)

// Process and Write the image
.write("lower2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/9b0ee50ae854a0c71be54e48be1570d6.png)

**参考:**

*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)