# Node.js GM edge()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-edge-function/](https://www.geeksforgeeks.org/node-js-gm-edge-function/)

**边缘()函数**是 GraphicsMagick 库中的一个内置函数，用于检测图像中的边缘。该函数在成功时返回真值。

**语法:**

```js
edge( radius )
```

**参数:**该功能接受如上所述的单个参数，描述如下:

*   **半径:**此参数用于指定图像内边缘的半径。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke borderColor() function
// and set border color to green
.borderColor('Green')

// Invoke resize function
.border(10, 30)

// Invoke edge function
.edge(13)

// Process and Write the image
.write("edge1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/5d73f81a4781de1617ca040022ded314.png)

**例 2:**

```js
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

// Invoke borderColor() function and
// set border color to green
.borderColor("Green")

// Invoke border function
.border(62, 32)

// Invoke edge() function
.edge(20)

// Process and write the image 
.write("edge2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/6dea7b0d7368f81e0e846811e7311f64.png)

**参考:**

*   [http://www.graphicsmagick.org/GraphicsMagick.html](http://www.graphicsmagick.org/GraphicsMagick.html)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)