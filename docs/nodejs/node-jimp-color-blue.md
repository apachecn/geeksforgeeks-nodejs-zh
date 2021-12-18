# 节点 Jimp |颜色蓝色

> 原文:[https://www.geeksforgeeks.org/node-jimp-color-blue/](https://www.geeksforgeeks.org/node-jimp-color-blue/)

**简介:****异或**修改器是 Nodejs Jimp 中的一个内置颜色修改器，它以给定的量修改给定图像的蓝色分量。

**语法:**

```js
image.color([
  { apply: 'green', params: value }
]);

```

**参数:**

*   **值:**该参数存储图像蓝色的修改量。

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
    const image = await Jimp.read(
'https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png');
    // color function having blue modifier
    image.color([{apply:'blue', params: [73]}])
    .write('blue1.png');
} 

main();
    console.log("Image Processing Completed");
```

**输出:**
![](img/c807fba09227a176bc64a5f9686d2032.png)

**例 2: cb(可选参数)**

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
    const image = await Jimp.read(
'https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');

// color function having blue modifier
    image.color([{apply:'blue', params: ['50']}], function(err){
        if (err) throw err;
    })
    .write('blue2.png');
}

main();
    console.log("Image Processing Completed");
```

**输出:**
![](img/feaaf956341fa03a72c8c235aad7b129.png)

**参考:**T2】https://www.npmjs.com/package/jimp