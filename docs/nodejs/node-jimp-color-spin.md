# 节点 Jimp |颜色旋转

> 原文:[https://www.geeksforgeeks.org/node-jimp-color-spin/](https://www.geeksforgeeks.org/node-jimp-color-spin/)

**简介**
**旋转**修改器是 Nodejs | Jimp 中的内置颜色修改器，它将图像的色调旋转到给定的量，从-360 到 360。旋转到 0，360，-360 不会执行任何功能，因为它会将色调设置回以前的颜色。
**语法:**

```js
image.color([
  { apply: 'spin', params: [value] }
]);

```

**参数:**

*   **值**–该参数存储要应用的色调旋转量。它的取值范围是-360 到 360。

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
// color function having spin modifier
  image.color([{apply:'spin', params: [50]}])
  .write('spin1.png');
} 

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/9ad23e99f7a8e944c9d71714781ca1ec.png)
**例 2: cb(可选参数)**

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// color function having spin modifier
  image.color([{apply:'spin', params: [50]}], function(err){
    if (err) throw err;
  })
  .write('spin2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/b42ac032c648eba1be5036460ffeadce.png)
**参考:**[https://www.npmjs.com/package/jimp](https://www.npmjs.com/package/jimp)