---
title: Tensorflow入坑试水
date: 2019-01-30 10:49:28
tags:
---
# Leadin
## The computation graph
### Building the graph
``` py
import tensorflow as tf
matrix1 = tf.constant([[3.,3.]]) # create a constant
matrix2 = tf.constant([[2.],[2.]])
product = tf.matual(matrix1,matrix2)  # create a matlum op(operation)
```
### Launching the graph in a session
```py
sess = tf.Session()  # create a session in tensorflow
result = sess.run(product)
print(result)
sess.close()   # DONT FORGET THIS!
```
