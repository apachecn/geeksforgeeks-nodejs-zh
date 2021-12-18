# Node.js 木偶师

> 原文:[https://www.geeksforgeeks.org/node-js-puppeteer/](https://www.geeksforgeeks.org/node-js-puppeteer/)

Puppeteer 是 Node.js 的开源库，通过提供对开发人员工具的控制来帮助自动化和简化开发。它允许开发人员编写和维护简单的自动化测试。大多数在浏览器中手动完成的事情都可以通过使用木偶师来完成。木偶师的特点是–

*   它可以作为一个网络涂鸦器。
*   它可以生成页面截图。
*   它可以制作网页的 pdf。
*   它可以自动化测试和表单提交的过程。
*   它可以用来测试 Chrome 扩展。
*   它为测试创建了一个更新的自动化环境，这样测试就可以直接在浏览器中运行(谷歌 Chrome)。
*   它创建自己的浏览器用户配置文件，每当运行该库时都会清除该文件。

**安装:**第一步，用 **package.json** 文件初始化应用程序。因此，运行以下命令–

```js
npm init
```

要安装库，请编写以下命令–

```js
npm install puppeteer --save
```

安装后，我们的 package.json 文件将看起来像–

```js
{
  "name": "day37",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "Pranjal Srivastava",
  "license": "ISC",
  "dependencies": {
    "puppeteer": "^3.1.0"
  }
}

```

**实现:**木偶师基本上创建一个**浏览器**的实例，然后操纵浏览器的页面。让我们看一个木偶师的实现，用于**导航到网页**-

```js
const puppeteer = require('puppeteer');

(async () => {
    const browser = await puppeteer.launch();
    const page = await browser.newPage();
    await page.goto('https://www.geeksforgeeks.org/');

    await browser.close();
})();
```

首先，我们正在创建一个浏览器实例，并允许木偶师库启动。这里使用
**browser.newPage()** 新建一个页面，然后导航到 **page.goto()** 中提供的 URL 作为参数。最后 **browser.close()** 关闭整个运行过程。我们的 javascript 文件的名称是 **index.js** ，因此，要运行该应用程序，只需在终端中键入以下命令–

```js
node index.js
```

上面的代码将在您的系统中启动默认的网络浏览器，并导航到 https://www.geeksforgeeks.org/

**拍摄网页截图:**要拍摄网页截图，请编写以下代码–

```js
const puppeteer = require('puppeteer');

(async () => {
    const browser = await puppeteer.launch();
    const page = await browser.newPage();
    await page.goto('https://www.geeksforgeeks.org/');
    await page.screenshot({ path: 'GFG.png' });
    await browser.close();
})();
```

这里，**page . screen**方法会把页面截图，用文件名**GFG.png**保存。上面的代码将首先打开页面，然后拍摄页面的截图。

使用以下命令运行应用程序–

```js
node index.js
```

上述代码的输出将是–
![](img/479693502c59d933b82df346cba8e31a.png)

**要为给定网站创建 PDF:**要创建网站的 PDF，请编写以下代码–

```js
const puppeteer = require('puppeteer');

(async () => {
    const browser = await puppeteer.launch();
    const page = await browser.newPage();
    await page.goto('https://www.geeksforgeeks.org/');
    await page.pdf({ path: 'gfg.pdf' });

    await browser.close();
})();
```

在这里， **page.pdf()** 将创建给定网站的 pdf，并以**gfg.pdf**的名称保存。使用以下命令运行应用程序–

```js
node index.js
```

上面的代码将生成页面的 PDF。
上述代码的输出将是–
![](img/049fc4778762d67b023afb4bcd137fa4.png)

**获取打开网页的尺寸:**要获取页面的尺寸，请编写以下代码–

```js
const puppeteer = require('puppeteer');

(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();
  await page.goto('https://www.geeksforgeeks.org/');

  const getDimensions = await page.evaluate(() => {
    return {
      width: document.documentElement.clientWidth,
      height: document.documentElement.clientHeight
    };
  });

  console.log(getDimensions);

  await browser.close();
})();
```

在这里， **getDimensions** 将首先评估页面，然后返回页面的宽度和高度。属性**客户端宽度**和**客户端高度**分别用于获取页面的宽度和高度。使用以下命令运行应用程序–

```js
node index.js
```

上述代码的输出将是–

```js
{
width: 1366px,
height: 695px
}

```

**默认设置:**

*   **它以无头模式运行:**浏览器的无头模式提供自动化测试和服务器环境。这是一种在没有完整图形用户界面的情况下运行浏览器的方式。在无头模式下使用浏览器的优势在于它可以连续运行 javascript 测试。无头浏览器的默认设置是木偶戏中的**真**。要使其为假，请编写以下代码–

    ```js
    const browser = await puppeteer.launch({ headless: false })
    ```

*   **It runs the specific version of Chrome:** By default, puppeteer uses the specific version of Chrome. If you want to run some other version of code, then write the following –

    ```js
    const browser = await puppeteer.launch({ executablePath:
                 '/path/to/your/version/of/Chrome' });
    ```

    在这里， **executablePath** 属性允许您指定 Chrome 版本的路径。

**结论:**在本文中，我们了解了 Node.js 的**瞳孔器**库，也了解了这个库的各种特性。我们已经看到了它的实现和这个库使用的默认设置。