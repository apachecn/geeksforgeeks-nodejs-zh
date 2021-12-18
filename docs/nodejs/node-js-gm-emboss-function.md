# Node.js GM 浮雕()功能

> 原文:[https://www.geeksforgeeks.org/node-js-gm-emboss-function/](https://www.geeksforgeeks.org/node-js-gm-emboss-function/)

**浮雕()**函数是 GraphicsMagick 库中的一个内置函数，用于浮雕图像，这意味着图像的每个像素都被替换以产生 3D 效果。该函数在成功时返回真值。
**语法:**

```js
emboss(radius)
```

**参数:**该功能接受单个参数作为半径，用于指定压花半径。
**返回值:**该函数返回 GraphicsMagick 对象。
**例 1:**

## java 描述语言

```js
// Include gm library 
var gm = require('gm'); 

// Import the image 
gm('1.png') 

// Invoke emboss function 
.emboss(12) 

// Process and Write the image 
.write("emboss1.png", function (err) { 
  if (!err) console.log('done'); 
}); 
```

**输出:**

![](img/ecb891b6048c8af623e7ac859fd286bf.png)

**例 2:**

## java 描述语言

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

// Invoke borderColor() function 
// and set border color to green 
.borderColor("Green") 

// Invoke border function 
.border(62, 32) 

// Invoke emboss function 
.emboss(3) 

// Process and Write the image 
.write("emboss2.png", function (err) { 
  if (!err) console.log('done'); 
}); 
```

**输出:**

![](img/df4c3195735a883170ad190e92722b30.png)

**参考:**

*   [http://www.graphicsmagick.org/GraphicsMagick.html](http://www.graphicsmagick.org/GraphicsMagick.html)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)