# 在 Node.js 中搭建一个简单的静态文件 web 服务器

> 原文:[https://www . geesforgeks . org/build-a-simple-static-file-web-server-in-node-js/](https://www.geeksforgeeks.org/build-a-simple-static-file-web-server-in-node-js/)

在本文中，我们将构建一个静态文件 web 服务器，它将列出目录中的所有文件，并在单击文件名时显示文件内容。创建静态文件服务器的步骤如下:

*   **Step 1:** Import the necessary modules and define [MIME type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types) to help the browser know the file type being sent.

## JavaScript

```
// Importing necessary modules
const http = require('http');
const url = require('url');
const fs = require('fs');
const path = require('path');

// Port on which the server will create
const PORT = 1800;

// Maps file extension to MIME types which
// helps the browser to understand what to
// do with the file
const mimeType = {
    '.ico': 'image/x-icon',
    '.html': 'text/html',
    '.js': 'text/javascript',
    '.json': 'application/json',
    '.css': 'text/css',
    '.png': 'image/png',
    '.jpg': 'image/jpeg',
    '.wav': 'audio/wav',
    '.mp3': 'audio/mpeg',
    '.svg': 'image/svg+xml',
    '.pdf': 'application/pdf',
    '.doc': 'application/msword',
    '.eot': 'application/vnd.ms-fontobject',
    '.ttf': 'application/font-sfnt'
};
```

*   **Step 2:** Create a server at the designated port (such as 1800).

## Javascript

```
// Creating a server and listening the port 1800
http.createServer( (req, res) => {

}).listen(PORT);
```

*   **Step 3:** We will list all files in the directory in response to **URL "/**. We will limit this article to the current working directory. Add the following code to the function call of the server.

## Javascript

```
// Parsing the requested URL
const parsedUrl = url.parse(req.url);

// If requested url is "/" like "http://localhost:8100/"
if(parsedUrl.pathname==="/") {
    var filesLink="<ul>";
    res.setHeader('Content-type', 'text/html');
    var filesList=fs.readdirSync("./");

    filesList.forEach(element => {
        if(fs.statSync("./"+element).isFile()) {
            filesLink +=`<br/><li><a href='./${element}'>
                ${element}
            </a></li>` ;        
        }
    });
    filesLink+="</ul>";

    res.end("<h1>List of files:</h1> " + filesLink);
}
```

*   **Step 4:** Preprocess the requested file path name to avoid directory traversal (such as http://localhost: 1800/../fileoutofcontext.txt) and replace it with "../'with''.

## Javascript

```
/* processing the requested file pathname to
avoid directory traversal like,
http://localhost:1800/../fileOutofContext.txt
by limiting to the current directory only */
const sanitizePath = 
path.normalize(parsedUrl.pathname).replace(/^(\.\.[\/\\])+/, '');

let pathname = path.join(__dirname, sanitizePath);
```