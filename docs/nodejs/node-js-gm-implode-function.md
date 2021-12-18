# Node.js GM 内爆()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-implode-function/](https://www.geeksforgeeks.org/node-js-gm-implode-function/)

**内爆()函数**是 GraphicsMagick 库中的一个内置函数，用于内爆中心周围的图像像素。该函数在成功时返回真值。

**语法:**

```
implode( factor )
```

**参数:**该功能接受如上所述的单个参数，描述如下:

*   **因子:**该参数用于指定图像需要围绕中心内爆图像像素的因子。

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

// Invoke implode function
.implode(3)

// Process and Write the image
.write("implode1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/72971b4454552fb22ddbcdb93841b851.png)

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

// Invoke implode() function
.implode(2)

// Process and write the image 
.write("implode2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/97d9bfbf11b588068230f4f68f15d996.png)

**参考:**

*   [http://www.graphicsmagick.org/GraphicsMagick.html](http://www.graphicsmagick.org/GraphicsMagick.html)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)