---
title: performance-base-core-processor
date: 2021-05-17 12:31:26
author: Starrier
tags: [性能基础]
excerpt: 性能基础 - CPU、物理核、逻辑核概念与关系
swiper:
keywords: [性能基础]
description: 性能基础 - CPU、物理核、逻辑核概念与关系
---

# 性能基础 - CPU、物理核、逻辑核概念与关系

> * 原文地址：[]()
> * 原文作者：[]()
> * 本文永久链接：[]()

##### **特别说明**

当前文章内容迁移中，如有问题，请提交 [issues](https://github.com/Starrier/starrier.github.io/issues) 谢谢 ~~

## 基础概念
##### 1. CPU( CentralProcessingUnit): 

中央处理单元，CPU不等于物理核，更不等于逻辑核。

##### 2. 物理核(physical core/processor): 

可以看的到的，真实的cpu核，有独立的电路元件以及L1,L2缓存，可以独立地执行指令。

##### 3. 逻辑核( logical core/processor，LCPU):

在同一个物理核内，逻辑层面的核。（比喻，像动画片一样，我们看到的“动画”，其实是一帧一帧静态的画面，24帧/s连起来就骗过了人类的眼睛，看起来像动起来一样。逻辑核也一样，物理核通过高速运算，让应用程序以为有两个cpu在运算）。

##### 4. 超线程( Hyper-threading， HT)：

超线程可以在一个逻辑核等待指令执行的间隔(等待从cache或内存中获取下一条指令)，把时间片分配到另一个逻辑核。高速在这两个逻辑核之间切换，让应用程序感知不到这个间隔，误认为自己是独占了一个核。


关系: 一个CPU可以有多个物理核。如果开启了超线程，一个物理核可以分成n个逻辑核，n为超线程的数量。


## 逻辑CPU与虚拟CPU

虚拟 CPU 术语与逻辑 CPU 相当，但它增加了一定的细微差别：它在计算虚拟化方面更加框架化。它指的是从底层主机硬件映射到虚拟机的那些 cpus，可以是物理或逻辑 cpus，HT。通常，来自主机服务器的1个逻辑 cpu映射到虚拟机内的1个虚拟cpu，因此它们几乎是类似的术语。