# 节点| Jimp |对比

> 原文:[https://www.geeksforgeeks.org/node-jimp-contrast/](https://www.geeksforgeeks.org/node-jimp-contrast/)

**简介:****对比度()**功能是 Nodejs | Jimp 中的一个内置功能，它将图像的对比度调整为-1 到+1 的值。

**语法:**

```js
contrast(n, cb)
```

**参数:**

*   **n**–该参数存储调整对比度的量，介于-1 和+1 之间的数字
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
// contrast function
  image.contrast(.4)
  .write('contrast1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/87e534c0cba9e27699062d249137e97b.png)

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
// contrast function using callback function
  image.posterize(.5, function(err){
    if (err) throw err;
  })
  .write('contrast2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/1ff8ddf2ae1e76464926d68b89895f74.png)

**参考:**T2https://www.npmjs.com/package/jimp