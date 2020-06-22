---
layout:     post
title:      "2020-06-20: 视频相关文章阅读笔记"
subtitle:   " 2020-06-20： Video Related Paper Reading Notes"
date:       2020-06-20
author:     "kiwi"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
    - study
    - Video
    - Action Recognition
    - Object Detection
---

### 1. Would Mega-scale Datasets Further Enhance Spatiotemporal 3D CNNs?

更大规模的数据集是否会进一步地提高时空3DCNN的性能呢？

结论是可以的。但是边际收益在下降。

![](https://i.postimg.cc/FsbDdFH2/screenshot-24.png)

1. 大的数据集预训练能够提升性能。（Kinetics-700 > Kinetics -400)

2. 大的数据集能训更深的模型 (Kinetics-700 with ResNet-200 √， Kinetics-400 with ResNet-200 X)

3. 构建数据集时，应该保持类别数补办，然后增加类别的内instance数量。

   ![](https://i.postimg.cc/Y23JD7H1/screenshot-27.png)

4. Released Model and Code on [Github](https://github.com/kenshohara/3D-ResNets-PyTorch)

### 2. Temporal Pyramid Network for Action Recognition

![](https://i.postimg.cc/bwgrzJ43/screenshot-28.png)

SlowFast 通过两个模型来处理运动节奏快慢，但是两个模型又大又重，能不能一个模型完成呢。这里提出了一个时序金字塔的方法来实现。整体基于TSN来改造，不过应该可以拓展到其他模型。

那么对于金字塔的每一层，都由一个所谓的辅助头“auxiliary head，用来分别预测一个分数，辅助模型收敛，增强语义捕捉能力。

![](https://i.postimg.cc/4NnLSxjC/screenshot-29.png)

然后引入对经过spatial  modulation的特征进行时序缩放，毕竟在原模型里面深度不一样时序维度不一。

接下来就是怎么将金字塔里的特征合在一起。

![](https://i.postimg.cc/fWv7fQbG/screenshot-30.png)

![](https://i.postimg.cc/zvWGprC9/screenshot-31.png)

实验结果说Parallel最好。

![](https://i.postimg.cc/WbC7h6zz/screenshot-32.png)



### 3. Memory Enhanced Global-Local Aggregation for Video Object Detection

![](https://i.postimg.cc/HxnLJnYt/screenshot-25.png)

这里认为的是对于video object detection 来说，有全局语义信息和局部定位信息。 这里用了memory enhanced 来做这点。Long Range Memory （LRM）Module.

Global: 当我们无法识别当前的物体，会尝试通过对上下文通过高度语义相似的来决定这个物体是什么。

Local: 通过相邻帧中的物体运动变化，可以帮助我们寻找到物体的位置。

![](https://i.postimg.cc/sgTTrfXr/screenshot-26.png)

shuffle video frames as global , ordered as local. 

LRM是对历史的有限local 特征的 aggregation，cached 在那里来减少计算，直接供模型调用。

