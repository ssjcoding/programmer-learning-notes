## 分词算法

[TOC]

### 一、实现原理

#### 1.1 基于词典分词

##### 1.1.1 原理

> 根据已有词典进行分词，类似于查字典。基于词典的分词方法简单、速度快，效果也还可以，但对歧义和新词的处理不是很好，对词典中未登录的词没法进行处理。

##### 1.1.2 常用方法

> - 正向最大匹配
> - 逆向最大匹配
> - 双向最大匹配
> - 最少分词数分词

##### 1.1.3 优点

> 基于词典分词，更有利于根据人们意愿得到想要的分词结果，训练速度快。

#### 1.2 基于概率统计分词

##### 1.2.1 原理

> 基于统计的分词方法是从大量已经分词的文本中，利用统计学习方法来学习词的切分规律，从而实现对未知文本的切分。简单的来说就是从已有的大量文本中训练模型，对未知文本进行预测，得到分词结果。

##### 1.2.2 常用方法

> - HMM
> - CRF
> - Bilstm-CRF

##### 1.2.3 优点

> 基于概率统计模型分词，可以处理未知文本，但需要大量的训练文本才能保证效果。

### 二、常用分词器

#### 2.1 jieba分词器

> jieba分词结合了词典和统计学习方法，分词效果快，也能处理未知文本。词典部分是作者找的语料dict.txt(安装jieba后可以在site-packages/目录下找到，大约5M大小)，统计学习模型部分是一个训练好的HMM模型

##### 2.1.1 分词过程

> - 根据默认词典进行前缀词典初始化
> - 基于前缀词典实现高效的词图扫描，生成句子中汉字所有可能成词情况所构成的有向无环图
> - 采用了动态规划（维特比算法）查找最大概率路径, 找出基于词频的最大切分组合
> - 对于未登录词，采用了基于汉字成词能力的 HMM 模型。







------

> [jieba分词源码解读](https://zhuanlan.zhihu.com/p/199057371?utm_source=wechat_session&utm_medium=social&utm_oi=713397501310283776)

