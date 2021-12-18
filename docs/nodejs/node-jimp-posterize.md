# 节点 Jimp |后置

> 原文:[https://www.geeksforgeeks.org/node-jimp-posterize/](https://www.geeksforgeeks.org/node-jimp-posterize/)

**简介**:**后置()**功能是 Nodejs | Jimp 中的一个内置功能，应用了 **n** 级别的后置效果。
**语法:**

```
posterize(n, cb)
```

**参数:**

*   **n**–该参数存储对比度调整量，最小阈值为 2
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
// sepia function
  image.posterize(4)
  .write('posterize1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/6531373fa8b0e3d00c8b7f92c40330ce.png)

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
// opaque function using callback function
  image.posterize(5, function(err){
    if (err) throw err;
  })
  .write('posterize2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/526f5ea51d051fd3d3eede3ec1ac4f8b.png)

**参考:**T2https://www.npmjs.com/package/jimp