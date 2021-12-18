# Node.js path.parse()方法

> 原文:[https://www.geeksforgeeks.org/node-js-path-parse-method/](https://www.geeksforgeeks.org/node-js-path-parse-method/)

**path.parse()方法**用于返回一个属性表示给定路径的对象。此方法返回以下属性:

*   Root (root name)
*   Directory (directory name)
*   Base (file name with extension)
*   Ext (extension only)
*   Name (file name only)

每个平台的这些属性值可能不同。它在解析过程中忽略平台的尾随目录分隔符。

**语法:**

```
path.parse( path )
```

**参数:**该方法接受单参数**路径**，该路径保存该方法将解析的文件路径。如果此参数不是字符串值，它将引发类型错误。

**返回值:**这个方法返回一个包含路径细节的对象。

下面的例子说明了 node.js 中的 **path.parse()方法**:

**例 1:** 在 POSIX

```
// Node.js program to demonstrate the   
// path.parse() method

// Import the path module
const path = require('path');

path1 = path.parse("/users/admin/website/index.html");
console.log(path1);

path2 = path.parse("website/readme.md");
console.log(path2);
```

上

**输出:**

```
{
  root: '/',
  dir: '/users/admin/website',
  base: 'index.html',
  ext: '.html',
  name: 'index'
}
{
  root: '',
  dir: 'website',
  base: 'readme.md',
  ext: '.md',
  name: 'readme'
}
```

**示例 2:** 在 Windows 上

```
// Node.js program to demonstrate the   
// path.parse() method

// Import the path module
const path = require('path');

path1 = path.parse("C:\\users\\admin\\website\\index.html");
console.log(path1);

path2 = path.parse("website\\style.css");
console.log(path2);
```

**输出:**

```
{
  root: 'C:\\',
  dir: 'C:\\users\\admin\\website',
  base: 'index.html',
  ext: '.html',
  name: 'index'
}
{
  root: '',
  dir: 'website',
  base: 'style.css',
  ext: '.css',
  name: 'style'
}
```

**参考:**T2】https://nodejs.org/api/path.html#path_path_parse_path