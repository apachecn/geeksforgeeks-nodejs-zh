# 节点 Jimp | Blit

> 原文:[https://www.geeksforgeeks.org/node-jimp-blit/](https://www.geeksforgeeks.org/node-jimp-blit/)

**简介**
blit()函数是 Nodejs 中的一个内置函数。它用于组合两个位图模式。| Jimp，它使用布尔函数将几个位图组合成一个。

**参数:**

*   **src**–该参数存储要进行 blit 的图像源。
*   **x**–该参数取 x 位置对图像进行块传输。
*   **y**–该参数取 y 位置对图像进行 blit。
*   **srcx(可选)**–该参数取 x 位置，从该位置裁剪源图像。
*   **srcy(可选)**–该参数取 y 位置，从该位置裁剪源图像。
*   **srcw(可选)**–此参数采用裁剪源图像的宽度。
*   **srch (optional)** – This parameter takes the height to which to crop the source image.

    **输入图像:**
    ![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

    ![](img/290a52d70280cfd5211f5083f062f10e.png)

    **例 1:**

    ```js
    // npm install --save jimp
    // import jimp library to the environment
    var Jimp = require('jimp');

    // User-Defined Function to read the images
    async function main() {
      const image1 = await Jimp.read('../gfg.png');
      const image2 = await Jimp.read('../gfg1.png');

      // call to blit function 
      image1.blit(image2, 20, 40)

      // write image
      .write('blit1.png');
      console.log('Image Processing Completed');
    }
    main();
    ```

    **输出:**
    ![](img/cb1dfdae6a4e9cc047938506a2d08544.png)

    **例 2:**

    ```js
    // npm install --save jimp
    // import jimp library to the environment
    var Jimp = require('jimp');

    // User-Defined Function to read the images
    async function main() {
      const image1 = await Jimp.read('../gfg.png');
      const image2 = await Jimp.read('../gfg1.png');

      // call to blit function along with optional parameters
      image1.blit(image2, 20, 40, 130, 30, 440, 80);

      // write image
      .write('blit2.png');
      console.log('Image Processing Completed');
    }
    main();
    ```

    **输出:**
    ![](img/eab8d7fcfa508a438bbd43bcbd302d1f.png)

    **参考:**T2】https://www.npmjs.com/package/jimp