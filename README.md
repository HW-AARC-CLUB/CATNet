# COCO Text修订版

[COCO Text](https://vision.cornell.edu/se3/coco-text-2/) 是OCR领域中一个著名的开源文字检测&识别数据集。文字识别部分中，训练集包含42618条标注数据，验证集包含9896条标注数据，测试集包含9838条数据但不含标注。在此数据集中，有大约13%的数据存在分辨率过低、文字被严重遮挡、文字方向旋转等问题。部分图片含有竖写文字，还有部分图片不含文字却有文字标注。我们开源的COCO Text修订版，不仅修正了上述问题，并且给测试集也加上了离线标注。

在修订过程中，我们丢弃了所有文字无法肉眼识别或者压根不含文字的图片。我们给所有图片都标注了旋转角（顺时针0，90，180，270择其一）。最终数据集中，训练集共保留了37710张，验证集保留了8638张，测试集保留了7859张，均含有统一格式的标注。

修正版本数据集已经用作测评文字识别模型的benchmark数据集之一。第一个使用修正版本数据集的论文CATNet: Scene Text Recognition Guided by Concatenating Augmented Text Features已经被ICDAR2021接收。

你可以在[这里](https://drive.google.com/file/d/1md_6J4qihcT70I_tPA19PI6br9oZDiLS/view?usp=sharing)下载本数据集

# 标注文件

在每个子集下（训练集，验证集，测试集），均有如下文件（夹）：

```
.
│  coco_all_examples.txt
│  coco_blur_examples.txt
│  coco_curve_examples.txt
│  coco_hard_examples.txt
│  coco_normal_examples.txt
│
└─images
```

其中，images文件夹包含了保留的图片。coco_all_examples.txt包含了本子集的全部样本；coco_blur_examples.txt包含了模糊的样本；coco_curve_examples.txt包含了文字弯曲的样本；coco_hard_examples.txt包含了因为各种原因难以阅读（但依然能读）的样本；coco_normal_examples.txt包含的是图像质量正常的样本。

# 标注格式
每个标注文件（.txt）中，每一行代表一个样本，以tab分隔（"\t"）。每行依此被分隔为三段，分别为路径，标签和旋转角

例如若某行为：
```
images/12345.jpg	ABC	90
```
则代表相对路径为images/12345.jpg的样本的标签为“ABC”，旋转角为顺时针90度。


# 开源许可

本数据集中的标注适用[Creative Commons Attribution 4.0 License](https://creativecommons.org/licenses/by/4.0/legalcode) 。

本数据集中的图片我们不声明所有权，其所有权归原作者所有，不适用开源许可。
