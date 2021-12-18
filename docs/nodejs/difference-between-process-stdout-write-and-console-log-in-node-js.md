# process . stdout . write 和 console.log in Node.js

的区别

> 原文:[https://www . geesforgeks . org/process-stdout-write-and-console-log-in-node-js/](https://www.geeksforgeeks.org/difference-between-process-stdout-write-and-console-log-in-node-js/)

NodeJS 中的 **process.stdout.write** 和 **console.log** 都具有在控制台上显示消息的基本功能。基本上 **console.log** 实现 **process.stdout.write** 而 **process.stdout.write** 是一个缓冲区/流，会直接输出到我们的控制台。

**process . stdout . write 和 console.log in Node.js 的区别是:**

<figure class="table">

| Sl 没有。 | **流程。stdout** | **控制台。日志** |
| --- | --- | --- |
| one | It will print information continuously along with the data being retrieved without adding new lines. | Information obtained during printing is retrieved and new lines are added. |
| Two | Use **process.stdout** for the variable of the display object. | Use **console.log** to display many unreadable characters for a variable. |
| three | It takes only strings as arguments. Any other data type passed as a parameter will throw a type error. | It takes any JavaScript data type. |
| four | If we don't put the dash at the end, we will get a weird character after our string. | We don't need a line feed here, because it's already formatted, and the weird character really disappeared. |
| five | It can be used to print patterns because it does not add new lines. | We use it when we want to print the results on a new line. |
| six | 我们不能写多个字符串。例如:
`process.stdout.write("Hello","World");`
输出:这会给出一个类型错误。 | 我们可以写多个字符串。例如:
`console.log("Hello", "World");`
输出:这会在控制台打印 Hello World。 |
| seven | 我们不能搞联想。例如:
`process.stdout.write("Hello %s", "All");`
输出:这会给出一个类型错误。

 | 我们可以做联想。例如:
`console.log("Hello %s", "All");`
输出:这将在控制台打印 Hello All。 |

</figure>

**示例:**下面的示例是展示如何使用 **process.stdout.write**

## java 描述语言

```
<script>
    // For process.std.out 
    process.stdout.write("Hello");
    process.stdout.write("World");
    process.stdout.write("!!!");
</script>
```

**输出:**

```
HelloWorld!!!
```

**示例:**下面的示例是展示如何使用**控制台**

## java 描述语言

```
<script>
    // For console.log 
    console.log("Hello");
    console.log("World");
    console.log("!!!");
</script>
```

**输出:**

```
Hello
World
!!!
```