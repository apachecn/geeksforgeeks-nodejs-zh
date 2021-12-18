# 节点 Jimp |颜色饱和

> 原文:[https://www.geeksforgeeks.org/node-jimp-color-saturate/](https://www.geeksforgeeks.org/node-jimp-color-saturate/)

**简介**:**饱和**修改器是 Nodejs | Jimp 中的一个内置颜色修改器，它将图像饱和到给定的量，从 0 到 100。

**语法:**

```
image.color([
 { apply: 'saturate', params: [value] }
]);
```

**参数:**

*   **值**–该参数存储要应用的饱和度。它接受 0-100 之间的值。

**输入图像:**

![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

![](img/290a52d70280cfd5211f5083f062f10e.png)

#### **设置环境:**

```
npm init -y
```

#### 安装依赖项:

```
npm install jimp 
```

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
// color function having saturate modifier
  image.color([{apply:'saturate', params: [50]}])
  .write('saturate1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/44d695a93e3532c6786a2efc79a69a7b.png)

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
// color function having saturate modifier
  image.color([{apply:'saturate', params: [50]}], function(err){
    if (err) throw err;
  })
  .write('saturate2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/1fd2154deb0820bee381791fb2daebcb.png)

**参考:**T2https://www.npmjs.com/package/jimp