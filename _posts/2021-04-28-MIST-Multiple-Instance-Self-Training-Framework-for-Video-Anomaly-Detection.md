---
layout:     post
title:      "MIST: Multiple Instance Self-Training Framework for Video Anomaly Detection"
subtitle:   "面向视频异常检测的多示例自训练框架"
date:       2021-04-28
author:     "kiwi"
header-img: "https://i.postimg.cc/gJrb4G36/Structure-New-1.png"
catalog: true
tags:
    - CVPR2021
    - VAD
    - Weakly Supervised
    - Project Page
---

# MIST: Multiple Instance Self-Training Framework for Video Anomaly Detection

Published in ***IEEE International Conference on Computer Vision and Pattern Recognition* (CVPR), 2021**

Recommended citation form: 

> Jia-Chang Feng, Fa-Ting Hong and Wei-Shi Zheng. “MIST: Multiple Instance Self-Training Framework for Video Anomaly Detection, Proceedings of the IEEE International Conference on Computer Vision and Pattern Recognition. 2021.

## Brief Biography

Weakly supervised video anomaly detection (WS-VAD) is to distinguish anomalies from normal events based on discriminative representations. Most existing works are limited in insufficient video representations. In this work, we develop a multiple instance self-training framework (MIST)to efficiently refine task-specific discriminative representations with only video-level annotations. In particular, MIST is composed of 1) a multiple instance pseudo label generator, which adapts a sparse continuous sampling strategy to produce more reliable clip-level pseudo labels, and 2) a self-guided attention boosted feature encoder that aims to automatically focus on anomalous regions in frames while extracting task-specific representations. Moreover, we adopt a self-training scheme to optimize both components and finally obtain a task-specific feature encoder. Extensive experiments on two public datasets demonstrate the efficacy of our method, and our method performs comparably to or even better than existing supervised and weakly supervised methods, specifically obtaining a frame-level AUC 94.83% on ShanghaiTech.

![](https://i.postimg.cc/gJrb4G36/Structure-New-1.png)

## Experimental Results

We have deployed extensive experiments on UCF-Crime and ShanghaiTech dataset, and outperforms other methods under the same setting.

<img src="https://i.postimg.cc/54w4tSmh/UCF-results.png" width="600" align=center>

<img src="https://i.postimg.cc/cZRC109v/SHT-results.png" width="600" align=center>


Comparison with previous encoder-based method [Zhong .et al, CVPR 2019] as below, the left of which are the results of UCF-Crime while the right are those of ShanghaiTech.

<img src="https://i.postimg.cc/9QSkVy9z/Zhong-Compare-1.png" width="600" align=center>


## Visualization


Visualization of the testing results on UCF-Crime (better viewed in color). The red blocks in the graphs are temporal
ground truths of anomalous events. The orange circle shows the wrongly labeled ground truth, the blue circle indicates the
wrongly predicted clip, and the red cricle indicates the correctly predicted clip.

![](https://i.postimg.cc/MpcRkBxs/Score-UCF-v2-1.png)

More spatial anomaly activation maps visualization on UCF-Crime. The left 5 columns of the graphs are the
successful results while the right 2 columns are the failures. 

![](https://i.postimg.cc/bYCszvm4/Spatial-More-1.png)




***```Paper```*** [Download paper here](https://arxiv.org/abs/2104.01633)

