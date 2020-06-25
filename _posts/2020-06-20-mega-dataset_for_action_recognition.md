---
layout:     post
title:      "2020-06-20: 更大规模的数据集是否会进一步地提高时空3DCNN的性能呢？"
subtitle:   " 2020-06-20： Would Mega-scale Datasets Further Enhance Spatiotemporal 3D CNNs?"
date:       2020-06-20
author:     "kiwi"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
    - study
    - Video
    - Action Recognition
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

## 2. Large-scale weakly-supervised pre-training for video action recognition, CVPR 2019
![](https://i.postimg.cc/0y9vLKhY/image.png)
这里facebook提出了更大的数据集IG-Kinetics-19M. Bigger than bigger.
