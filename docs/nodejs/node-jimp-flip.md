# 节点 Jimp |翻转

> 原文:[https://www.geeksforgeeks.org/node-jimp-flip/](https://www.geeksforgeeks.org/node-jimp-flip/)

**简介**:**翻转()**功能是 Nodejs | Jimp 中的内置功能，可以水平或垂直翻转图像。默认设置是水平翻转图像。

**语法:**

```
flip(h, v, cb)
```

**参数:**

*   **h**–该参数取布尔值，如果为真，图像将水平翻转。
*   **v**–该参数取布尔值，如果为真，图像将垂直翻转。
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
// flip function also known as mirror function
  image.flip(true, false)
  .write('flip1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/438c9f264e6e6b6cc9dfa326e3387001.png)

**例 2:带 h、v、cb(可选参数)**

## java 描述语言

```
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
  const image = await Jimp.read
  ('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
// flip function using callback function
  image.flip(true, true, function(err){
    if (err) throw err;
  })
  .write('flip2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/683969963bd8b57c1838374839e9637d.png)

**参考:**T2https://www.npmjs.com/package/jimp