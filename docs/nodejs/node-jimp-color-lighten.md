# 节点 Jimp |颜色变浅

> 原文:[https://www.geeksforgeeks.org/node-jimp-color-lighten/](https://www.geeksforgeeks.org/node-jimp-color-lighten/)

**简介**:亮化修改器是 Nodejs | Jimp 中内置的一个颜色修改器，它可以将图像的颜色亮化到给定的量，范围在 0 到 100 之间。如果提供 100，将产生透明的白色图像。

**语法:**

```
image.color([
 { apply: 'lighten', params: [value] }
]);
```

**参数:**

*   **值**–该参数存储要应用的亮度。它接受 0-100 之间的值。

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
// color function having lighten modifier
  image.color([{apply:'lighten', params: [50]}])
  .write('lighten1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/e23f565992246ba9e008b28e966b3215.png)

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
// color function having lighten modifier
  image.color([{apply:'lighten', params: [50]}], function(err){
    if (err) throw err;
  })
  .write('lighten2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/e59b3a3703e210257bcae685745892b7.png)

**参考:**T2https://www.npmjs.com/package/jimp