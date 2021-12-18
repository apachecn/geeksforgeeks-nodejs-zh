# Node.js GM flip()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-flip-function/](https://www.geeksforgeeks.org/node-js-gm-flip-function/)

**flip()** 函数是 GraphicsMagick 库中的一个内置函数，用于创建垂直方向的镜像。该函数在成功时返回真值。

**语法:**

```js
flip()
```

**参数:**此功能不接受任何参数。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke borderColor() function and
// set border color to green
.borderColor('Green')

// Invoke resize function
.border(10, 30)

// Invoke flip() function
.flip()

// Process and Write the image
.write("flip1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/bea97f0a32037272190fa6f99d351293.png)

**例 2:**

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

// Invoke borderColor() function and
// set border color to green
.borderColor("Green")

// Invoke border function
.border(62, 32)

// Invoke flip() function
.flip()

// Process and write the image 
.write("flip2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/eb8e728393361fa1efc0807346bd0ddd.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html #详情-翻转](http://www.graphicsmagick.org/GraphicsMagick.html#details-flip)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)