# 基于 ResNet 的 CIFAR-10 图像分类方法复现与实验研究

**Reproduction and Experimental Study of ResNet for CIFAR-10 Image Classification**

## 1. 项目简介

本项目基于 PyTorch 深度学习框架，在 CIFAR-10 数据集上实现并研究残差神经网络 ResNet-20 的图像分类性能。

项目以普通卷积神经网络（BaselineCNN）作为对照模型，通过训练、测试和实验结果分析，研究残差连接对图像分类性能的影响。

本项目复现了 ResNet 的核心残差学习思想，并采用适用于 CIFAR-10 数据集的 ResNet-20 网络结构进行实验。

## 2. 研究论文

- **论文名称：** Deep Residual Learning for Image Recognition
- **作者：** Kaiming He, Xiangyu Zhang, Shaoqing Ren, Jian Sun
- **会议：** CVPR 2016
- **论文链接：** https://arxiv.org/abs/1512.03385

## 3. 数据集

本项目使用 CIFAR-10 图像分类数据集。

- 图像类别：10 类
- 图像尺寸：32 × 32
- 图像通道：RGB 三通道
- 训练集：45,000 张
- 验证集：5,000 张
- 测试集：10,000 张

分类类别包括：airplane、automobile、bird、cat、deer、dog、frog、horse、ship 和 truck。

## 4. 模型介绍

### 4.1 BaselineCNN

采用普通卷积神经网络作为对照模型，通过卷积层、池化层和全连接层完成图像分类。

### 4.2 ResNet-20

采用残差神经网络结构，通过残差连接学习输入与输出之间的残差映射，改善深层网络的训练效果。

ResNet-20 主要由卷积层、Batch Normalization、残差模块、全局平均池化层和全连接分类层组成。

## 5. 实验环境

- 编程语言：Python
- 深度学习框架：PyTorch
- 实验平台：Google Colab
- GPU：NVIDIA Tesla T4
- 数据集：CIFAR-10

## 6. 实验结果

两个模型均训练 20 个 Epoch，并在 CIFAR-10 官方测试集（10,000 张图像）上进行评估。

| 评价指标 | BaselineCNN | ResNet-20 |
|---|---:|---:|
| Epochs | 20 | 20 |
| Test Loss | 0.8301 | 0.4481 |
| Test Accuracy | 71.26% | 84.93% |
| Macro Precision | 71.19% | 84.95% |
| Macro Recall | 71.26% | 84.93% |
| Macro F1 | 70.95% | 84.91% |

实验结果表明，ResNet-20 在 CIFAR-10 测试集上的准确率达到 84.93%，高于 BaselineCNN 的 71.26%，说明残差学习结构在本项目实验设置下具有更好的分类性能。

## 7. 实验结果可视化

### 7.1 模型准确率对比

![Model Accuracy Comparison](results/model_comparison_accuracy.png)

### 7.2 BaselineCNN 混淆矩阵

![BaselineCNN Confusion Matrix](results/baseline20_confusion_matrix.png)

### 7.3 ResNet-20 混淆矩阵

![ResNet-20 Confusion Matrix](results/resnet20_confusion_matrix.png)

### 7.4 训练过程

训练过程中的 Loss 和 Accuracy 曲线保存在 `results` 目录中。

## 8. 项目文件说明

- `ResNet_CIFAR10_Project.ipynb`：项目完整实验 Notebook。
- `baseline_best.pth`：BaselineCNN（10 Epoch）最佳模型权重。
- `baseline20_best.pth`：BaselineCNN（20 Epoch）最佳模型权重。
- `resnet20_best.pth`：ResNet-20（20 Epoch）最佳模型权重。
- `results/`：训练日志、测试结果、分类报告、混淆矩阵和实验图表。

## 9. 运行方法

1. 下载或克隆本项目仓库。
2. 使用 Google Colab 打开 `ResNet_CIFAR10_Project.ipynb`。
3. 根据 Notebook 中的代码单元格顺序运行。
4. 下载并加载 CIFAR-10 数据集。
5. 完成模型训练、测试和结果分析。

模型权重文件保存在 `checkpoints` 目录中，实验结果保存在 `results` 目录中。

## 10. 项目仓库

GitHub：  
https://github.com/Oh811/ResNet-CIFAR10-Image-Classification

## 11. 致谢

感谢 Kaiming He 等作者提出的 ResNet 网络结构，以及 CIFAR-10 数据集提供的图像分类实验数据。

本项目仅用于计算机视觉课程学习、论文方法复现和实验研究。
