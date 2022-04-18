> 介绍在CUDA 10.0的大环境下,安装pytorch-gpu(1.3.1)和tensorflow-gpu(1.15.0)

## 0. 环境
- CUDA 10.0
- cudnn 7.4
- python 3.7.2
- windows 10

## 1. 安装Pytorch-gpu
### 1.1 方法一: pytorch官网自动化安装命令
问题：仅支持CUDA10.2或者CUDA11.1，不放心
官网链接：https://pytorch.org/get-started/locally/
![对照表](https://picgo-1256052225.cos.ap-guangzhou.myqcloud.com/img/20211111140639.png)

### 1.2 方法二：下载whl文件自己安装
下载地址：https://download.pytorch.org/whl/torch_stable.html
需要下载 **torch** 和 **torchvision**
我下载的版本是(一定选择**cu**开头的)：
- [torch-1.3.1-cp37-cp37m-win_amd64](https://download.pytorch.org/whl/cu101/torch-1.3.1-cp37-cp37m-win_amd64.whl)
- [torchvision-0.4.1-cp37-cp37m-win_amd64](https://download.pytorch.org/whl/cu101/torchvision-0.4.1-cp37-cp37m-win_amd64.whl)

### 1.3 检验是否成功
```python
import torch
print(torch.cuda.is_available())
print(torch.cuda.get_device_name(0))
```

## 2. 安装Tensorflow-gpu
### 2.1 找到对应版本直接安装
tensorflow_gpu与CUDA和cudnn版本对照表：
官网链接：https://tensorflow.google.cn/install/source#linux
![版本对照表](https://picgo-1256052225.cos.ap-guangzhou.myqcloud.com/img/20211111141542.png)

我这里选择的是 tensorflow_gpu-1.15.0

```shell
pip install tensorflow_gpu==1.15.0
```

### 2.2 检验是否成功
```python
import tensorflow as tf
print(tf.test.is_gpu_available())
```