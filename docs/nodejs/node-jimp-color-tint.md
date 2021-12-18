# 节点 Jimp |颜色色调

> 原文:[https://www.geeksforgeeks.org/node-jimp-color-tint/](https://www.geeksforgeeks.org/node-jimp-color-tint/)

**简介**
**色调**修改器是 Nodejs | Jimp 中的一个内置颜色修改器，它将白色混合到图像中。
**语法:**

```js
image.color([
  { apply: 'tint', params: value }
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
// color function having tint modifier
  image.color([{apply:'tint', params: [60]}])
  .write('tint1.png');
} 

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/b111df062a0adc2ddda54057f7c95ec8.png)
**例 2: cb(可选参数)**

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// color function having tint modifier
  image.color([{apply:'tint', params: [30]}], function(err){
    if (err) throw err;
  })
  .write('tint2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/80f4b75e60724443ae92dde29481c05d.png)
**参考:**[https://www.npmjs.com/package/jimp](https://www.npmjs.com/package/jimp)