# 如何使用 node.js 中的文件 url 从 firebase 中删除文件？

> 原文:[https://www . geeksforgeeks . org/如何从 firebase-use-file-URL-in-node-js 中删除文件/](https://www.geeksforgeeks.org/how-to-delete-file-from-the-firebase-using-file-url-in-node-js/)

要从 firebase 存储中删除一个文件，我们需要一个引用来将该文件存储在存储中。由于我们只有文件 URL，我们需要在 firebase 存储中创建文件的引用对象，然后删除该文件。

使用文件 URL 删除文件可以分两步完成–

1.  从 firebase.storage。
2.  Use the [reffromul](https://firebase.google.com/docs/reference/js/firebase.storage.Storage#reffromurl) method to obtain the reference to the storage. Delete the file using the reference to the file in the storage obtained from step 1.

方法 **refFromUrl** 返回对该文件的引用，可以将两种类型的文件 Url 作为输入–

1.  页:1
2.  Download the URL from the object metadata.

**示例 1:** 使用 refFromURL 方法从给定的文件 URL 中删除文件。

## Javascript

```js
var fileUrl = 
'https://firebasestorage.googleapis.com/b/bucket/o/images%20geeksforgeeks.jpg';

// Create a reference to the file to delete
var fileRef = storage.refFromURL(fileUrl);

console.log("File in database before delete exists : " 
        + fileRef.exists())

// Delete the file using the delete() method 
fileRef.delete().then(function () {

    // File deleted successfully
    console.log("File Deleted")
}).catch(function (error) {
    // Some Error occurred
});

console.log("File in database after delete exists : "
        + fileRef.exists())
```