# 基于神经网络算法的用电量预测

作者信息：linsl1986 (https://github.com/linsl1986)

我在AI Studio上获得白银等级，点亮1个徽章，来互关呀~ https://aistudio.baidu.com/aistudio/personalcenter/thirdview/134639

## 1. 简要介绍
    开展电力系统用电量及负荷预测的目的是：为了电力系统供电范围内电力工业的发展能够适应国民经济和社会发展的需要。
    用电量及负荷预测是电力工业生产建设计划及经营管理的基础，又是电力系统规划设计的基础。
    本项目以A地区一年的用电量和相应的气象因素为依据，使用神经网络算法进行电量及负荷预测。

## 2. 环境设置
导入包，设置所用的归一化方法、神经网络结构、训练轮数和预测时间段等信息

-------------------------------------------------------------------
import pandas as pd
import numpy as np
import paddle
import paddle.fluid as fluid
import numpy as np
import pickle
from tqdm import tqdm
import matplotlib.pyplot as plt
# 选择归一化方法
normalization=1 # 0表示Max-min归一化， 1表示Zscore归一化
# 选择神经网络
flag = 0 # 0表示全连接神经网络， 1表示LSTM神经网络
day_num = 1 # 选择前一天的特征作为输入数据。
# 训练参数设置
BATCH_SIZE = 5
learning_rate = 0.001
EPOCH_NUM = 200

# 可视化天数选择，建议大于7，这样才能展示一周的预测情况
date_n = 7
-------------------------------------------------

