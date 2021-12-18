# 节点 Jimp |颜色去饱和

> 原文:[https://www.geeksforgeeks.org/node-jimp-color-desaturate/](https://www.geeksforgeeks.org/node-jimp-color-desaturate/)

**简介**
**去饱和**修改器是 Nodejs | Jimp 中的一个内置颜色修改器，它将图像去饱和到一个给定量，从 0 到 100。如果超过 100 个数量，就会产生灰度图像。
**语法:**

```
image.color([
 { apply: 'desaturate', params: [value] }
]);
```

**参数:**

*   **值**–该参数存储要应用的暗度。它接受 0-100 之间的值。

**输入图像:**

![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

![](img/290a52d70280cfd5211f5083f062f10e.png)

**例 1:**

## java 描述语言

```
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png');
// color function having desaturate modifier
  image.color([{apply:'desaturate', params: [60]}])
  .write('desaturate1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/633075de2678debda0de1d0dea56fc6c.png)

**例 2: cb(可选参数)**

## java 描述语言

```
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// color function having desaturate modifier
  image.color([{apply:'desaturate', params: [50]}],function(err){
    if (err) throw err;
  })
  .write('desaturate2.jpg');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/7e80ee4e7147d2750bf5732714b61c61.png)

**参考:**T2】https://www.npmjs.com/package/jimp