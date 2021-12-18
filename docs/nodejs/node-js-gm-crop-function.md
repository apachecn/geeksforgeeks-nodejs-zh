# Node.js 转基因作物()功能

> 原文:[https://www.geeksforgeeks.org/node-js-gm-crop-function/](https://www.geeksforgeeks.org/node-js-gm-crop-function/)

**裁剪()**函数是 GraphicsMagick 库中的一个内置函数，用于通过指定坐标来移除图像中不需要的区域。该函数在成功时返回真值。

**语法:**

```
crop(width, height, x, y, percentage)
```

**参数:**该功能接受五个参数，如上所述，描述如下:

*   **宽度:**此参数用于指定要裁剪图像的宽度。
*   **高度:**此参数用于指定要裁剪图像的高度。
*   **x:** 此参数用于指定裁剪图像的宽度。
*   **y:** 此参数用于指定裁剪图像的宽度。
*   **百分比:**该参数用于指定布尔值，如果为真，则前面提到的所有值都被视为以像素为单位的百分比。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke crop function
.crop(50, 50, 12, 6, true)

// Process and Write the image
.write("crop1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/4331440a75f90395f1a7a19f05c7f279.png)

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

// Invoke borderColor() function
// and set border color to green
.borderColor("Green")

// Invoke border function
.border(62, 32)

// Invoke gaussian function
.crop(70, 40, 10, 10, true)

// Process and Write the image
.write("crop2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/e31df48de3025f03401c5f65f0990022.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-crop](http://www.graphicsmagick.org/GraphicsMagick.html#details-crop)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)