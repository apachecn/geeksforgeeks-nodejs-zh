# 节点 Jimp |像素化

> 原文:[https://www.geeksforgeeks.org/node-jimp-pixelate/](https://www.geeksforgeeks.org/node-jimp-pixelate/)

**简介**:pixelate()函数是 Nodejs | Jimp 中的一个内置函数，用于在图像或区域上应用像素化效果。

**语法:**

```
pixelate(size, x, y, w, h, cb)
```

**参数:**

*   **大小**–该参数取像素的大小。
*   **x**–该参数取区域的 x 位置进行像素化。
*   **y**–该参数将区域的 y 位置像素化。
*   **w**–这是一个可选参数，它将区域的宽度像素化。
*   **h**–这是一个可选参数，它将区域的高度像素化。
*   **CB**–这是一个可选参数，在编译完成时调用。

**输入图像:**

![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

![](img/290a52d70280cfd5211f5083f062f10e.png)

#### 安装环境:

```
npm init -y
```

#### 安装依赖项:

```
npm install jimp
```

**例 1:**

## java 描述语言

```
//npm install --save jimp
//import jimp library to the environment
var Jimp = require('jimp');

//User-Defined Function to read the images
async function main() {
  const image = await Jimp.read('../gfg.png');
// pixelate function
  image.pixelate(5)
  .write('pixelate1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/b4d38aa54f85fe23fc68538d5df879f8.png)

**例 2:带尺寸，x，y，w，h 和 cb(可选参数)**

## java 描述语言

```
//npm install --save jimp
//import jimp library to the environment
var Jimp = require('jimp');

//User-Defined Function to read the images
async function main() {
  const image = await Jimp.read('../gfg1.png');
//pixelate function using callback function
  image.pixelate(5, 40, 50, 190, 200, function(err){
    if (err) throw err;
  })
  .write('pixelate2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/99a814a40957f2d170acab127527e1eb.png)

**参考:**T2https://www.npmjs.com/package/jimp