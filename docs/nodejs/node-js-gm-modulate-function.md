# 节点 js GM 调制()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-modulate-function/](https://www.geeksforgeeks.org/node-js-gm-modulate-function/)

**调制()**功能是 GraphicsMagick 库中的一个内置功能，用于改变图像的亮度、饱和度和色调。该函数在成功时返回真值。

**语法:**

```js
modulate( brightness, saturation, hue )
```

**参数:**该函数接受三个参数，如上所述，如下所述:

*   **亮度:**该参数用于指定亮度等级的值。
*   **饱和度:**该参数用于指定饱和度等级的值。
*   **色调:**该参数用于指定色调级别的值。

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

// Invoke modulate function
.modulate(50, 50, 50)

// Process and Write the image
.write("modulate1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/5e40c0fcef4a7a4d59ad5996a7aa10d6.png)

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

// Invoke borderColor() function
// and set border color to green
.borderColor("Green")

// Invoke border function
.border(62, 32)

// Invoke motionBlur() function
.modulate(120, 110, 130)

// Process and write the image 
.write("modulate2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/8ce156db039da835b6c48e96866b2136.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-modulate](http://www.graphicsmagick.org/GraphicsMagick.html#details-modulate)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)