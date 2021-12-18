# Node.js GM 油漆()功能

> 原文:[https://www.geeksforgeeks.org/node-js-gm-paint-function/](https://www.geeksforgeeks.org/node-js-gm-paint-function/)

**paint()** 函数是 GraphicsMagick 库中的一个内置函数，用于模拟一幅油画。
该函数返回成功时的真实值。

**语法:**

```js
paint( radius )
```

**参数:**该功能接受如上所述的单个参数，描述如下:

*   **半径:**此参数用于指定油漆的半径。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke ordered Dither on
// Green Channel with 50 x 60
.paint(2)

// Process and Write the image
.write("paint1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/b6aa40b6b39f6360e317993088793cf1.png)

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

// Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Invoke paint function
.paint(1.2)

// Process and write the image 
.write("paint2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/509f14f6c159ac8ce75e383951332a2e.png)
**参考:**

[http://www.graphicsmagick.org/GraphicsMagick.html#details-paint](http://www.graphicsmagick.org/GraphicsMagick.html#details-paint)

*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)T2
    T4】