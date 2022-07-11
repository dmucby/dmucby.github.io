---
title:       "Hidden Markov Model"
subtitle:    "HMM隐马尔科夫模型与编码器解码器"
description: "用通信模型来应用马尔可夫模型在机器学习自然语言处理等领域"
date:        2022-06-18
author:      蔡博宇
image:       "/img/programming/Math/pexels-fauxels-3183170.jpg"
published: true
tags:
    - Math
URL: "/2022/6/16/Math/Pleasing/HMM"
categories:  ["Tech" ]
---

# Hidden Markov Model

> 在哲学的意义上，这是人类认识的一个飞跃！

马尔可夫模型是一个并不复杂，且在自然语言处理领域最为快捷有效的方法，它通过概率的计算解决了生活中看似困难的问题。

## 通信模型

首先来看经典的通信模型，由Roman Jakobson提出通信的6要素：发送者、信道、接收者、信息、上下文、编码。

![通信.drawio](https://personal-drawing-bed.oss-cn-beijing.aliyuncs.com/img/%E9%80%9A%E4%BF%A1.drawio.png)

> Encoder <–> Decoder 信息流通

那么问题就是如何根据接收端的信息 $o_1,o_2,o_3,...$ 来推测发送端的信息 $s_1,s_2,s_3,...$ 这个问题就转化为概率的问题。

即求最大的 $P(s_1,s_2,s_3,...|o_1,o_2,o_3,...)$，则最大的概率所代表的发送信息就是最有可能传过来的信息（但是这也不是一定的）。

上述公式也可以等价为：

$$\mathbf{\frac{P(s_1,s_2,s_3,...|o_1,o_2,o_3,...) \cdot P(s_1,s_2,s_3,...)}{p(o_1,o_2,o_3,...)} {\large } }$$

在贪心情况下我们认为此时的 $s_1,s_2,s_3,...$ 就是结果，但现实往往出现问题，这就导致了`Attention` 的出现(大名鼎鼎的`Transformer`)。

## 隐马尔可夫模型

由于在随机过程中，都可能产生随即状态，这样就有了两个维度的不确定性。

为了简化所以马尔可夫认为每个随机状态不再是随机的，而是只与前一个状态有关。

![v2-6f11525bdfd04676773bae193694ce19_720](https://personal-drawing-bed.oss-cn-beijing.aliyuncs.com/img/v2-6f11525bdfd04676773bae193694ce19_720w.jpg)

即 $P(s_t|s_1,s_2,s_3,...,s_{t-1}) =  P(s_t|s_{t-1})$，这就是马尔科夫链的数学假设。

![](https://personal-drawing-bed.oss-cn-beijing.aliyuncs.com/img/v2-3899583b9d750644e978a7f4e7ed6dbf_r-16554842971135.jpg)



隐马尔可夫模型在此基础增加每个时刻的输出 $o_t$，通过 $o_t$ ：

![99909](https://personal-drawing-bed.oss-cn-beijing.aliyuncs.com/img/999096.png)



我们便能计算某个时刻状态$s_1,s_2,s_3,...$产生输出$o_1,o_2,o_3,...$的概率：

 $ P(s_1,s_2,s_3,...|o_1,o_2,o_3,...)$ = $ \prod_{t}p(s_t|s_{t-1})\cdot  p(o_t|s_t)$ ，

将公式类比到通信模型的公式中得到：

$$P(o_1,o_2,o_3,...|s_1,s_2,s_3,...) = \prod_{t}p(o_t|s_t) $$

这样通过计算产生最大的概率就可以确定原始的发送信息，这样看似困难的语音识别与Seq2Seq问题就被解决了。