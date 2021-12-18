# 节点 Jimp |高斯

> 原文:[https://www.geeksforgeeks.org/node-jimp-gaussian/](https://www.geeksforgeeks.org/node-jimp-gaussian/)

**简介**:**高斯()函数**是 Nodejs | Jimp 中的一个内置函数，它对图像应用了真正的高斯模糊，但与其他 Jimp 函数相比，它的处理速度相当慢。

**语法:**

```
gaussian(r, cb)
```

**参数:**

*   **r**–该参数存储模糊的像素半径。
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
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png');
// invert function
  image.gaussian(5)
  .write('gaussian1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/2a017e55a504099152e72c58c0be518d.png)

**例 2:带半径和 cb(可选参数)**

## java 描述语言

```
//npm install --save jimp
//import jimp library to the environment
var Jimp = require('jimp');

//User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
//gaussian function using callback function
  image.gaussian(10, function(err){
    if (err) throw err;
  })
  .write('gaussian2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/e2bb40a4242c0f7aa65493c9a0b6fd07.png)

**参考:**T2https://www.npmjs.com/package/jimp