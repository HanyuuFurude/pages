---
title: Tensorflow入坑试水
date: 2019-01-30 10:49:28
tags:
---
## Tensorflow变量类型
|Name|Useage|
|----|------|
|[tf.Variable](https://www.tensorflow.org/api_docs/python/tf/Variable?hl=zh-CN)|Tensor变量|
|[tf.constant](https://www.tensorflow.org/api_docs/python/tf/constant?hl=zh-CN)|Tensor常量|
|[tf.placeholder](https://www.tensorflow.org/api_docs/python/tf/placeholder?hl=zh-CN)|Tensor占位符|
|[tf.SparseTensor](https://www.tensorflow.org/api_docs/python/tf/SparseTensor?hl=zh-CN)|Tensor稀疏张量
## 设备管理
``` py
import tensorflow as tf
#选择设备 CPU->CPU:0
with tf.device('/gpu:1'):
    v1 = tf.constant([1.0, 2.0, 3.0], shape=[3], name='v1')
    v2 = tf.constant([1.0, 2.0, 3.0], shape=[3], name='v2')
    sumV12 = v1 + v2
    #config=tf.ConfigProto(log_device_placement=True)打印执行操作所用的设备
    with tf.Session(config=tf.ConfigProto(log_device_placement=True)) as sess:
        print sess.run(sumV12)
```
## 使用GPU计算
若要使用Tensorflow-gpu，请检查您是否有**算力大于3的NVIDIA显卡**。
* 查询显卡算力[地址](https://developer.nvidia.com/cuda-gpus#collapseOne)
* 若要使用CUDA加速计算，请确保您已安装[CUDA Toolkit](https://developer.nvidia.com/cuda-downloads),并且按需下载并配置您需要的[Deep learning frameworks](https://developer.nvidia.com/deep-learning-software),目前，我们用到的frameworks有[cuDNN](https://developer.nvidia.com/cudnn),请确保您的framework和CUDA版本配套，否则**无法使用**。


## ImportError: No module named input_data
	由于版本更新，Tensorflow已经不建议再使用input_data.如果需要继续使用，请查看[input_data.py](../Example/input_data.py)