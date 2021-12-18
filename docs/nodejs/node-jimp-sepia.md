# 节点 Jimp |棕褐色

> 原文:[https://www.geeksforgeeks.org/node-jimp-sepia/](https://www.geeksforgeeks.org/node-jimp-sepia/)

**简介**:**棕褐色()**功能是 Nodejs | Jimp 中的一个内置功能，可对图像应用棕褐色色调/色调。

**语法:**

```js
sepia(cb)
```

**参数:**

*   **CB**–这是一个可选参数，在编译完成时调用。

**输入图像:**

![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

![](img/290a52d70280cfd5211f5083f062f10e.png)

#### 安装环境:

```js
npm init -y
```

#### 安装依赖项:

```js
npm install jimp
```

**例 1:**

## java 描述语言

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
  ('https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png');
// fade function
  image.sepia()
  .write('sepia1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/81a7f785639c9d55d326187a2f004562.png)

**例 2:带 cb(可选参数)**

## java 描述语言

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
  ('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// fade function using callback function
  image.sepia(function(err){
    if (err) throw err;
  })
  .write('sepia2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/92da473fe3548eb573027eb4f90f629a.png)

**参考:**T2https://www.npmjs.com/package/jimp