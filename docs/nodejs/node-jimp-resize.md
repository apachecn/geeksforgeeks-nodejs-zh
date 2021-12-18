# 节点 Jimp |调整大小

> 原文:[https://www.geeksforgeeks.org/node-jimp-resize/](https://www.geeksforgeeks.org/node-jimp-resize/)

**简介**
resize()函数是 Nodejs | Jimp 中的一个内置函数，它使用 2 遍双线性算法将图像的大小调整为设定的宽度和高度。
**语法:**

```
resize(w, h, mode, cb)
```

**参数:**

*   **w**–该参数存储图像的宽度。
*   **h**–该参数存储图像的高度。
*   **模式**–这是存储缩放方法的可选参数。
*   **CB**–这是编译完成时调用的可选参数。

**输入图像:**

![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

![](img/290a52d70280cfd5211f5083f062f10e.png)

### 步骤 1:设置环境

```
npm init -y
```

### 第二步:安装*跳*

```
npm install jimp --save
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
// rotate Function having rotation as 55
    image.resize(323, 421)
    .write('resize1.png');
}

main();
    console.log("Image Processing Completed");
```

**输出:**

![](img/ab4ab048366044d2016afda9aa4455cb.png)

**例 2:带 cb(可选参数)**

## java 描述语言

```
//npm install --save jimp
//import jimp library to the environment
var Jimp = require('jimp');

//User-Defined Function to read the images
async function main() {
    const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');
//rotate Function having rotation angle as 99, mode and callback function
  image.resize(1024, 768, Jimp.RESIZE_BEZIER, function(err){
      if (err) throw err;
  })
      .write('resize2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/52130d5ec97b20ecf0a67716addb0935.png)

**参考:**T2https://www.npmjs.com/package/jimp