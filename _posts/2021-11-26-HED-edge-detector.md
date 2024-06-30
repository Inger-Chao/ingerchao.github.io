---
layout: post
title: "论文：边缘检测相关"
date: 2020-10-30
author: ingerchao
category: blog
tag:
- Paper
---

# HED

## 摘要

我们开发了一种新的边缘检测算法，解决了这个长期存在的视觉问题中的两个重要问题：（1）整体图像训练和预测； (2) 多尺度多层次特征学习。我们提出的方法，整体嵌套边缘检测 (HED)，通过利用完全卷积神经网络和深度监督网络的深度学习模型来执行图像到图像的预测。 HED 自动学习丰富的分层表示（由对侧响应的深度监督引导），这对于解决边缘和对象边界检测中具有挑战性的模糊性很重要。我们在 BSD500 数据集（ODS F-score 为 .782）和纽约大学深度数据集（ODS F-score 为 0.746）上显着提升了最先进的技术，并以更高的速度（0.4s per图像）比最近一些基于 CNN 的边缘检测算法快几个数量级



# Theory of Edge detection

## 摘要

提出了一种边缘检测理论，实验分两部分进行。

1. 在不同尺度上分别检测自然图像中在大范围内发生的强度变换。发现在一定尺度上高斯二阶导数不依赖方向
2. 图像的强度变化来自表面不连续性或反射或照明边界，这些都具有空间局部化的特性。

> mate translate: 提出了一种边缘检测理论。分析分两部分进行。 (1) 在不同尺度上分别检测自然图像中在很宽范围内发生的强度变化。发现在给定尺度上用于此目的的适当滤波器是高斯的二阶导数，并且表明，只要满足一些简单条件，这些初级滤波器就不必依赖于方向。因此，给定尺度的强度变化最好通过找到图像 I 的 ∇2G(x, y)* I(x, y) 的零值来检测，其中 G(x, y) 是二维高斯分布， ∇2 是拉普拉斯算子。然后在每个通道中发现的强度变化由称为零交叉段的定向基元表示，并且有证据表明这种表示是完整的。 (2) 图像的强度变化是由表面不连续性或反射率或光照边界引起的，这些都具有它们是 空间局部化。正因为如此，来自不同通道的过零段不是独立的，并且推导出将它们组合成图像描述的规则。这种描述称为原始原始草图。该理论解释了几个基本的心理物理学发现，并且从作用于图像的中心环绕 ∇2G 滤波器的输出形成定向过零片段的操作构成了简单细胞生理模型的基础（参见 Marr & Ullman 1979）。 