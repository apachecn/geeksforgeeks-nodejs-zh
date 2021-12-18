# 节点 Jimp |不透明度

> 原文:[https://www.geeksforgeeks.org/node-jimp-opacity/](https://www.geeksforgeeks.org/node-jimp-opacity/)

**简介**:**不透明度()**函数是 Nodejs | Jimp 中的一个内置函数，它将每个像素的不透明度乘以 0 到 1 之间的系数。

**语法:**

```js
opacity(f, cb)
```

**参数:**

*   **f**–该参数存储图像变得不透明的值。它的范围是 0 到 1。1 将使图像完全透明。
*   **CB**–这是一个可选参数，在编译完成时调用。

**输入图像:**

![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

![](img/290a52d70280cfd5211f5083f062f10e.png)

#### 安装环境:

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
  const image = await Jimp.read
  ('https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png');
// opacity function
  image.opacity(.3)
  .write('opacity1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/ed7daacad460968673d0e320bdb30ccb.png)

**例 2:带 cb(可选参数)**

## java 描述语言

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
  ('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// opacity function using callback function
  image.opacity(.5, function(err){
    if (err) throw err;
  })
  .write('opacity2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/f4a34679a272a255163ffebd70ba9968.png)

**参考:**T2https://www.npmjs.com/package/jimp