# 节点 Jimp |颜色提亮

> 原文:[https://www.geeksforgeeks.org/node-jimp-color-brighten/](https://www.geeksforgeeks.org/node-jimp-color-brighten/)

**简介**
**提亮**修改器是 Nodejs | Jimp 中的一个内置颜色修改器，用于将图像提亮到给定量，范围在 0 到 100 之间。

**语法:**

```
image.color([
 { apply: 'brighten', params: [value] }
]);
```

**参数:**

*   **值**–该参数存储要应用的亮度值。它接受 0-100 之间的值。

**输入图像:**

![](img/11d75a22300d1eaf21322ef1a88a13d0.png) ![](img/290a52d70280cfd5211f5083f062f10e.png)

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
// color function having brighten modifier
  image.color([{apply:'brighten', params: [50]}])
  .write('brighten1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/bf7c476f273dcc3cb2e57a17741911a7.png)

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
// color function having brighten modifier
  image.color([{apply:'brighten', params: [50]}], function(err){
    if (err) throw err;
  })
  .write('brighten2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/ec5820199e7adbdfc855a7e2dc3eeeea.png)

**参考:**T2https://www.npmjs.com/package/jimp