# 节点 Jimp |淡化

> 原文:[https://www.geeksforgeeks.org/node-jimp-fade/](https://www.geeksforgeeks.org/node-jimp-fade/)

**简介**
**渐变()**功能是 Nodejs | Jimp 中的一个内置功能，它以 0 到 1 之间的因子渐变每个像素。
**语法:**

```js
fade(f, cb)
```

**参数:**

*   **f**–该参数存储使图像透明的值。它的范围是 0 到 1。1 将使图像完全透明。
*   **CB**–这是编译完成时调用的可选参数。

**输入图像:**

![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

![](img/290a52d70280cfd5211f5083f062f10e.png)

### 步骤 1:设置环境

```js
npm init -y
```

### 第二步:安装*跳*

```js
npm install jimp --save
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
// fade function
  image.fade(.5)
  .write('fade1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/f03138eddaa1573ff3f8494c47fd01fa.png)

**例 2:带 f 和 cb(可选参数)**

## java 描述语言

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
  ('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// fade function using callback function
  image.fade(0.8, function(err){
    if (err) throw err;
  })
  .write('fade2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/907cd8003c7263ae061bf9e62911aacb.png)

**参考:**T2https://www.npmjs.com/package/jimp