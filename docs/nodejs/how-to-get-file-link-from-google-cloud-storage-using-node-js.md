# 如何使用 Node.js 从谷歌云存储获取文件链接？

> 原文:[https://www . geesforgeks . org/how-to-file-link-from-Google-cloud-storage-use-node-js/](https://www.geeksforgeeks.org/how-to-get-file-link-from-google-cloud-storage-using-node-js/)

要从 firebase 存储中获取文件的签名公共链接，我们需要一个对谷歌云存储中文件的引用。由于我们在存储中只有该文件的路径，因此我们首先需要创建对该对象的引用，然后获取该文件的签名链接。

**使用文件路径生成指向存储中文件的公共链接的步骤:**

1.  使用存储对象上的 bucket()和 file()方法从 [@google-cloud/storage](https://www.npmjs.com/package/@google-cloud/storage) 获取对存储的引用。
2.  在第一步中创建的引用对象上，使用 [getSignedUrl](https://googleapis.dev/nodejs/storage/latest/File.html#getSignedUrl) 方法为该文件生成一个签名的公共链接。

**模块安装:**使用以下命令安装模块:

```js
npm install @google-cloud/storage
```

方法 getSignedUrl()将一个*配置*对象作为输入任务，并返回一个 Promise，该 Promise 使用下载 Url 进行解析，或者如果提取失败(包括该对象不存在)则拒绝。

**示例:文件名:index.js**

## java 描述语言

```js
// Imports the Google Cloud client library
const {Storage} = require('@google-cloud/storage');

// Creates a client
const storage = new Storage();

var bucketName = 'geeksforgeeks'; 
var fileName = 'gfg.png';

// Create a reference to the file to generate link
var fileRef = storage.bucket(bucketName).file(fileName);

fileRef.exists().then(function(data) {
  console.log("File in database exists ");
});

const config = {
  action: 'read',

  // A timestamp when this link will expire
  expires: '01-01-2026',
};

// Get the link to that file
fileRef.getSignedUrl(config, function(err, url) {
  if (err) {
    console.error(err);
    return;
  }

  // The file is now available to
  // read from this URL
  console.log("Url is : " + url);
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

> 数据库中存在文件
> 网址为:https://storage.googleapis.com/geeksforgeeks/gfg.png?x-Google-算法=[令牌]