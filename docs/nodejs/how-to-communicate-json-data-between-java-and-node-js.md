# 【Java 和 Node.js 之间如何进行 JSON 数据的通信？

> 原文:[https://www . geeksforgeeks . org/how-communication-JSON-数据在 java 和节点之间-js/](https://www.geeksforgeeks.org/how-to-communicate-json-data-between-java-and-node-js/)

所以这里我们将使用 JSON 在两个叫做 Java 和 Node.js 的程序之间进行通信，我们可以使用一种通用的文本格式进行通信，但是文本格式会包含很多复杂性。然而，JSON 是轻量级的，易于使用。JSON 是独立于语言的，因此可以被任何编程语言使用。

**使用 Java 的序列化:**序列化是将编程数据转换为 JSON 文本的过程。在 Java 中，没有内置的 JSON 阅读器库。我们需要要么在我们的等级项目中添加一个依赖项，要么下载 jar 文件。我们有杰克逊图书馆和简单 json 图书馆。这里使用了简单的 json 库。

让我们使用 java 代码生成一个 JSON 文件，如下所示。

## Java 语言(一种计算机语言，尤用于创建网站)

```js
import org.json.simple.JSONObject;
import java.io.FileWriter;
import java.io.IOException;
public class MyClass {
    public static void main(String args[]) {
      JSONObject obj = new JSONObject();

      obj.put("name", "Inshal Khan");
      obj.put("Roll no", new Integer(42));
      obj.put("cgpa", new Double(7.99));
      try {
        FileWriter file = new FileWriter("E:/output.json");
        file.write(obj.toJSONString());
        file.close();
      } catch (IOException e) {

         e.printStackTrace();
      }
      System.out.println("JSON file created: "+jsonObject);
    }
}
```

**输出:**

```js
JSON file created:{
"name":"Inshal Khan",
"Roll no":"42",
"cgpa":"7.99"}
```

**使用 Node.js 反序列化:**

## java 描述语言

```js
'use strict';

const fs = require('fs');

fs.readFile('output.json', (err, data) => {
    if (err) throw err;
    let obj = JSON.parse(data);
    console.log(obj);
});

console.log('File Reading completed');
```

**输出:**

```js
JSON file created:{
"name":"Inshal Khan",
"Roll no":"42",
"cgpa":"7.99"}
```