# 如何使用 Node.js 将字符串数组的每个元素拆分成不同的类别？

> 原文:[https://www . geesforgeks . org/如何使用节点 js/](https://www.geeksforgeeks.org/how-to-split-each-element-of-an-array-of-strings-into-different-categories-using-node-js/) 将字符串数组中的每个元素拆分成不同的类别

任务是将字符串数组的每个元素分成不同的类别。

**示例:**

> ***输入数组:*** 常量输入= ['abc '，' def '，' ghi '，' jkl '，' mno '，' pqr '，' stw '，' *xyz']*
> 
> ***类别数组:*** 常量类别= ['a '，' b '，' c']
> 
> ***分割大小:*** 常量分割 _ 大小= 3
> 
> ***输出:***
> 
> a: [ 'abc '，' def '，' ghi' ]，
> 
> b: [ 'jkl '，' mno '，' pqr' ]，
> 
> c:[' STW '，' XYZ ']
> 
> ]

**进场:**

*   初始化一个存储类别的对象，并初始化一个保存类别索引的变量**索引**。
*   开始遍历数组**并根据拆分大小拆分**。
*   将新的分割数组分配给给定的类别，**增加**索引。

下面给出了上述方法的代码。

## java 描述语言

```
function split_array (array, categories, split_size) {
    // Initialize empty array
    var chunks = [];

    // Initialize index equal to zero to keep track of categories
    var index=0;

    // Traverse the array according to the split size
    for(var i=0; i<array.length; i+=split_size){
        // Slicing the split_size array from i
        var temp = array.slice(i,i+split_size);

        // Assigning the sliced array to the category
        chunks[categories[index]] = temp;

        // Increment index to keep track of categories
        index++;
    }

    // return the final array
    return chunks;
}
//input array
const input =  ['abc', 'def', 'ghi', 'jkl', 'mno', 'pqr', 'stw', 'xyz']
//categories array
const categories = ['a', 'b', 'c']
const split_size = 3; //split size

//calling the function
const output = split_array(input,categories,split_size);

console.log(output) //printing the array
```

**输出:**

```
[
    a: ["abc", "def", "ghi"]
    b: ["jkl", "mno", "pqr"]
    c: ["stw", "xyz"]
]
```