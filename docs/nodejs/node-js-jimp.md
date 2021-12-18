# node . js jimp

> 原文:[https://www.geeksforgeeks.org/node-js-jimp/](https://www.geeksforgeeks.org/node-js-jimp/)

**简介**
Jimp 是一个用于做图像处理的节点模块，由 npm 安装程序提供。Jimp–Javascript 图像处理程序是一个完全用 JAVAScript 为 Node 编写的库，没有任何外部或本机依赖关系。
该库中可用的各种图像操作选项有:blit、blur、color、contain 等等。
Jimp 支持的图像类型:

*   @jimp/日本
*   @jimp/png
*   @jimp/bmp
*   @jimp/蒂夫
*   @jimp/gif

**优点:**
Nodejs 语法容易处理，有 Python 或 C++背景的人很容易习惯。nodejs 中的编译时间比其他任何东西都快。
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
//npm install --save jimp
//import jimp library to the environment
var Jimp = require('jimp');

//User-Defined Function to read the images
async function main() {
  const image1 = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png');
  const image2 = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');

  //call to blit function 
  image1.blit(image2, 20, 40)
  //write image
  .write('blit1.png');
  console.log("Image Processing Completed");
}

main();
```

**输出:**

![](img/7683a143a57191f36a2c64f66ad42b6c.png)

**例 2:**

## java 描述语言

```js
//npm install --save jimp
//import jimp library to the environment
var Jimp = require('jimp');

//User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
  image.blur(2, function(err){
    if (err) throw err;
  })
  .write('blur2.png');
}

main();
console.log("Image Processing Completed");
```

**输出:**

![](img/8ed69f9d7a7ea8b155298f9c3de40f86.png)

**参考:**T2https://www.npmjs.com/package/jimp