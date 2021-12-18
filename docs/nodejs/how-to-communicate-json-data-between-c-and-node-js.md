# 如何在 C++和 Node.js 之间进行 JSON 数据的通信？

> 原文:[https://www . geeksforgeeks . org/how-communication-JSON-c 与节点之间的数据-js/](https://www.geeksforgeeks.org/how-to-communicate-json-data-between-c-and-node-js/)

在本文中，我们将使用 JSON 数据在两个名为 C++和 Node.js 的程序之间进行通信，我们可以使用一种通用的文本格式进行通信，但是文本格式会包含很多复杂性。然而，JSON 是轻量级的，易于使用。JSON 是独立于语言的，因此可以被任何编程语言使用。

**使用 C++的序列化:**序列化是将编程数据转换为 JSON 文本的过程。在 C++中，没有供 JSON 读者使用的内置库。我们需要将头文件添加到我们的项目中。你基本上需要 C++项目的 json.hpp 文件来完成下面描述的工作。

让我们使用 C++代码生成一个 JSON 文件，如下所示。

## c++

```js
#include<iostream>
#include<ofstream>
#include "json.hpp"

// For convenience
using json = nlohmann::json;
using namespace std;

int main(){
  json obj;
  obj["Name"] = "Inshal";
  obj["Roll no"] = "42";
  obj["Dept"] = "CSE";
  obj["cgpa"] = "7.99";

  ofstream file("output.json");
  file<<setw(4)<<obj<<endl;
  file.close();
  cout<<"JSON Object Created:";
  for (auto& element : obj) {
    cout << element << '\n';
  }
}
```