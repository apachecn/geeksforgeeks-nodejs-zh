# Node.js GM 通道()功能

> 原文:[https://www.geeksforgeeks.org/node-js-gm-channel-function/](https://www.geeksforgeeks.org/node-js-gm-channel-function/)

**通道()函数**是 GraphicsMagick 库中的一个内置函数，用于从图像中提取特定的通道。

**语法:**

```
channel( channelType )
```

**参数:**该功能接受单参数**通道类型**，保存通道名称的类型。通道的类型有红色、绿色、蓝色、不透明度、哑光、青色、洋红色、黄色、黑色或灰色。

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

// Invoke Channel function
// with 'All' parameter
.channel('All')

// Process and Write the image
.write("channel-all1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/9c5d8d150515a51e45a6ea432acb8f8d.png)

**例 2:**

```
// Include gm library
var gm = require('gm');

//Import the image
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

// Invoke Channel function 
// with 'All' parameter
.channel('Green')

// Process and write the image 
.write("channel-green.png", function (err) {
    if (!err) console.log('done');
});
```

**输出:**
![](img/e300c8ef9ac9d14a99fe30092b52e7a4.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html #详情-频道](http://www.graphicsmagick.org/GraphicsMagick.html#details-channel)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)