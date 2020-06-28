---
layout:     post
title:      EEG调研
subtitle:   神经科学笔记
date:       2020-6-22
author:     Zixuan Chen
header-img: img/post-bg-eeg.jpg
catalog: true
tags:
    - neurosciences
---
> EEG是神经科学的常用研究工具，本文对EEG进行了相关市场调研，为后续设备采购提供方案

## EEG简单介绍
EEG是**E**lectro**E**ncephalo**G**raphy（脑电图描记法）的简写，是一种非侵入式的脑电波采集技术。
![图片来自](https://img-blog.csdnimg.cn/20200615092638137.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM5MzE4NDQz,size_16,color_FFFFFF,t_70#pic_center =600x)
在脑电图中，扁平的金属盘(电极)连接到你的头皮上。在高密度脑电图中，如图所示，电极被紧密地间隔在一起。电极通过电线连接到脑电图机上。有些人戴上有电极的弹性帽，而不是把粘合剂涂在头皮上。

## EEG参数介绍
**通道数** 这个最重要，决定了采样的空间分辨率，这是EEG的瓶颈。
**采样频率** 这个决定了采样的时间分辨率，一般来说EEG的采样分辨率已经足够高了


## 我们的需求
### 需求一：EEG辅助机器人控制
一种实验设计思路如下图所示
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200615112811839.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM5MzE4NDQz,size_16,color_FFFFFF,t_70)
EEG作为原始脑电数据的采集设备。这要求EEG通道数要尽可能高，同时由于我们采集的信号主要用于运动的控制，对脑皮层运动区([Motor cortex](https://en.wikipedia.org/wiki/Motor_cortex))采样准确率要尽可能高，这要求EEG的电极必须是能活动的而且尽量小，方便我们在下图中的区域尽可能多安放电极
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200615112421535.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM5MzE4NDQz,size_16,color_FFFFFF,t_70#pic_center )
### 需求二：EEG+眼动仪
对眼动仪的介绍在[这里](https://zhuanlan.zhihu.com/p/23164412)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200615141708840.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM5MzE4NDQz,size_16,color_FFFFFF,t_70#pic_center )
我们的视觉处理和眼动的协调通常由大脑皮层和皮层下的许多区域来完成。在选择与任务相关的信息时，眼动通常由视觉功能相关特征的相互作用和被试者选择任务相关信息的目标优先程度所驱使。

我们可以将EEG获取的脑电波信息与眼动仪的眼动信息结合实现**视觉与任务执行的交互研究**


### 需求三：社会机器人学
在研究机器人的社会接受度方面，抛弃传统的问卷模式。通过EEG收集受试者的脑电波进行情感计算
## 市场上现有EEG型号分析

### wearablesensing
这家EEG的优点是它在使用时是不用打凝胶的，只用干电极，而且可以穿过头发，但是缺点在于它的通道数只有21个有点少
[DSI Series Dry EEG Headsets](http://www.wearablesensing.com/)
### g.tec
这一家的通道数最高可以达到64，同时可以配合fNIRs，同时有电池可以佩戴着户外运动的。
[g.NAUTILUS RESEARCH可穿戴头盔](https://www.gtec.at/product/gnautilus-research/)
### EGI High Density EEG
这一款的特点在于通道数极高（最高可达256个），所以称之为High Density，同时具有兼容MEG和fMRI的型号。
[GES400和GES405](https://www.egi.com/images/stories/company/documents/ges_400_brochure_08_15_MM_400.pdf)

### biosemi
通道数也挺高的（256个），也不用涂凝胶，直流放大器，24位分辨率，有源电极生物电位测量系统
[ ActiveTwo system](https://www.biosemi.com/products.htm)

### ANTneuro
该电池供电系统有4个版本，用于记录32到256个EEG通道，高密度脑电图站可以被分割成独立的(移动的)64通道脑电图系统，供个人使用或群体研究。此外，系统的功能可以很容易地扩展，包括EOG、ECG、EMG、实时数据访问以及呼吸、温度、皮肤电导和加速等生理传感器。
[EEGmylab](https://www.ant-neuro.com/sites/default/files/SLS-SM-0036.03rev02%20eego_mylab_brochure_A4%202020-04-30%20%281%29_0.pdf)

### Advanced Brain Monitoring
10分钟快速安装
自动无线阻抗检查
ESU-MC蓝牙无线范围可达10米
可充电电池续航8小时以上
机载加速度计，以量化头部运动和位置
数据质量监控和反馈
缺点是通道数太少（只有20个）
[Stat X Series Mobile EEG](https://www.advancedbrainmonitoring.com/products/stat-x-series-eeg)
