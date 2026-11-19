# Awesome Single-Pixel Imaging & Ghost Imaging

> 单像素成像 / 鬼成像 / 关联成像 的代码、工具与资源清单
> 面向：想快速找到可跑代码、少踩环境坑的研究者
>
> 最后更新：2026-11 · 维护者：[@你的用户名](https://github.com/你的用户名)

---

## 目录

- [工具箱 / 框架](#工具箱--框架)
- [经典方法实现](#经典方法实现)
- [深度学习方向](#深度学习方向)
- [鬼成像（GI / CGI / DGI）](#鬼成像gi--cgi--dgi)
- [压缩感知 / 硬件实现](#压缩感知--硬件实现)
- [术语对照表](#术语对照表)
- [如何判断一个库值不值得用](#如何判断一个库值不值得用)
- [踩坑记录](#踩坑记录)
- [贡献方式](#贡献方式)

---

## 工具箱 / 框架

> 能直接当依赖用的库，优先级最高。**先看这三个。**

| 仓库                                                         | 说明                                                         | 语言   | ⭐    | 状态          | 备注                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------ | ---- | ------------- | ------------------------------------ |
| [openspyrit/spyrit](https://github.com/openspyrit/spyrit)    | 深度图像重建 Python 工具箱，重点面向单像素成像；带 PyTorch 后端与文档 | Python | ~69  | ☐ 未跑 ☐ 跑通 | 本领域唯一框架级项目，起点           |
| [nducros/SPIRIT](https://github.com/nducros/SPIRIT)          | 单像素成像重建工具箱（TV / 正则化反演），MATLAB 脚本与函数集 | MATLAB | ~41  | ☐ 未跑 ☐ 跑通 | 与 spyrit 同源生态，做 baseline 必备 |
| [KMCzajkowski/FDRI-single-pixel-imaging](https://github.com/KMCzajkowski/FDRI-single-pixel-imaging) | 傅里叶域正则化反演（FDRI）的 MATLAB 工具箱                   | MATLAB | ~22  | ☐ 未跑 ☐ 跑通 | 代码短、好懂，适合第一个跑通         |

---

## 经典方法实现

> 论文配套代码，主要用来读**方法怎么写**，不是拿来当依赖。

| 仓库                                                         | 说明                                                   | 语言            | ⭐    | 状态          | 备注                                               |
| ------------------------------------------------------------ | ------------------------------------------------------ | --------------- | ---- | ------------- | -------------------------------------------------- |
| [zibangzhang/Fourier-single-pixel-imaging](https://github.com/zibangzhang/Fourier-single-pixel-imaging) | 傅里叶单像素成像（FSPI），高质量高效率方案             | MATLAB          | ~76  | ☐ 未跑 ☐ 跑通 | 全领域 star 最高；FSPI 代表作                      |
| [williamdelacruz/Single-Pixel-Imaging](https://github.com/williamdelacruz/Single-Pixel-Imaging) | 基于 Hadamard 基的单像素成像                           | —               | ~48  | ☐ 未跑 ☐ 跑通 | 入门最短路径                                       |
| [cbasedlf/single_pixel_demo](https://github.com/cbasedlf/single_pixel_demo) | Hadamard 函数作为感知基的 demo，Matlab / Python 双实现 | MATLAB + Python | ~38  | ☐ 未跑 ☐ 跑通 | **双语言对照**，理解"测量矩阵 × 单像素强度 → 图像" |
| [zibangzhang/Real-time-Fourier-single-pixel-imaging](https://github.com/zibangzhang/Real-time-Fourier-single-pixel-imaging) | 二值抖动正弦强度图案实现快速 FSPI                      | MATLAB          | ~34  | ☐ 未跑 ☐ 跑通 | 含图案生成 → 工程价值高                            |

---

## 深度学习方向

| 仓库                                                         | 说明                                                         | 语言   | ⭐    | 状态          | 备注                           |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------ | ---- | ------------- | ------------------------------ |
| [FeiWang0824/physics-driven-fine-tuning](https://github.com/FeiWang0824/physics-driven-fine-tuning) | 论文 *Single-pixel imaging using physics enhanced deep learning* 的 demo 代码 | Python | ~44  | ☐ 未跑 ☐ 跑通 | **物理驱动微调**，思路值得借鉴 |
| [Gang-Qu/HATNet-SPI](https://github.com/Gang-Qu/HATNet-SPI)  | Dual-scale Transformer 做大规模单像素成像                    | Python | ~30  | ☐ 未跑 ☐ 跑通 | 当前 SOTA 方向参考             |
| [Polarbeartnt/SP-ILC](https://github.com/Polarbeartnt/SP-ILC) | 同时做单像素成像 + 目标定位 + 分类                           | Python | ~12  | ☐ 未跑 ☐ 跑通 | 不只重建图像                   |
| [zhaoxiaodong95/Single_Pixel_Camera](https://github.com/zhaoxiaodong95/Single_Pixel_Camera) | 深度学习单像素成像系统（含实验链路）                         | Python | ~11  | ☐ 未跑 ☐ 跑通 |                                |
| [stephenllh/bcs-unet](https://github.com/stephenllh/bcs-unet) | 块压缩感知 + U-Net 的单像素重建                              | Python | ~10  | ☐ 未跑 ☐ 跑通 | 硕士项目，代码清晰             |
| [1577148518/single-photon-counting-imaging](https://github.com/1577148518/single-photon-counting-imaging) | 论文配套：联合追踪亚像素扫描采样的深度学习单光子计数压缩成像 | —      | ~10  | ☐ 未跑 ☐ 跑通 |                                |
| [songkai2020/SSDL](https://github.com/songkai2020/SSDL)      | 单光子单像素成像的**自监督**深度学习                         | —      | ~6   | ☐ 未跑 ☐ 跑通 |                                |
| [OPaRu2611/No-Reference-QA-Neural-Hadamard-SPI](https://github.com/OPaRu2611/No-Reference-Quality-Assessment-of-Neural-Assisted-Hadamard-Based-Single-Pixel-Imaging) | 神经辅助 Hadamard 单像素成像的**无参考质量评价**，含仿真与实测对比 DIP 去噪 | —      | —    | ☐ 未跑 ☐ 跑通 | 评价指标方向                   |
| [baturalpguven/...-GANs](https://github.com/baturalpguven/Deep-Learning-Reconstruction-for-Single-Pixel-Imaging-with-Generative-Adversarial-Networks) | cGAN 单像素成像重建（ICIP 2023）                             | —      | ~4   | ☐ 未跑 ☐ 跑通 |                                |

---

## 鬼成像（GI / CGI / DGI）

| 仓库                                                         | 说明                                                         | 语言       | ⭐    | 状态          | 备注                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ---------- | ---- | ------------- | ---------------------------- |
| [pj-sun-optics/Computational-Ghost-Imaging](https://github.com/pj-sun-optics/Computational-Ghost-Imaging) | 计算鬼成像 MATLAB 仿真，含流式 DGI 重建与高分辨率精化        | MATLAB     | —    | ☐ 未跑 ☐ 跑通 | **DGI 流式实现**，适合做对照 |
| [yoloxiaobai/Simulation-Reconstruction-System](https://github.com/yoloxiaobai/Simulation-Reconstruction-System) | 计算鬼成像辅助仿真与重建系统                                 | —          | ~1   | ☐ 未跑 ☐ 跑通 |                              |
| [tianzi41/ghost-imaging-lab](https://github.com/tianzi41/ghost-imaging-lab) | **浏览器里跑的单像素鬼成像模拟器**，直观展示图像如何从噪声中被算出 | JavaScript | —    | ☐ 未跑 ☐ 跑通 | 用来建立直觉/教学演示极好    |
| [Kleven2k/ghost-imager](https://github.com/Kleven2k/ghost-imager) | **FPGA 实现**（Nexys Video Artix-7），结构化光图案 + 片上采集与重建 | Verilog/C  | —    | ☐ 未跑 ☐ 跑通 | 硬件方向参考                 |

---

## 压缩感知 / 硬件实现

| 仓库                                                         | 说明                                           | 语言   | ⭐    | 状态          | 备注               |
| ------------------------------------------------------------ | ---------------------------------------------- | ------ | ---- | ------------- | ------------------ |
| [PONT-MAX/TQET33](https://github.com/PONT-MAX/TQET33)        | FOI 学位项目：SWIR 波段的压缩感知单像素相机    | —      | ~2   | ☐ 未跑 ☐ 跑通 | 短波红外方向       |
| [PGKhanh123/ISTA](https://github.com/PGKhanh123/ISTA)        | 用 ISTA 做单像素相机的压缩感知重建             | —      | —    | ☐ 未跑 ☐ 跑通 |                    |
| [PGKhanh123/IHT_Image_processing_for_single_pixel_camera](https://github.com/PGKhanh123/IHT_Image_processing_for_single_pixel_camera) | 用 IHT 做单像素相机的压缩感知重建              | —      | —    | ☐ 未跑 ☐ 跑通 | 与 ISTA 可成对比较 |
| [TaviG/Compressed-Sensing](https://github.com/TaviG/Compressed-Sensing) | 压缩感知 / 单像素相机                          | —      | —    | ☐ 未跑 ☐ 跑通 |                    |
| [christiansteck/Compressed-Sensing](https://github.com/christiansteck/Compressed-Sensing) | 受单像素相机启发的压缩感知示例                 | —      | —    | ☐ 未跑 ☐ 跑通 |                    |
| [1Robert1Business1/Single-Pixel-Camera](https://github.com/1Robert1Business1/Single-Pixel-Camera) | 低成本单像素相机原型 + MATLAB 压缩感知重建仿真 | MATLAB | —    | ☐ 未跑 ☐ 跑通 |                    |

---

## 术语对照表

> 搜不到项目，八成是词不对。这个领域同一个东西有很多叫法。

| 中文                | 英文 / 缩写                         | 说明                                                         |
| ------------------- | ----------------------------------- | ------------------------------------------------------------ |
| 单像素成像          | Single-Pixel Imaging (SPI)          | 总称，**搜索首选关键词**                                     |
| 鬼成像              | Ghost Imaging (GI)                  | 关键词会被 Ghost 博客平台污染，需配合 `in:readme` 或改用 `single-pixel` |
| 计算鬼成像          | Computational Ghost Imaging (CGI)   | 用空间光调制器产生已知图案，只需单像素探测器                 |
| 微分鬼成像          | Differential Ghost Imaging (DGI)    | 抑制背景噪声、提升 SNR 的经典改进                            |
| 归一化鬼成像        | Normalized Ghost Imaging (NGI)      | 抗光强波动                                                   |
| 关联成像            | Correlated Imaging                  | 更偏物理表述，国内文献常见                                   |
| 傅里叶单像素成像    | Fourier Single-Pixel Imaging (FSPI) | 频域采样，张子邦等人的代表工作                               |
| Hadamard 单像素成像 | Hadamard SPI / HSPI                 | 正交基采样，重建快、抗噪                                     |
| 压缩感知单像素成像  | SPI + Compressed Sensing (CS)       | 欠采样重建                                                   |
| 结构化照明          | Structured Illumination             | 图案投影                                                     |
| 空间光调制器        | SLM / DMD                           | 数字微镜器件（DMD）是常用图案发生器                          |

---

## 如何判断一个库值不值得用

本领域普遍 star 极低（最高不到 100），**不要用 star 门槛筛**。改看：

- [ ] 最后 commit 在 1 年内？（`pushed:>2023-01-01`）
- [ ] 有 `examples/` 或可直接运行的脚本？
- [ ] 有 `LICENSE`？（论文代码常常没有 → 严格来说不可再分发）
- [ ] 依赖的 MATLAB 工具箱你装了吗？（Image Processing / Wavelet 常被漏提）
- [ ] 有 `CITATION.cff` 或 README 引用段 → 能否在论文里引用？
- [ ] 作者是否还在维护（看 Issues 有无回复）

---

## 踩坑记录

> 用一条删一条，这是这份清单最值钱的部分。

- [ ] 本领域代码 **绝大多数是 MATLAB**，年代跨度 R2016–R2023，先确认工具箱版本再动手
- [ ] 大量论文代码只在 **Zenodo / 期刊补充材料 / 作者主页 zip** 里，GitHub 上搜不到
- [ ] GitHub 搜 `ghost imaging` 会被 Ghost CMS 相关仓库淹没，必须加 `in:readme` 或换词
- [ ] _（自己补）_

---

## 贡献方式

发现遗漏或失效链接，欢迎开 Issue 或 PR。要求：
1. 一个仓库一行，写清用途（不要只写"单像素成像代码"）
2. 标明语言与是否需要商业工具箱
3. 死链请直接提 PR 删除

## License

[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) — 随便用。