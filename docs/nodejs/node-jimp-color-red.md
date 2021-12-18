# 节点 Jimp |颜色红色

> 原文:[https://www.geeksforgeeks.org/node-jimp-color-red/](https://www.geeksforgeeks.org/node-jimp-color-red/)

**简介**
**红色**修改器是 Nodejs | Jimp 中的一个内置颜色修改器，它以给定的量修改给定图像的红色分量。

```js
image.color([
  { apply: 'red', params: value }
]);

```

**参数:**

*   **值**–该参数存储图像红色的修改量。

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
// color function having red modifier
  image.color([{apply:'red', params: [73]}])
  .write('red1.png');
} 

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/f382c246de68a8adbb4e81e105434a49.png)
**例 2: cb(可选参数)**

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// color function having red modifier
  image.color([{apply:'red', params: ['50']}], function(err){
    if (err) throw err;
  })
  .write('xor2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/1c90a64a16614bdf83aa23449f36ca7f.png)
**参考:**[https://www.npmjs.com/package/jimp](https://www.npmjs.com/package/jimp)