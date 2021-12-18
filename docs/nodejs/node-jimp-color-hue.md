# 节点 Jimp |色调

> 原文:[https://www.geeksforgeeks.org/node-jimp-color-hue/](https://www.geeksforgeeks.org/node-jimp-color-hue/)

**简介**
**色调**修改器是 Nodejs | Jimp 中的一个内置颜色修改器，它将图像的色调应用到给定的数量，从-360 到 360。它是旋转修改器的别名。
**语法:**

```
image.color([
  { apply: 'hue', params: [value] }
]);

```

**参数:**

*   **值**–该参数存储要应用的色调量。它取-360–360 之间的值。

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
// color function having hue modifier
  image.color([{apply:'hue', params: [50]}])
  .write('hue1.png');
} 

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/9dbbf444da32fe4f2cfb5e6331798b7c.png)
**例 2: cb(可选参数)**

```
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// color function having hue modifier
  image.color([{apply:'hue', params: [50]}], function(err){
    if (err) throw err;
  })
  .write('hue2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**
![](img/4e1ed414c78377d53c7ebb4f3e0d4cb6.png)
**参考:**[https://www.npmjs.com/package/jimp](https://www.npmjs.com/package/jimp)