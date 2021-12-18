# 节点 Jimp |亮度

> 原文:[https://www.geeksforgeeks.org/node-jimp-brightness/](https://www.geeksforgeeks.org/node-jimp-brightness/)

**简介:****亮度()**功能是 Nodejs | Jimp 中的内置功能，可以将图像的亮度调整为-1 到+1 的值。

**语法:**

```
brightness(n, cb)
```

**参数:**

*   **n**–该参数存储亮度调节量，介于-1 和+1 之间的数字
*   **CB**–这是一个可选参数，在编译完成时调用。

**输入图像:**

![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

![](img/290a52d70280cfd5211f5083f062f10e.png)

#### 安装环境:

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
// contrast function
  image.brightness(.4)
  .write('brightness1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/9211f212e9c073755f409aa22ee59571.png)

**例 2:带 cb(可选参数)**

## java 描述语言

```
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
  ('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// contrast function using callback function
  image.brightness(-.5, function(err){
    if (err) throw err;
  })
  .write('brightness2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/6a398ddbf552a05900cb96fad4f2144a.png)

**参考:**T2https://www.npmjs.com/package/jimp