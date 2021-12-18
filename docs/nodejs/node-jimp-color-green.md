# 节点 Jimp |颜色|绿色

> 原文:[https://www.geeksforgeeks.org/node-jimp-color-green/](https://www.geeksforgeeks.org/node-jimp-color-green/)

**简介**
**绿色**修改器是 Nodejs | Jimp 中的一个内置颜色修改器，它以给定的量修改给定图像的绿色分量。

```
image.color([
  { apply: 'green', params: value }
]);

```

**参数:**

*   **值**–该参数存储图像绿色的修改量。

**输入图像:**
![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

![](img/290a52d70280cfd5211f5083f062f10e.png)

**例 1:**

```
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png');
// color function having green modifier
  image.color([{apply:'green', params: [73]}])
  .write('green1.png');
} 

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/74446c8316db5b4cda72ade6263db964.png)
**例 2: cb(可选参数)**

```
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// color function having green modifier
  image.color([{apply:'green', params: ['50']}], function(err){
    if (err) throw err;
  })
  .write('green.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/1c7923095e3edb9a137a09447923fb8c.png)
**参考:**[https://www.npmjs.com/package/jimp](https://www.npmjs.com/package/jimp)