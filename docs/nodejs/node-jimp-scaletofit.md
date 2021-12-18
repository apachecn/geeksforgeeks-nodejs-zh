# 节点 Jimp | scaleToFit

> 原文:[https://www.geeksforgeeks.org/node-jimp-scaletofit/](https://www.geeksforgeeks.org/node-jimp-scaletofit/)

**简介**:scaleToFit()函数是 Nodejs | Jimp 中的一个内置函数，它可以将图像缩放到适合给定宽度和高度的矩形内部的最大尺寸。

**语法:**

```js
scaleToFit(w, h, mode, cb)
```

**参数:**

*   **w**–该参数存储图像的宽度。
*   **h**–该参数存储图像的高度。
*   **模式**–这是存储缩放方法的可选参数。
*   **CB**–这是编译完成时调用的可选参数。

**输入图像:**

![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

![](img/290a52d70280cfd5211f5083f062f10e.png)

#### **设置环境:**

```js
npm init -y
```

#### 安装依赖项:

```js
npm install jimp 
```

**例 1:**

## java 描述语言

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read('
    https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png');
// scaleToFit Function having width and height
  image.scaleToFit(300, 300)
  .write('scaleToFit1.png');
}

main();
  console.log('Image Processing Completed');
```

**输出:**

![](img/211861655f8b3ac103147b38fe01e790.png)

**示例 2:带模式和 cb(可选参数)**

## java 描述语言

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read('
   https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// scaleToFit Function having width, height, mode and callback function
  image.scaleToFit(1000, 1700, Jimp.RESIZE_BEZIER, function(err){
    if (err) throw err;
  })
  .write('scaleToFit2.png');
}

main();
  console.log('Image Processing Completed');
```

**输出:**

![](img/44a5b531c9871be915f872fb8b1fdbc6.png)

**参考:**T2https://www.npmjs.com/package/jimp