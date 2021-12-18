# Node.js GM roll()功能

> 原文:[https://www.geeksforgeeks.org/node-js-gm-roll-function/](https://www.geeksforgeeks.org/node-js-gm-roll-function/)

**滚动()**功能是 GraphicsMagick 库中的一个内置功能，用于垂直或水平滚动图像。该函数在成功时返回真值。

**语法:**

```js
roll( x, y )
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **x:** 此参数用于指定水平滚动的值。
*   **y:** 此参数用于指定垂直滚动的值。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

## java 描述语言

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke roll function with 60, 60
.roll(60, 60)

// Process and Write the image
.write("roll1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/1f14ab40af91e3f5fd91defd27595997.png)

**例 2:**

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

// Invoke roll function
.roll(300, 150)

// Process and write the image 
.write("roll2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/13816d44cebc3e0d202093f50553e8f8.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-rotate](http://www.graphicsmagick.org/GraphicsMagick.html#details-rotate)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)