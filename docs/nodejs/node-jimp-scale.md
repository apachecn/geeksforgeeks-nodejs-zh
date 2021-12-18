# 节点 Jimp |刻度

> 原文:[https://www.geeksforgeeks.org/node-jimp-scale/](https://www.geeksforgeeks.org/node-jimp-scale/)

**简介**:scale()函数是 Nodejs | Jimp 中的一个内置函数，将图像统一缩放一个因子。

**语法:**

```js
scale(scale, mode, cb)
```

**参数:**

*   **缩放**–该参数存储图像的缩放因子。
*   **模式**–这是存储缩放方法的可选参数。
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

**例 1:**

## java 描述语言

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read('
   https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png');
// scale Function having scaling factor as 0.2
  image.scale(.2)
  .write('scale1.png');
}

main();
  console.log('Image Processing Completed');
```

**输出:**

![](img/ef4ffdca576c0728de0c4c4dded1d5ac.png)

**示例 2:带模式和 cb(可选参数)**

## java 描述语言

```js
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read('
   https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// scale Function having scaling-factor, mode and callback function
  image.scale(3, Jimp.RESIZE_BEZIER, function(err){
    if (err) throw err;
  })
  .write('scale2.png');
}

main();
  console.log('Image Processing Completed');
```

**输出:**

![](img/f93aad8847ea96385f70c54e839d3776.png)

**参考:**T2https://www.npmjs.com/package/jimp