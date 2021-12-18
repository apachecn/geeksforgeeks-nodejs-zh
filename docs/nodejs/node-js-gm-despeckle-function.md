# Node.js GM despeckle()函数

> 原文:[https://www . geesforgeks . org/node-js-GM-despeckle-function/](https://www.geeksforgeeks.org/node-js-gm-despeckle-function/)

**去斑点()**函数是 GraphicsMagick 库中的一个内置函数，用于减少图像中的斑点。该函数在成功时返回真值。

**语法:**

```
despeckle()
```

**参数:**此功能不接受任何参数。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke despeckle function
.despeckle()

// Process and Write the image
.write("despeckle1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/2431fcf9069627bbfde7573882d411f6.png)

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

// Invoke despeckle function
.despeckle()

// Process and Write the image
.write("despeckle2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/2a4f7b8b356887bd6333fafa85695bf6.png)

**参考:**

*   [http://www.graphicsmagick.org/GraphicsMagick.html](http://www.graphicsmagick.org/GraphicsMagick.html)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)