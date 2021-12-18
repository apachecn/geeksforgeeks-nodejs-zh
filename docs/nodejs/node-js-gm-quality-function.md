# Node.js GM 质量()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-quality-function/](https://www.geeksforgeeks.org/node-js-gm-quality-function/)

**quality()** 函数是 GraphicsMagick 库中的一个内置函数，用于 JPEG/MIFF/PNG/TIFF 压缩级别。如果滤波器类型为 4 或更小，则指定的滤波器类型用于所有扫描线:0:无、1:子、2:上、3:平均、4:路径。该函数在成功时返回真值。
**语法:**

```
quality( level )
```

**参数:**该函数接受上面提到的、下面定义的单个参数:

*   **等级:**该参数用于指定质量等级。

**返回值:**该函数返回 GraphicsMagick 对象。
T3】例 1:

## java 描述语言

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke quality function with
// average parameter
.quality(3)

// Process and Write the image
.write("quality1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/f81c6ad5db1d483441d66c8eeeb6c2db.png)

**例 2:**

## java 描述语言

```
// Include gm library
var gm = require('gm');

//Import the image
gm(600, 300, 'white')

// Set the color for the stroke
.stroke("green", 3)

// Set the font 
.font("Helvetica.ttf", 60)

//Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Invoke quality function with
// sub-option via 1 
    //  0: none
    //  1: sub
    //  2: up
    //  3: average
    //  4: Paeth
.quality(1)

// Process and write the image 
.write("quality2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/4ee7529d0fe4e8c153d209a84727159f.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html #详情-质量](http://www.graphicsmagick.org/GraphicsMagick.html#details-quality)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)