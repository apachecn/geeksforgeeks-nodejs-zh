# Node.js GM sepia()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-sepia-function/](https://www.geeksforgeeks.org/node-js-gm-sepia-function/)

**棕褐色()**函数是 GraphicsMagick 库中的一个内置函数，用于对图像应用棕褐色滤镜。该函数在成功时返回真值。

**语法:**

```js
sepia()
```

**参数:**此功能不接受任何参数。

**返回值:**该函数返回 GraphicsMagick 对象。

**例 1:**

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke sepia function
.sepia()

// Process and Write the image
.write("sepia1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/90860b0d330713c7f09e8c4fad001a22.png)

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

//Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Invoke borderColor() function
// and set border color to green
.borderColor("Green")

// Invoke border function
.border(62, 32)

// Invoke sepia function
.sepia()

// Process and Write the image
.write("sepia2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/272144a6775f937897ed83a8ff0400d9.png)

**参考:**

*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)