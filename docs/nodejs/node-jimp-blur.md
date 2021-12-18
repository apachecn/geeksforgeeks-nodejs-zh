# 节点 Jimp |模糊

> 原文:[https://www.geeksforgeeks.org/node-jimp-blur/](https://www.geeksforgeeks.org/node-jimp-blur/)

**简介**:blur()函数是 Nodejs | Jimp 中的一个内置函数，它使用模糊算法，产生类似高斯模糊的效果。

**语法:**

```js
blur(r, cb())
```

**参数:**

*   **r**–该参数存储模糊的半径。
*   **CB**–这是编译完成时调用的可选参数。

**输入图像:**

![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

![](img/290a52d70280cfd5211f5083f062f10e.png)

#### **设置环境:**

```js
npm init -y
```

#### 安装依赖项:

```js
npm install jimp 
```

#### **例 1:**

## java 描述语言

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
 const image = await Jimp.read('
   https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png');
  image.blur(5)
  .write('blur1.png');
}
main();
  console.log('Image Processing Completed');
```

**输出:**

![](img/d94cd29afbe88567b0b4d4175b671244.png)

**例 2:带 cb(可选参数)**

## java 描述语言

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read('
    https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
  image.blur(2, function(err){
    if (err) throw err;
  })
  .write('blur2.png');
}
main();
  console.log('Image Processing Completed');
```

**输出:**

![](img/28cedf6352a0288ead503aec20739054.png)

**参考:**T2https://www.npmjs.com/package/jimp