# 节点 Jimp |反转

> 原文:[https://www.geeksforgeeks.org/node-jimp-invert/](https://www.geeksforgeeks.org/node-jimp-invert/)

**简介**:**反转()**功能是 Nodejs | Jimp 中的一个内置功能，可以反转图像的颜色。

**语法:**

```js
invert(cb)
```

**参数:**

*   **CB**–这是编译完成时调用的可选参数。

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
// invert function
  image.invert()
  .write('invert1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/18a0771b88aa5375e041ef6c628aa831.png)

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
// invert function using callback function
  image.invert(function(err){
    if (err) throw err;
  })
  .write('invert2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/f162b45d3ac235e2cea857e62bdec49c.png)

**参考:**T2https://www.npmjs.com/package/jimp