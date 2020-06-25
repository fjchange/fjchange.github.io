---
layout:     post
title:      "CVPR 2020: 记忆增强的全局局部聚合的视频物体检测"
subtitle:   " CVPR 2020： Memory Enhanced Global-Local Aggregation for Video Object Detection"
date:       2020-06-20
author:     "kiwi"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
    - study
    - Video
    - Object Detection
---
# Memory Enhanced Global-Local Aggregation for Video Object Detection

![](https://i.postimg.cc/HxnLJnYt/screenshot-25.png)

这里认为的是对于video object detection 来说，有全局语义信息和局部定位信息。 这里用了memory enhanced 来做这点。Long Range Memory （LRM）Module.

Global: 当我们无法识别当前的物体，会尝试通过对上下文通过高度语义相似的来决定这个物体是什么。

Local: 通过相邻帧中的物体运动变化，可以帮助我们寻找到物体的位置。

![](https://i.postimg.cc/sgTTrfXr/screenshot-26.png)

shuffle video frames as global , ordered as local. 

LRM是对历史的有限local 特征的 aggregation，cached 在那里来减少计算，直接供模型调用。
