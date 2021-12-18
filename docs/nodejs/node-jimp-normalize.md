# 节点 Jimp |规格化

> 原文:[https://www.geeksforgeeks.org/node-jimp-normalize/](https://www.geeksforgeeks.org/node-jimp-normalize/)

**简介**:**normalize()**函数是 Nodejs | Jimp 中的一个内置函数，它通过计算直方图来规范化图像的颜色。

**语法:**

```js
normalize(cb)
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
// normalize Function
    image.normalize()
    .write('normalize1.png');
}

main();
    console.log("Image Processing Completed");
```

**输出:**

![](img/2f6f758abfaf35c6f48d1153d2a43c77.png)

**示例 2:带模式和 cb(可选参数)**

## java 描述语言

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
    const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// Normalize Function having callback function
    image.normalize(function(err){
      if (err) throw err;
  })
    .write('normalize2.png');
}

main();
    console.log("Image Processing Completed");
```

**输出:**

![](img/f04ec551e1f881b6414842321e59a30c.png)

**参考:**T2https://www.npmjs.com/package/jimp