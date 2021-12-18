# 节点 Jimp |颜色变暗

> 原文:[https://www.geeksforgeeks.org/node-jimp-color-darken/](https://www.geeksforgeeks.org/node-jimp-color-darken/)

**简介**
**变暗**修改器是 Nodejs | Jimp 中的一个内置颜色修改器，用于将图像变暗到给定的量，范围在 0 到 100 之间。在 100，图像将变成黑色图像。

**语法:**

```js
image.color([
 { apply: 'darken', params: [value] }
]);
```

**参数:**

*   **值**–该参数存储要应用的暗度。它接受 0-100 之间的值。

**输入图像:**

![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

![](img/290a52d70280cfd5211f5083f062f10e.png)

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
// color function having darken modifier
  image.color([{apply:'darken', params: [50]}])
  .write('darken1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/baa284dafef6d48bd6dfffc5db4206c0.png)

**例 2: cb(可选参数)**

## java 描述语言

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// color function having darken modifier
  image.color([{apply:'darken', params: [50]}], function(err){
    if (err) throw err;
  })
  .write('darken2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/50115aa28ce41fdc406dff9a78263df1.png)

**参考:**T2】https://www.npmjs.com/package/jimp