---
layout:     post
title:      上传RNA-seq测序数据到NCBI
subtitle:   以帮助xlb上传RNA-seq数据为例
date:       2019-06-13
author:     Xilong Chen
header-img: img/NCBI-bg.jpg
catalog: true
tags:
    - NCBI
    - RNA-seq
---

昨天xlb托我帮他上传一下他文章的原始数据，我查阅了一下现有能搜到的中文教程，没有非常合适的，于是自己边上传边写了一下的流程供未来的自己或他人参考。

文章数据基本情况：两个处理三个时期共6个样品，二代双端RNA-seq测序，Raw data fastq序列文件2*6=12个。

## 准备工作

- 申请一个NCBI账号

 不赘述

- 准备好自己的原始数据

 把公司给的测序原始数据copy到能长期开机的PC上

- 理解submission层级结构：NCBI SRA 数据库现在的上传需要进行3个层级的submission，分别是：

 - BioProject 试验项目，最大的层级，一般来说一个完整的文章就是一个BioProject
 - BioSample 试验过程中的样本，一个文章内所有采集的样品和样品信息
 - Sequence Read Archive (SRA) 具体的数据，每个样品具体获得的测序数据

 注意：样品可以有不同的试验数据，比如项目中一个样品同时测定了RNA-seq和miRNA，那么在Sample层面有一个记录，但是在SRA层面就有两个数据，共同指向这个Sample。

下面我们来具体做一遍

## 申请BioProject
