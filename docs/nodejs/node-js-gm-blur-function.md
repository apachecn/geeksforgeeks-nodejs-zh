# Node.js GM 模糊()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-blur-function/](https://www.geeksforgeeks.org/node-js-gm-blur-function/)

**模糊()函数**是 GraphicsMagick 库中的一个内置函数，用于给图像添加模糊滤镜。该函数在成功时返回真值。

**语法:**

```
blur( radius, sigma )
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **半径:**该参数存储模糊半径的值。
*   **σ:**是存储对象σ的可选参数。

**返回值:**该函数返回模糊的 Gmagick 图像。

**原图:**
![](img/3a7f2a0c7a1b7410f45c9428c4fda2ad.png)

**例 1:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm('gfg.png')

// Invoke Blur function with blur radius as 12
.blur(10)

// Process and Write the image
.write("blur1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/5ebb9e0f75fbb6db0b06763ae335bf16.png)

**例 2:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke shear function with 
// xDegrees as 45 and yDegrees as 90
.rotate("#545651", 78)

// Invoke blur function with radius
// as 5 and sigma as 5 
.blur(5, 5)

// Process and Write the image
.write("blur2.png", function (err) {
    if (!err) console.log('done');
});
```

**输出:**
![](img/34a6cdab71c45c2575bea8e9283ab23f.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html #详情-模糊](http://www.graphicsmagick.org/GraphicsMagick.html#details-blur)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)