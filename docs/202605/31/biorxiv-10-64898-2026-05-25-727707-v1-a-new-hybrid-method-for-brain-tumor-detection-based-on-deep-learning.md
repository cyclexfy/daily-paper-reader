---
title: A New Hybrid Method for Brain Tumor Detection Based on Deep Learning
title_zh: 一种基于深度学习的新型混合方法用于脑肿瘤检测
authors: "Sharbaf, S."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.25.727707v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 混合DCNN-鲸鱼优化算法用于MRI脑肿瘤检测
tldr: "脑肿瘤MRI检测因肿瘤异质性和成像差异而困难。本文提出DCNN-WOA混合框架，结合卷积神经网络与鲸鱼优化算法，实现自动化特征提取与超参数优化。在公开数据集上达97.8%准确率、96.4%灵敏度、98.1%特异度。该方法减少特征冗余并加速收敛，为临床决策支持提供有效方案。"
source: biorxiv
selection_source: fresh_fetch
motivation: 脑肿瘤MRI检测中，传统方法精度不足且难以处理异质性，需要更高效自动化的检测模型。
method: 提出DCNN-WOA框架，包含数据预处理、CNN特征提取、WOA特征选择与超参数优化及分类。
result: "在公开MRI数据集上实现97.8%准确率、96.4%灵敏度、98.1%特异度和97.2% F1分数。"
conclusion: 该混合方法优于传统CNN和当前最优深度学习架构，适用于实时临床神经影像决策支持。
---

## 摘要
由于肿瘤异质性和成像可变性，利用磁共振成像（MRI）进行脑肿瘤检测仍然是一项具有挑战性的任务。本文提出了一种新颖的混合深度卷积神经网络-鲸鱼优化算法（DCNN-WOA）框架，用于自动脑肿瘤检测和分类。该方法包括四个主要阶段：MRI数据预处理和增强、使用多层卷积神经网络（CNN）进行深度特征提取、通过鲸鱼优化算法（WOA）进行特征选择和超参数优化，以及最终分类并全面评估性能。通过联合优化深度特征和训练参数，该框架有效降低了特征冗余，加速了收敛，并增强了模型泛化能力。在公开可用的MRI数据集上的实验结果表明，DCNN-WOA模型优于传统CNN和最新的深度学习架构，实现了97.8%的准确率、96.4%的灵敏度、98.1%的特异性和97.2%的F1分数。该方法的实际影响使其成为神经影像学中实时临床决策支持系统的有前途的解决方案。

## Abstract
Brain tumor detection using Magnetic Resonance Imaging (MRI) remains a challenging task due to tumor hetero-geneity and imaging variability. This paper presents a novel hybrid Deep Convolutional Neural Network Whale Optimization Algorithm (DCNN,WOA) framework for automated brain tumor detection and classification. The proposed method consists of four main stages: MRI data preprocessing and augmentation, deep feature extraction using multi-layer Convolutional Neural Networks (CNN), feature selection and hyperparameter optimization via the Whale Optimization Algorithm (WOA), and final classification with comprehensive performance evaluation. By jointly optimizing deep features and training parameters, the framework effectively reduces feature redundancy, accelerates convergence, and enhances model generalization. Experimental results on a publicly available MRI dataset demonstrate that the DCNN-WOA model outperforms conventional CNN and state-of-the-art Deep Learning (DL) architectures, achieving an accuracy of 97.8%, sensitivity of 96.4%, specificity of 98.1%, and F1-score of 97.2%. The practical impact of this approach makes it a promising solution for real-time clinical decision-support systems in neuroimaging.