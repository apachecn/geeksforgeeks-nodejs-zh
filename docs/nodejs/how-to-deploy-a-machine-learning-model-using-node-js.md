# 如何使用 Node.js 部署机器学习模型？

> 原文:[https://www . geesforgeks . org/如何部署机器学习模型-使用节点-js/](https://www.geeksforgeeks.org/how-to-deploy-a-machine-learning-model-using-node-js/)

在本文中，我们将学习如何使用 **NodeJS** 部署机器学习模型。在此过程中，我们将使用 **NodeJS** 和 **tensorflow.js** ***制作一个简单的手写数字识别器。***

**Tensorflow.js** 是一个 JavaScript 的 ML 库。它有助于将机器学习模型直接部署到 node.js 或 web 浏览器中。

**训练模型:**为了训练模型，我们将使用[谷歌可乐](https://colab.research.google.com)。它是一个我们可以运行所有 python 代码的平台，并且它装载了大多数使用的机器学习库。

下面是我们将创建的最终模型的代码。

## 巨蟒

```js
# Importing Libraries
from tensorflow.keras.datasets import mnist
import matplotlib.pyplot as plt
from keras.utils import np_utils
from keras import Sequential
from keras.layers import Dense
import tensorflowjs as tfjs

# Loading data
(X_train, y_train), (X_test, y_test) = mnist.load_data()
print ("X_train.shape: {}".format(X_train.shape))
print ("y_train.shape: {}".format(y_train.shape))
print ("X_test.shape: {}".format(X_test.shape))
print ("y_test.shape: {}".format(y_test.shape))

# Visualizing Data
plt.subplot(161)
plt.imshow(X_train[3], cmap=plt.get_cmap('gray'))
plt.subplot(162)
plt.imshow(X_train[5], cmap=plt.get_cmap('gray'))
plt.subplot(163)
plt.imshow(X_train[7], cmap=plt.get_cmap('gray'))
plt.subplot(164)
plt.imshow(X_train[2], cmap=plt.get_cmap('gray'))
plt.subplot(165)
plt.imshow(X_train[0], cmap=plt.get_cmap('gray'))
plt.subplot(166)
plt.imshow(X_train[13], cmap=plt.get_cmap('gray'))

plt.show()

# Normalize Inputs from 0–255 to 0–1
X_train = X_train / 255
X_test = X_test / 255
# One-Hot Encode outputs
y_train = np_utils.to_categorical(y_train)
y_test = np_utils.to_categorical(y_test)
num_classes = 10

# Training model
x_train_simple = X_train.reshape(60000, 28 * 28).astype('float32')
x_test_simple = X_test.reshape(10000, 28 * 28).astype('float32')
model = Sequential()
model.add(Dense(28 * 28, input_dim=28 * 28, activation='relu'))
model.add(Dense(num_classes, activation='softmax'))
model.compile(loss='categorical_crossentropy', 
        optimizer='adam', metrics=['accuracy'])
model.fit(x_train_simple, y_train, 
        validation_data=(x_test_simple, y_test))
```