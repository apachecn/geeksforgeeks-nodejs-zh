# 如何使用 Node.js 在 JSON 文件中添加数据？

> 原文:[https://www . geesforgeks . org/how-add-data-in-JSON-file-use-node-js/](https://www.geeksforgeeks.org/how-to-add-data-in-json-file-using-node-js/)

[<u>【JSON】</u>](https://www.geeksforgeeks.org/javascript-json/)代表 Javascript 对象符号。它是应用程序之间交换信息最简单的方式之一，通常被网站/应用程序接口用来通信。关于 Node.js 的入门，请参考[](https://www.geeksforgeeks.org/introduction-to-nodejs/)<u>这篇文章。</u>

<u>首先，您需要确保您期望的 JSON 文件不会消耗大量内存。对于估计消耗约 500 兆字节的数据，这种方法效率不高，您应该考虑使用数据库系统。</u>

1.  <u>Node.js 有一个名为 **fs** 的内置模块，它代表文件系统，使用户能够以建模的方式与文件系统交互。要使用它，请在服务器程序中键入下面的代码。</u>

    ```
    const fs = require('fs');
    ```

    <u>fs 模块的文档可以在 [<u>这里</u>](https://nodejs.org/api/fs.html#fs_file_system) <u>找到。</u></u>

2.  <u>我们可以从创建一个 JSON 文件开始，对于这个例子，它将包含一个 id、一个名字和一个城市。请注意，您可以拥有任意多的键值对，但是我们首先使用三个。</u>

     <u>```
    {
        "id": 1,
        "name": "John",
        "city": "London"
    }
    ```

    让我们将这个 JSON 文件命名为 data.json。</u> 
3.  <u>现在我们有了一个可以写入的 JSON 文件，首先我们将创建一个 JavaScript 对象来访问该文件。为此，我们将使用[<u>fs . readfilesync()</u>](https://nodejs.org/api/fs.html#fs_fs_readfilesync_path_options)，它将为我们提供原始格式的数据。为了得到 JSON 格式的数据，我们将使用 [<u>JSON.parse()</u>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse) 。因此，我们服务器端的代码如下所示:</u>

    ```
    var data = fs.readFileSync('data.json');
    var myObject= JSON.parse(data);
    ```

4.  <u>现在我们已经准备好了对象，让我们假设我们有一个要添加的键值对数据:</u>

    ```
    let newData = {
        "country": "England"
    } 
    ```

    <u>我们需要使用我们的对象(即 myObject)来添加这些数据。我们将通过使用。push()方法如下:</u>

    ```
    myObject.push(newData);
    ```

5.  <u>要将新数据写入我们的 JSON 文件，我们将使用 [<u>fs.writeFile()</u>](https://nodejs.org/api/fs.html#fs_fs_writefile_file_data_options_callback) ，它将 JSON 文件和要添加的数据作为参数。请注意，在写入对象之前，我们必须先将它转换回原始格式。这将使用 [<u>JSON.stringify()</u>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify) 方法来完成。</u>

    ```
    var newData = JSON.stringify(myObject);
    fs.writeFile('data.json', newData, err => {
        // error checking
        if(err) throw err;

        console.log("New data added");
    }); 
    ```

    <u>现在，我们的 data.json 文件如下所示:</u>

    ```
    {
        "id": 1,
        "name": "John",
        "city": "London",
        "country": "England"
    }
    ```

<u>**示例:**上面示例的 index.js 代码。</u>

## <u>index.js</u>

```
// Requiring fs module
const fs = require("fs");

// Storing the JSON format data in myObject
var data = fs.readFileSync("data.json");
var myObject = JSON.parse(data);

// Defining new data to be added
let newData = {
  country: "England",
};

// Adding the new data to our object
myObject.push(newData);

// Writing to our JSON file
var newData2 = JSON.stringify(myObject);
fs.writeFile("data2.json", newData2, (err) => {
  // Error checking
  if (err) throw err;
  console.log("New data added");
});
```

<u>**输出:**
![](img/72e512f6ff33cd37f41d614953e4c7e9.png)</u>