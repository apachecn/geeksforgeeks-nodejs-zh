# 节点 Jimp |旋转

> 原文:[https://www.geeksforgeeks.org/node-jimp-rotate/](https://www.geeksforgeeks.org/node-jimp-rotate/)

**简介**
rotate()函数是 Nodejs | Jimp 中的一个内置函数，顺时针旋转图像，图像的尺寸保持不变。
**语法:**

```
rotate(r, mode, cb)
```

**参数:**

*   **r**–该参数存储图像的旋转角度。
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

// rotate Function having a rotation as 55
  image.rotate(55)
  .write('rotate1.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/9a8917116277839170d7034a4c147b49.png)

**示例 2:带模式和 cb(可选参数)**

## java 描述语言

```
// npm install --save jimp
// import jimp library to the environment
var Jimp = require('jimp');

// User-Defined Function to read the images
async function main() {
    const image = await Jimp.read
('https://media.geeksforgeeks.org/wp-content/uploads/20190328185333/gfg111.png');

// rotate Function having rotation angle as 99, mode and callback function
    image.rotate(99, Jimp.RESIZE_BEZIER, function(err){
        if (err) throw err;
    })
        .write('rotate2.png');
}

main();
  console.log("Image Processing Completed");
```

**输出:**

![](img/6e2b76fe5c290c8b6b0438803fb9cf8b.png)

**参考:**T2https://www.npmjs.com/package/jimp