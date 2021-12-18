# 节点 Jimp |彩色灰度

> 原文:[https://www.geeksforgeeks.org/node-jimp-color-greyscale/](https://www.geeksforgeeks.org/node-jimp-color-greyscale/)

**简介**
**灰度**修改器是 Nodejs | Jimp 中的内置颜色修改器，它根据给定的数量(从 0 到 100)将图像颜色去饱和为灰度。
**语法:**

```js
image.color([
 { apply: 'grayscale', params: [value] }
]);
```

**参数:**

*   **值**–该参数存储要应用的灰度值。它接受 0-100 之间的值。

**输入图像:**

![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

![](img/290a52d70280cfd5211f5083f062f10e.png)

**例 1:**

## java 描述语言

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

//User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png');
// color function having grayscale modifier
  image.color([{apply:'grayscale', params: [50]}])
  .write('grayscale1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/b642009c77f12171ee29412e635fc9b9.png)

**例 2: cb(可选参数)**

## java 描述语言

```js
//npm install --save jimp
//import jimp library to the environment
var Jimp = require('jimp');

//User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// color function having grayscale modifier
  image.color([{apply:'grayscale', params: [50]}], function(err){
    if (err) throw err;
  })
  .write('grayscale2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/6486eff30e81d4c9bc73175231193a63.png)

**参考:**T2https://www.npmjs.com/package/jimp