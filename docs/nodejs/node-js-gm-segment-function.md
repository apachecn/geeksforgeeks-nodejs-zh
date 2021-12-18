# Node.js GM 段()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-segment-function/](https://www.geeksforgeeks.org/node-js-gm-segment-function/)

**segment()** 函数是 GraphicsMagick 库中的一个内置函数，用于通过分析颜色分量的直方图和使用模糊 c 均值技术识别同质单元来分割图像。该函数在成功时返回真值。

**语法:**

```js
threshold( cluster threshold, smoothing threshold )
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **聚类阈值:**此参数用于指定聚类阈值的值。
*   **平滑阈值:**此参数用于指定平滑阈值的值。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

## java 描述语言

```js
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

// Invoke segment function
.segment(1, 0.1)

// Process and write the image 
.write("segment1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/b19e25b28f05a8537e2237f683f03e9b.png)

**例 2:**

## java 描述语言

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke segment function with 2, 0.2
.segment(2, 0.2)

// Process and Write the image
.write("segment1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/96ffa7cdf7a21cd9c3a627f294f6e492.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-rotate](http://www.graphicsmagick.org/GraphicsMagick.html#details-rotate)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)