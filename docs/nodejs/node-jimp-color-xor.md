# 节点 Jimp |颜色 xor

> 原文:[https://www.geeksforgeeks.org/node-jimp-color-xor/](https://www.geeksforgeeks.org/node-jimp-color-xor/)

**简介**
**xor**修改器是 Nodejs | Jimp 中的内置颜色修改器，它将两种颜色视为位域，并对给定图像的红色、绿色和蓝色分量进行 XOR 运算。

```
image.color([
  { apply: 'xor', params: value }
]);

```

**参数:**

*   **值**–该参数存储要应用异或运算的颜色。

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
// color function having xor modifier
  image.color([{apply:'xor', params: ['green']}])
  .write('xor1.png');
} 

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/fdccf9d13cb9c83707a6327c50708f2f.png)
**例 2: cb(可选参数)**

```
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// color function having xor modifier
  image.color([{apply:'xor', params: ['blue']}], function(err){
    if (err) throw err;
  })
  .write('xor2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/8e7b62054231168a7cf2d619b6caa7ee.png)
**参考:**[https://www.npmjs.com/package/jimp](https://www.npmjs.com/package/jimp)