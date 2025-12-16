下面是一个**系统性的图像生成领域重要论文推荐清单**（从基础理论到前沿技术），适合从**头开始学习图像生成**相关应用。我们按研究路线与模型类别组织，方便你构建学习路径。

---

## 一、基础生成模型（理解核心思想与原理）

### 1) 变分自编码器（VAE） — 概率生成建模基础

* **Auto-encoding Variational Bayes** — *Diederik P. Kingma & Max Welling (2013)*
  VAE 经典原始论文，提出了变分推理 + 自编码器的概率生成框架，是理解生成模型数学基础的重要起点。 ([ScholarWorks][1])

### 2) 生成对抗网络（GAN） — 生成性对抗学习

* **Generative Adversarial Nets** — *Goodfellow et al., NeurIPS 2014*
  GAN 开创性论文，引入对抗训练机制，在图像生成早期取得巨大效果。 ([arXiv][2])
* **Unsupervised Representation Learning with Deep Convolutional GANs (DCGAN)** — *Radford et al. (2015)*
  引入卷积结构提高生成图像质量，是理解现代 GAN 架构的关键。 ([知乎专栏][3])
* **Improved Techniques for Training GANs** — *Salimans et al., NeurIPS 2016*
  介绍了稳定训练和评价的关键技巧。 ([知乎专栏][3])

论文综述（调研 GAN 发展与分类）：

* **Image Synthesis with Adversarial Networks: a Comprehensive Survey and Case Studies** — 全面综述 GAN 系列在图像生成中的架构与进展。 ([arXiv][4])
* **Comparison and Analysis of Image-to-Image Generative Adversarial Networks: A Survey** — 专注于图像↔图像 GAN 应用与性能比较。 ([arXiv][5])

---

## 二、扩散模型（Diffusion） — 当前最主流的高质量生成框架

### 核心理论与开创性论文

* **Denoising Diffusion Probabilistic Models (DDPM)** — *Ho, Jain & Abbeel, NeurIPS 2020*
  扩散模型经典论文，通过正向加噪与反向去噪框架定义生成过程，是理解扩散生成机制的核心。 ([arXiv][2])

### 改进与训练/采样技巧

* **Improved Denoising Diffusion Probabilistic Models (Improved DDPM)** — *Nichol & Dhariwal, ICML 2021*
  提出训练与采样改进策略，提升样本质量与效率。 ([arXiv][2])
* **Classifier-Free Diffusion Guidance** — *Ho & Salimans, arXiv 2022*
  广泛用于条件图像生成（如文本→图像 prompt）。 ([arXiv][2])

### 应用与专业任务

* **Diffusion Probabilistic Models beat GANs on Medical Images** — 演示扩散模型在具体任务中优于 GAN 的案例。 ([arXiv][6])
* **Few-shot Image Generation with Diffusion Models** — 探讨在少样本条件下如何适配扩散模型。 ([arXiv][7])
* **Assessing Capacity of Diffusion Models to Reproduce Spatial Context** — 定量评估扩散模型学习图像空间结构的能力。 ([arXiv][8])

### 综述与最新进展

* **Comprehensive exploration of diffusion models in image generation: a survey (2025)** — 2025 年最新综述，讨论 Diffusion 在图像生成中的机制与挑战。 ([SpringerLink][9])
* **Diffusion Models for Image Restoration and Enhancement — A Comprehensive Survey** — 关注扩散模型在图像恢复/增强任务中的表现。 ([arXiv][10])

---

## 三、文本到图像 / 多模态生成（应用级、近前沿）

现代图像生成应用往往结合语言模型与视觉生成机制：

* **CLIP (Contrastive Language-Image Pretraining)** — 不是图像生成论文，但是文本信号指导图像生成的基础组件，在 DALL-E、Stable Diffusion 等中广泛使用。 ([arXiv][2])

重要生成式 AI 系统与相关论文（应查阅）：

* **DALL-E 2** 与相关提示机制（利用扩散模型与 CLIP）([cnblogs.com][11])
* **Stable Diffusion / Latent Diffusion Models** — 使用潜在空间扩散以提高生成速度与资源效率。 ([维基百科][12])
* **Imagen 系列模型（Google）** — 高质量文本→图像 Diffusion 模型体系。 ([维基百科][13])
* **DreamBooth** — 用于微调扩散模型以生成特定主题图像。 ([维基百科][14])

---

## 四、学习路线与建议（按阶段）

**阶段 1 — 理论基础**

1. 理解概率生成模型：VAE（*Kingma & Welling, 2013*）。 ([ScholarWorks][1])
2. 学习对抗训练与 GAN 基本原理：GAN 原始论文及 DCGAN。 ([arXiv][2])

**阶段 2 — 扩散模型理解与实践**

1. 阅读 DDPM 与 Improved DDPM。 ([arXiv][2])
2. 理解条件生成（Classifier-free guidance）。 ([arXiv][2])
3. 实践 Stable/Laten Diffusion 框架（包括文本条件）。 ([维基百科][12])

**阶段 3 — 应用与扩展**

1. 探索文本↔图像、多模态生成（CLIP + Diffusion 组合）。 ([arXiv][2])
2. 阅读最新综述与应用案例（CVPR/ICLR/NeurIPS 论文集）。 ([搜狐][15])

---

如果你希望我进一步整理**每篇论文的核心思想摘要**或**对应的代码实现资源（如 GitHub 链接）**，请告诉我你的侧重点（理论、应用或代码实践）。

[1]: https://scholarworks.bwise.kr/cau/bitstream/2019.sw.cau/78146/1/Denoising%20Diffusion-Based%20Image%20Generation%20Model%20Using%20Principal%20Component%20Analysis.pdf?utm_source=chatgpt.com "Denoising Diffusion-Based Image Generation Model Using ..."
[2]: https://arxiv.org/html/2502.21151v2?utm_source=chatgpt.com "A Review on Generative AI for Text-to-Image and ..."
[3]: https://zhuanlan.zhihu.com/p/649510313?utm_source=chatgpt.com "Diffusion Models论文集"
[4]: https://arxiv.org/abs/2012.13736?utm_source=chatgpt.com "Image Synthesis with Adversarial Networks: a Comprehensive Survey and Case Studies"
[5]: https://arxiv.org/abs/2112.12625?utm_source=chatgpt.com "Comparison and Analysis of Image-to-Image Generative Adversarial Networks: A Survey"
[6]: https://arxiv.org/abs/2212.07501?utm_source=chatgpt.com "Diffusion Probabilistic Models beat GANs on Medical Images"
[7]: https://arxiv.org/abs/2211.03264?utm_source=chatgpt.com "Few-shot Image Generation with Diffusion Models"
[8]: https://arxiv.org/abs/2309.10817?utm_source=chatgpt.com "Assessing the capacity of a denoising diffusion probabilistic model to reproduce spatial context"
[9]: https://link.springer.com/article/10.1007/s10462-025-11110-3?utm_source=chatgpt.com "Comprehensive exploration of diffusion models in image generation: a survey | Artificial Intelligence Review"
[10]: https://arxiv.org/abs/2308.09388?utm_source=chatgpt.com "Diffusion Models for Image Restoration and Enhancement -- A Comprehensive Survey"
[11]: https://www.cnblogs.com/AmazonwebService/p/17805605.html?utm_source=chatgpt.com "Generative AI 新世界| 文生图（Text-to-Image）领域论文解读"
[12]: https://en.wikipedia.org/wiki/Stable_Diffusion?utm_source=chatgpt.com "Stable Diffusion"
[13]: https://zh.wikipedia.org/wiki/Imagen?utm_source=chatgpt.com "Imagen"
[14]: https://zh.wikipedia.org/wiki/DreamBooth?utm_source=chatgpt.com "DreamBooth"
[15]: https://www.sohu.com/a/674963646_121119001?utm_source=chatgpt.com "当AIGC遇到GAN和Diffusion，CVPR 2023论文大盘点_图像_模型_方法"
