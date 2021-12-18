# Node.js GM shade()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-shade-function/](https://www.geeksforgeeks.org/node-js-gm-shade-function/)

**阴影()功能**是 GraphicsMagick 库中的一个内置功能，用于使用远距离光源对图像进行阴影处理。该函数在成功时返回真值。

**语法:**

```js
shade( azimuthal angle, elevation angle )
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **方位角:**该参数存储方位角的值。
*   **仰角:**该参数存储仰角的值。

**返回值:**该函数返回添加了图像的 GraphicsMagick 对象。

**原图:**
![](img/3a7f2a0c7a1b7410f45c9428c4fda2ad.png)

**示例:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('gfg.png')

// Set stroke color
.stroke("#fe1232")

// Set fill color
.fill("#1200ff")

// Draw Rectangle using drawRectangle function
.drawRectangle(10, 2, 130, 30, 1, 2)

// Invoke shadefunction with azimuthal
// as 45 and elevation angle as 90
.shade(45, 90)

// Process and Write the image
.write("shade1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/80ab0117e6867c275df006197a8deda0.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-shade](http://www.graphicsmagick.org/GraphicsMagick.html#details-shade)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)