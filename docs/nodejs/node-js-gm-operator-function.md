# Node.js GM 运算符()函数

> 原文:[https://www.geeksforgeeks.org/node-js-gm-operator-function/](https://www.geeksforgeeks.org/node-js-gm-operator-function/)

**运算符()函数**是 GraphicsMagick 库中的一个内置函数，用于对图像通道应用数学、按位或值运算符。如果运算结果为负，则结果被重置为零，如果运算结果溢出到可用范围，则结果被设置为最大可能值。
**语法:**

```
operator( channel, operator, rvalue[%] )
```

**参数:**该函数接受上面提到的和下面描述的四个参数:

*   **通道:**此参数用于从红色、绿色、蓝色、不透明度、哑光、青色、洋红色、黄色、黑色、全部或灰色中指定通道的值。通道值**全部**修改颜色通道，不修改通道的不透明度。
*   **运算符:**此参数用于指定运算符的值。
    经营者名单及其说明如下:
    *   **加法:**加法运算符的结果给出了加到通道值上的右值。
    *   **和:**And 运算符的结果给出了带通道值的右值的逻辑“与”。
    *   **赋值:**赋值运算符给出所提供值的结果。
    *   **深度:**深度运算符的结果给出了调整后的通道值，以便它可以(近似)存储在指定的位数中，而不会有额外的损失。
    *   **除:**除运算符给出的结果是通道值除以右值。
    *   **Gamma:**Gamma 运算符将结果作为通过右值调整的通道值 Gamma 给出。
    *   **lsshift:**lsshift 运算符将结果作为通道值按位左移右值位。
    *   **Log:**Log 运算符给出的计算结果为 Log(值*右值+1)/log(右值+1)。
    *   **最大值:**如果右值大于值，最大值运算符给出分配给右值的结果。
    *   **最小值:**如果右值小于值，则最小值运算符给出指定给右值的结果。
    *   **乘法:**乘法运算符给出通道值乘以右值的结果。
    *   **求反:**求反运算符给出的结果是通道值的倒数(就像底片一样)。
    *   **Or:**Or 运算符将结果作为带通道值的右值的逻辑 Or 给出。
    *   **幂:**幂运算符给出的结果计算为幂(值，右值)。
    *   **Rshift:**Rshift 运算符将结果作为通道值按位右移右值位给出。
    *   **减法:**减法运算符给出的结果是通道值减去右值。
    *   **阈值:**如果通道值大于右值，阈值运算符给出的结果为最大值(白色)，如果小于或等于右值，则为最小值(黑色)。
    *   **阈值-白色:**如果通道值大于右值，阈值-白色运算符给出的结果为最大值(白色)，如果小于或等于右值，则结果不变。
    *   **阈值-白色-求反:**如果通道值大于右值，阈值-白色-求反运算符将结果设置为黑色，如果小于或等于右值，则结果不变。
    *   **阈值-黑色:**如果通道值小于右值，阈值-黑色运算符将结果作为最小值(黑色)给出，如果大于或等于右值，则结果不变。
    *   **阈值-黑色-求反:**如果通道值小于右值，阈值-黑色-求反运算符将结果设置为白色，如果大于或等于右值，则结果不变。
    *   **异或:**异或运算符给出的结果是右值与通道值的逻辑异或。
    *   **噪声-高斯:**噪声-高斯算子给出的结果是根据右值指定的强度用高斯噪声调制的当前通道值。
    *   **噪声-脉冲:**噪声-脉冲运算符给出的结果是根据右值指定的强度用脉冲噪声调制的当前通道值。
    *   **噪声-拉普拉斯:**噪声-拉普拉斯算子给出的结果是根据右值指定的强度用拉普拉斯噪声调制的当前通道值。
    *   **噪声-乘法:**噪声-乘法算子给出的结果是根据右值指定的强度用乘法高斯噪声调制的当前通道值。
    *   **噪声-泊松:**噪声-泊松算子给出的结果是根据右值指定的强度用泊松噪声调制的当前通道值。
    *   **Noise-Random:**Noise-Random 运算符根据右值指定的强度，将结果作为随机(均匀分布)噪声调制的当前通道值给出。
    *   **噪声-均匀:**噪声-均匀算子给出的结果是根据右值指定的强度应用均匀噪声的通道值。
*   **右值:**此参数用于指定浮点或整数值范围内的值。通常，右值将在 0 到 MaxRGB 的范围内，其中 MaxRGB 是 GraphicsMagick 构建支持的最大量程值(255、65535 或 4294967295)，但该范围之外的值对某些算术运算很有用。参数值在使用前会被舍入为正整数值。如果我们添加一个百分比(%)符号，那么参数的范围是 0 到 100。

**返回值:**该函数返回 GraphicsMagick 对象。
**例 1:**

## java 描述语言

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke operator function with
// Channel as 'Green', Operator
// as 'And' and rValue(%) as 55
.operator('Green', 'And', 55, true)

// Process and Write the image
.write("operator-and1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/7f410d8aebd1de2015e5fdcdb10e1b75.png)

**例 2:**

## java 描述语言

```
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke operator function with
// Channel as 'Green', Operator
// as 'Divide' and rValue(%) as 55
.operator('Green','Divide',10,true)

// Process and Write the image
.write("operator-divide1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/873a9e8fb9c09054d5a7086dbc92b090.png)

**例 3:**

## java 描述语言

```
// Include gm library
var gm = require('gm');

// Import the image
gm(600, 300, 'white')

// Set the color for the stroke
.stroke("green", 3)

// Set the font 
.font("Helvetica.ttf", 60)

// Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Invoke operator function with
// Channel as 'Green', Operator as
// 'Assign' and rValue(%) as 35
.operator('Green', 'Assign', 35, true)

// Process and write the image 
.write("operator-assign2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**

![](img/0910e861d017da2565d8b2c3ba8b1d12.png)

**参考:**

*   [http://www . graphicsmagick . org/graphicsmagick . html # details-operator](http://www.graphicsmagick.org/GraphicsMagick.html#details-operator)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)