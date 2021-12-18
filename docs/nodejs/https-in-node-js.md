# node . js 中的 HTTPS

> 原文:[https://www.geeksforgeeks.org/https-in-node-js/](https://www.geeksforgeeks.org/https-in-node-js/)

**HTTP:** 当数据以 HTTP 协议传输时，它只是以明文格式传输。
**HTTPS:** 当请求从浏览器传输到网络服务器时，它只是进行加密，因此很难嗅探到这些信息。它主要在两件事情上起作用:

*   安全套接字层
*   传输层安全性

**两者都使用 PKI(公钥基础设施)**

*   如果你买不起 SSL 证书，那么另一个选择是有很多支付服务可以为你提供一个应用编程接口来集成到你的网站中，也就是说，你可以让你的网站在一个非安全的通道(HTTP)上，只要有支付，然后只是重定向用户到该支付网关服务。
*   HTTPS 是 Node.js 中的一个独立模块，用于通过安全通道与客户端进行通信。HTTPS 协议是 SSL/TLS(安全 HTTP 协议)之上的 HTTP 协议。

这个附加层有各种优点:

*   完整性和保密性得到保证，因为连接是以非对称方式加密的。
*   我们通过拥有密钥和证书来获得认证。

使用节点设置 HTTPS 服务器的示例。Js 如下:

*   我们将首先创建一个 homepage.html 文件，这个 homepage.html 文件将有一个创建网页的 HTML 代码，即当用户要求或输入相同的网址时将显示的页面。
*   homepage.css 文件也将有一个资源主页
*   当浏览器试图获取资源 homepage.css 时，它会把它扔给服务器，服务器会创建一个响应头，这样浏览器就知道如何解析文件了。
*   下面显示的代码写在保存为的第三个文件中。js 文件。

## java 描述语言

```js
<script>
(function() {

// Reading and writing to files in Node.js
// working with directories or file system
var fs = require("fs"); 

// Responsible for creating HTTPS server
// taking options for the server
// options like where your certificates 
// and private key files are located
// also take actual request and response server
// code for parsing web pages from files
var https = require("https");

// Helps with mimetypes in creating our response header
var path = require("path"); 

// "text/css" is added in response header 
// so browser knows how to handle it 
var mimetypes = {
    "css":"text/css",
    "html":"text/html"
};

// Options is used by the servers
// pfx handles the certificate file
var options = {
    pfx: fs.readFileSync("ssl/cert.pfx"),
    passphrase: "encrypted"
};

var server = https.createServer(options, function(request, response) {

    // If the url is empty
    if (request.url == "" || request.url == "/") {
        request.url = "homepage.html";
    }

    // __dirname is the directory where we are getting
    // these files from __dirname holds the file route
    // request.url is the index.html we made earlier
    // function is the callback function that holds two
    // parameters
    fs.readFile(__dirname + "/" + request.url, function(err, content) {
        if (err) { 
            console.log("Error: " + err);
        } 
        else { 

            // 200 is code for OK
            // content-Type is the object or the content header
            response.writeHead(200, 
    {'Content-Type':mimetypes[path.extname(request.url).split(".")[1]]});
            response.write(content); 
        }

        // This will send our response back to the browser
        response.end();
    });
});

server.listen("port number", "IP Address", function() {

    console.log("Server has started!");
}); 

})();
</script>
```

**输出:**无论给服务器的端口号和 IP 地址是什么，只要请求，它都会执行那个唯一的网页。这个网页将是一个 HTTPS。