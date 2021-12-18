# Node.js GM shave()功能

> 原文:[https://www.geeksforgeeks.org/node-js-gm-shave-function/](https://www.geeksforgeeks.org/node-js-gm-shave-function/)

**剃刮()**功能是 GraphicsMagick 库中的内置功能，用于从边缘剃刮图像像素，该边缘指定要从图像两侧去除的区域的宽度以及要从顶部和底部去除的区域的高度。

**语法:**

```js
shave(width, height, percentage)
```

**参数:**该功能接受三个参数，如上所述，描述如下:

*   **宽度:**该参数存储图像被剃刮的宽度值。
*   **高度:**该参数存储图像被剃刮的高度值。
*   **百分比:**这是一个可选的布尔参数，如果设置为真，则存储百分比，否则存储像素。

**返回值:**该函数返回添加了图像的 Gmagick 对象。

**原图:**
![](img/3a7f2a0c7a1b7410f45c9428c4fda2ad.png)

**程序:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke shave function
.shave(30, 40, true)

// Process and Write the image
.write("shave1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/3d6650180a9fafcd1df861fdb2974461.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html #详情-剃](http://www.graphicsmagick.org/GraphicsMagick.html#details-shave)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)