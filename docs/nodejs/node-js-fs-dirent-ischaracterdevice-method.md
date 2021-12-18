# Node.js fs。Dirent.isCharacterDevice()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-dirent-isracterdevice-method/](https://www.geeksforgeeks.org/node-js-fs-dirent-ischaracterdevice-method/)

**fs。方法是类 **fs 的内置应用编程接口。**文件系统**模块中的目录**，用于检查特定目录是否描述了字符设备。**

**语法:**

```js
const dirent.isCharacterDevice()
```

**参数:**此方法不接受任何参数。

**返回值:**如果特定方向描述字符设备，则该方法返回真，否则返回假。

下面的程序说明了**方法在 Node.js 中的使用:**

**示例 1:**
**文件名:index.js**

## java 描述语言

```js
// Node program to demonstrate the
// dirent.isCharacterDevice() method
const fs = require('fs');

// Initiating async function
async function stop(path) {

    // Creating and initiating directory's
    // underlying resource handle
    const dir = await fs.promises.opendir(path);

    // Synchronously reading the directory's
    // underlying resource handle using
    // readSync() method
    for (var i = 0; i <= 3; i++) {

        // Checking if the particular dirent
        // is Character device or not by using
        // isCharacterDevice() method
        const value = (dir.readSync())
                .isCharacterDevice();

        // Display the result
        console.log(dir.readSync());
        console.log(value);
    }
}

// Catching error
stop('./').catch(console.error);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Dirent { name: 'cert.cer', [Symbol(type)]: 1 }
false
Dirent { name: 'certificate1.cer', [Symbol(type)]: 1 }
false
Dirent { name: 'filename.txt', [Symbol(type)]: 1 }
false
Dirent { name: 'GFG.java', [Symbol(type)]: 1 }
false
```

**示例 2:**
**文件名:index.js**

## java 描述语言

```js
// Node program to demonstrate the
// dirent.isCharacterDevice() method
const fs = require('fs');

// Initiating async function
async function stop(path) {

    // Creating and initiating directory's
    // underlying resource handle
    const dir = await fs.promises
        .opendir(new URL('file:///F:/'));

    // Synchronously reading the directory's
    // underlying resource handle using
    // readSync() method
    for (var i = 0; i <= 3; i++) {

        // Checking if the particular dirent
        // is Character device or not by
        // using isCharacterDevice() method
        const value = (dir.readSync())
                    .isCharacterDevice();

        // Display the result
        console.log(dir.readSync());
        console.log(value);
    }
}

// Catching error
stop('./').catch(console.error);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Dirent { name: 'adonis_auth_api', [Symbol(type)]: 2 }
false
Dirent { name: 'Android Template', [Symbol(type)]: 2 }
false
Dirent { name: 'Calander', [Symbol(type)]: 2 }
false
Dirent { name: 'first-app', [Symbol(type)]: 2 }
false
```

**参考:**T2【https://nodejs . org/dist/latest-v 12 . x/docs/API/fs . html # fs _ dirent _ ischarterdeviceT4】