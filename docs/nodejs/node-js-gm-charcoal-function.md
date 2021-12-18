# Node.js GM 木炭()功能

> 原文:[https://www.geeksforgeeks.org/node-js-gm-charcoal-function/](https://www.geeksforgeeks.org/node-js-gm-charcoal-function/)

**木炭()函数**是 GraphicsMagick 库中的一个内置函数，用于向图像添加木炭滤镜。该函数在成功时返回真值。

**语法:**

```
charcoal( factor )
```

**参数:**该功能接受上面提到的和下面描述的单个参数:

*   **因子:**该参数存储要应用于图像的木炭因子的值。

**返回值:**该函数返回 Gmagick 木炭图像。

**原图:**
![](img/3a7f2a0c7a1b7410f45c9428c4fda2ad.png)

**例 1:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke Charcoal function
// with charcoal factor as 12
.charcoal(4)

// Process and Write the image
.write("charcoal1.png", function (err) {
    if (!err) console.log('done');
});
```

**输出:**
![](img/ca5731090d2bc14f2cbd83fd5b04b8a2.png)

**例 2:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Set stroke color
.stroke("#fe1232")

// Set fill color
.fill("#1200ff")

// Draw Rectangle using drawRectangle function
.drawRectangle(10, 2, 130, 30, 1, 2)

//Invoke Charcoal function as factor 3
.charcoal(3)

// Process and Write the image
.write("charcoal2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/7c880310f4cb457ed42aa74a7fae40eb.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-carbon](http://www.graphicsmagick.org/GraphicsMagick.html#details-charcoal)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)