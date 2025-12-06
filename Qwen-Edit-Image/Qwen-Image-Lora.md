https://www.bilibili.com/video/BV1kHCEBAEDz/?trackid=web_pegasus_0.router-web-pegasus-2356061-w94l6.1765014993469.163&track_id=pbaes.JzYZC9Uuu65aOiwNFPYTwbYMyRIKYrImQCxfXo9Mda4ekr1ZUBx4FwB7EqJesOO3BnN1xmhoywckLgareaz3oLIPm1HBweDfCu9VaHGJm7Sku7qjC-ZhpYMvFo3jLfEwhFIvMLgkmzijyBItyQLtHS2VF7_a4pHSutcv33imlA3uFYoMKfVoROX_rrBHkpqI&caid=__CAID__&resource_id=__RESOURCEID__&source_id=5614&from_spmid=__FROMSPMID__&request_id=1765014993419q172a27a61a103q2648&creative_id=718039452&linked_creative_id=718046007&vd_source=c9ff634ae673bbd311926a353b26d3b5

# Qwen-Image LoRA训练分享

# 1.训练的核心：变化
- 模型不是记忆图片
- 模型学习输入变化和输出
- 训练就是让模型掌握规律

## 变化的维度
- 光影
- 色彩
- 材质
- 形状
- 大小
- 背景

<img width="446" height="226" alt="image" src="https://github.com/user-attachments/assets/4d9c7fa1-b5d1-41af-ae1d-70bca798bf3f" />

<img width="445" height="218" alt="image" src="https://github.com/user-attachments/assets/70fe8295-efd9-4337-b7a8-73333d2abfd1" />

<img width="455" height="244" alt="image" src="https://github.com/user-attachments/assets/ca1da37a-0ae9-49cd-9e17-f460ea105024" />

反复强化

模型学习依赖重复

不能同时教太多变化，会学乱

每个功能要拆开训练

<img width="449" height="211" alt="image" src="https://github.com/user-attachments/assets/4c53f447-df8c-4058-a2ba-8f13101de7f7" />

很难去掉光斑

<img width="446" height="237" alt="image" src="https://github.com/user-attachments/assets/41a296c8-8b7f-4524-bf5a-daf65926d5cc" />

避免模型偏科

避免因为样本不足导致泛化能力不够

多个角度

多个颜色

多材质

多光源方向

多品质

多维度

多动作

多角度

## 泛化能力

模型能够处理没有见过的场景

数据不等于记忆

泛化是核心的能力

<img width="647" height="416" alt="image" src="https://github.com/user-attachments/assets/1199ec9e-6f6c-4468-9ec0-ed3a17f85a22" />

<img width="587" height="334" alt="image" src="https://github.com/user-attachments/assets/32f00fda-e08f-4c87-9c11-39a84d0aa7c1" />

## 泛化失败的三大根源

模型只能泛化他见过的变化

- 1.样本过少
- 2.样本变化不足
- 3.训练被噪声干扰

## 多样性 vs不学乱

扩大场景，但是保持变化一致的

扩大物体的种类

扩大背景风格

扩大光影方向

但是变化逻辑固定

只加合理的变化

## 从loss曲线看健康状况

平稳下降-》正常

忽高忽低-〉数据问题

不下降——》学不会
# 2.数据集的制作思路
# 3.泛化能力构建
# 4.曲线分析和问题定位


<img width="660" height="432" alt="image" src="https://github.com/user-attachments/assets/95583904-13c5-4eff-b2cc-7c191609faff" />

<img width="595" height="314" alt="image" src="https://github.com/user-attachments/assets/aea3cb8f-a952-408c-9b73-79a958c29b3b" />



<img width="555" height="259" alt="image" src="https://github.com/user-attachments/assets/aeb498e3-521b-46b5-940d-a82b6cae9993" />


<img width="598" height="332" alt="image" src="https://github.com/user-attachments/assets/dd7ae3ac-fa35-41be-9b03-ee4e269180e6" />


收敛太快：

学的太浅

模型懒惰

仅仅记住表面的规则

收敛过慢：

数据复杂

学习率太低

噪声样本干扰

<img width="586" height="308" alt="image" src="https://github.com/user-attachments/assets/886f0f37-7799-4e9d-a866-90086394cbcb" />


<img width="589" height="309" alt="image" src="https://github.com/user-attachments/assets/687f9fd9-3a5d-4b44-a402-f2734d91f619" />


什么是学习率？

太大会怎么样？

表现：

loss来回震荡，忽高忽低

不收敛

模型一致在乱跳

原因：每次更新太暴力，越过最佳点

太小的时候会怎么样？

表现：

loss下降非常慢，甚至卡着不动

学不会，时间浪费

原因：

每次更新太微弱，几乎没有推进

明确变化，

制作对照数据集

扩展泛化边界，

用曲线捕获问题

纹理类，网状，不规则的斑块效果非常不好的，

像素偏移

分辨率，分块处理的，

数据量的确定？

50对，少的话泛化能力弱的

人物场景

一句话描述清楚，描述清楚这个变化是什么？


15轮左右，前5轮检查是不是有异常的情况


float8


3bit语仪还原



