# 如何在 Node.js 中使用带有服务静态文件的路由？

> 原文:[https://www . geeksforgeeks . org/how-to-use-routes-with-service-static-file-in-node-js/](https://www.geeksforgeeks.org/how-to-use-routes-with-serve-static-files-in-node-js/)

本文的目的是学习如何使用路由来服务 Node.js 中的静态文件，它有一个内置的 HTTP 模块来通过超文本传输协议(HTTP)传输数据，该协议支持以前难以使用的各种功能。借助本模块提供的功能，从子文档(文本、布局描述、图像、视频、脚本等)中完成文档的重建。)就完成了。

**设置不同网址的路由:**

## app.js

```
const http = require('http');   
const port = 3000;

// Creating Basic http Server
const server = http.createServer((req, res) => {    
  const url = req.url;  // requested url
  const method = req.method;  // requested path
  if(url === "/")  // setting response for / path 
  {
      res.end("Path /");
  }
  // setting response for /about path
  else if(url === "/about")  
  {
   res.end("Path /about");
  }
  else  
  {
      // setting response for all other paths
      res.end("Path not found");
  }
  console.log("Url entered "+url);
});
server.listen(port, () => {
  console.log(`Server running at http://:${port}/`);
});
```

**输出:**

![](img/5f4edfb8f6505f245f8cfb60b67f301e.png)

### **使用 HTTP 模块服务静态文件:**

## App.js

```
const http = require('http');

// File system module used for accessing files in nodejs
const fs = require("fs");  
const port = 3000;

// Helper function 
function readAndServe(path, res)   
{
    fs.readFile(path,function(err, data)
    {
        console.log(data);

        // res.setHeader('Content-Type', 'text/html');
        res.end(data);
    })
}
const server = http.createServer((req, res) => {  
  const url = req.url;
  const method = req.method;

  /* Serving static files on specific Routes */
  if(url === "/") 
  {
      readAndServe("./index.html",res) 

      /* The file named index.html will be sent 
         as a response when the index url is requested */
  }
  else if(url === "/about")
  {
      readAndServe("./about.html",res) 
      /*The about.html file will be sent as a response when 
        /about is requested */
  }
  else
  {
      res.end("Path not found"); 
      /* All paths other than / and /about will send an error as 
      a response */
  }
});
server.listen(port, () => {
  console.log(`Server running at http://:${port}/`);
});
```

## index.html

```
<!DOCTYPE html>
<!DOCTYPE html>
<html>
  <head>
    <title>index</title>
  </head>
  <body>
    <h2>Welcome To GeeksForGeeks</h2>
    <p>This is Index file</p>
    <p><a href="/about">
        Click to go to About Page
       </a>
    </p>
  </body>
</html>
```

## about.html

```
<!DOCTYPE html>
<html>
  <head>
    <title>Abput</title>
  </head>
  <body>
    <h2>Welcome To About Page</h2>
    <p><a href="/">
        Click to go to index
       </a>
    </p>
  </body>
</html>
```

**输出:**为不同路径指定的静态文件将得到相应的服务。

![](img/c24e368f22cd913063917ec2ed1b7d55.png)