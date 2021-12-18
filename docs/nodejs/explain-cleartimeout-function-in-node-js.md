# 解释 Node.js 中的 clearTimeout()函数

> 原文:[https://www . geesforgeks . org/explain-clear time out-node 中的函数-js/](https://www.geeksforgeeks.org/explain-cleartimeout-function-in-node-js/)

在 node.js 中，有一个计时器模块，用于调度计时器并在未来某个时间段执行某种功能。

**setTimeout()方法:**用于调度功能在提供的毫秒后执行，下面是 setTimeout()方法的一个简单例子。

**示例:**脚本标签内部的 setTimeout 正在注册一个 3000 毫秒后要执行的函数，函数内部只有一个报警。

## HTML

```js
<!DOCTYPE html>
<html>

<body>
    <script>
        function alertAfter3Seconds() {
            alert("Hi, 3 Second completed!");
        }
        setTimeout(alertAfter3Seconds, 3000);
    </script>
</body>

</html>
```