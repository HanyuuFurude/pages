---
title: 高级数据结构复习
date: 2019-06-10 19:59:55
cover:
tags:
	- advanced data structures
	- review
categories:
---

# 平摊分析与基本思路

## Aggregate method （聚集分析）

### Potential Function

$P(i)=amortizedCost(i)-actualCost(i)+P(i-1)$

$\sum(P(i)-P(i-1))=\sum(amortizedCost(i)-actualCost(i))$

$P(n)-P(0)=\sum(amortizedCost(i)-actualCost(i))$

$P(n)-P(0)\geq 0$

When P(0)=0,P(i) is the amount by which the first i operations have been over charged

## Accounting method

## Potential function method



# 数据结构、二叉树与树

# 外排序

## 缓冲使用策略，原因和方法

# 红黑树

# 最小最大堆

# 设计数据结构与算法

