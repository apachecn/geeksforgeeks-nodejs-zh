# 节点 Jimp |颜色阴影

> 原文:[https://www.geeksforgeeks.org/node-jimp-color-shade/](https://www.geeksforgeeks.org/node-jimp-color-shade/)

**简介**
**色调**修改器是 Nodejs | Jimp 中的一个内置颜色修改器，它将黑色混合到图像中。
**语法:**

```js
image.color([
  { apply: 'shade', params: value }
]);

```

**参数:**

*   **值**–该参数存储要应用的色调量。

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
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png');
// color function having shade modifier
  image.color([{apply:'shade', params: [60]}])
  .write('sahde1.png');
} 

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/30693799c627ff9b3349aaaa84f0e772.png)
**例 2: cb(可选参数)**

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// color function having shade modifier
  image.color([{apply:'shade', params: [30]}], function(err){
    if (err) throw err;
  })
  .write('shade2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/b60fb94598844e037a9d2ed0a8e1a773.png)
**参考:**[https://www.npmjs.com/package/jimp](https://www.npmjs.com/package/jimp)