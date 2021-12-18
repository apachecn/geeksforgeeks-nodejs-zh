# Node.js GM raise()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-raise-function/](https://www.geeksforgeeks.org/node-js-gm-raise-function/)

**raise()** 函数是 GraphicsMagick 库中的一个内置函数，用于使图像边缘变亮或变暗。这将产生三维效果。该函数在成功时返回真值。

**语法:**

```js
raise( width, height )
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **宽度:**此参数用于指定效果的宽度。
*   **权重:**此参数用于指定效果的高度。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke quality function with
// average parameter
.raise(30, 60)

// Process and Write the image
.write("raise1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/fcba1b9ae16aaea19462f26c6539ba5c.png)

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

// Invoke raise function with 200, 75
.raise(200, 75)

// Process and write the image 
.write("raise2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/48661a19132a2f44cee806764edc602c.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-raise](http://www.graphicsmagick.org/GraphicsMagick.html#details-raise)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)