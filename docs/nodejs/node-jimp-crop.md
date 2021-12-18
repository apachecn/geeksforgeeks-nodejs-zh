# 节点 Jimp |裁剪

> 原文:[https://www.geeksforgeeks.org/node-jimp-crop/](https://www.geeksforgeeks.org/node-jimp-crop/)

**简介**
**裁剪()功能**是 Nodejs | Jimp 中的内置功能，用于以指定的坐标和尺寸裁剪图像。
**语法:**

```js
crop( x, y, w, h, cb )

```

**参数:**

*   **x**–该参数存储裁剪的 x 坐标。
*   **y**–该参数存储裁剪的 y 坐标。
*   **w**–该参数存储裁剪图像的宽度。
*   **h**–该参数存储裁剪图像的高度。
*   **CB**–这是编译完成时调用的可选参数。

**输入图像:**
![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

![](img/290a52d70280cfd5211f5083f062f10e.png)

**例 1:**

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read('../gfg.png');
// crop function having crop co-ordinates
// along with height and width
  image.crop(10, 10, 150, 120) 
  .write('crop1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/67e7b9087477c724ec5a22fd00a3252e.png)

**例 2:带 cb(可选参数)**

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read('../gfg1.png');
// crop function using callback function
  image.crop(20, 20, 100, 100, function(err){
    if (err) throw err;
  })
  .write('crop2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/4bac5a380f0370000d9a24cff77fcc58.png)

**参考:**T2】https://www.npmjs.com/package/jimp