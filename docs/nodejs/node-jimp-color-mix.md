# 节点 Jimp |颜色混合

> 原文:[https://www.geeksforgeeks.org/node-jimp-color-mix/](https://www.geeksforgeeks.org/node-jimp-color-mix/)

**简介**
**混合**修改器是 Nodejs | Jimp 中的一个内置颜色修改器，它通过颜色的 RGB 分量值和叠加颜色的不透明度来混合颜色。
**语法:**

```js
image.color([
  { apply: 'mix', params: [color : value] }
]);

```

**参数:**

*   **颜色**–该参数存储要应用的颜色。
*   **值**–该参数存储要应用的颜色混合量。

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
// color function having hue modifier
  image.color([{apply:'mix', params: ['blue', 60]}])
  .write('mix1.png');
} 

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/36878a00f6b8a042182218f5388c5c19.png)
**例 2: cb(可选参数)**

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// color function having hue modifier
  image.color([{apply:'mix', params: ['green', 50]}], function(err){
    if (err) throw err;
  })
  .write('mix2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/4bc3852cfe25866df589e341f0558618.png)
**参考:**[https://www.npmjs.com/package/jimp](https://www.npmjs.com/package/jimp)