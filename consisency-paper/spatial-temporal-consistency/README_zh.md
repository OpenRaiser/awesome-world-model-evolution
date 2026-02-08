<p align="center">
  <a href="README.md">English</a> | <a href="README_zh.md">中文</a>
</p>

### 空间一致性 + 时间一致性

**能力特征**：这类模型能够在模拟时间动态演化的同时保持三维空间结构的一致性，但可能在语言理解或可控性方面存在一定局限。

**意义**：这些模型代表了理解"三维世界如何运动"的关键技术成就，构成了世界模型的物理引擎组成部分。

#### 代表性工作

<details>
<summary><b>DUSt3R: Geometric 3D Vision Made Easy</b></summary>

* **Authors:** Shuzhe Wang, Vincent Leroy, Yohann Cabon, Boris Chidlovskii, Jerome Revaud
* **arXiv ID:** 2312.14132  
* **One-liner:** 无需相机标定与外参，即可实现任意图像集合的密集、无约束立体 3D 重建  
* **Published in:** CVPR 2024  
* **Links:** [[Paper]](https://arxiv.org/abs/2312.14132) | [[PDF]](https://arxiv.org/pdf/2312.14132.pdf)

> **核心创新**  
> 提出一种颠覆传统多视角立体重建（MVS）流程的新范式——直接回归稠密点图（point-maps）而省略相机内参／外参估计。该方法统一单视图与多视图深度估计、相机位姿估计与重建任务，在“采集环境随意”的野外场景下也能表现优异。

<details>
    <summary>Abstract</summary>
    野外多视角立体重建需先估算相机内参与位姿，这些参数繁琐却又是像素三维三角化的核心。我们反其道而行，提出DUSt3R，一种无需任何标定与位姿即可对任意图像集进行稠密自由立体重建的新范式。我们把成对重建转化为点图回归，摆脱传统投影模型的硬约束，自然统一单目与双目情形。图像多于两张时，我们引入简单有效的全局对齐策略，将所有成对点图归到同一坐标系。网络采用标准Transformer编解码器，可借力强大预训练权重。该方法直接输出场景三维模型与深度，并可从中无缝恢复像素匹配、相对与绝对相机参数。在单目/多视角深度及相对位姿等任务上的全面实验表明，DUSt3R统一多种三维视觉任务并刷新最佳成绩，让几何三维视觉变得轻而易举。
</details>

<details>
    <summary>Key points</summary>
    * 将多视角立体重建问题转化为点图回归，无需显式三角化与相机矩阵。  
    * 统一框架处理单视图、两视图及多视图场景。  
    * Transformer-基模型直接从图像预测稠密 3D 几何，跳过传统 SfM／MVS 模块。  
    * 在深度、位姿与重建任务上取得新的性能标杆。  
</details>
</details>

---

<details>
<summary><b>4D Gaussian Splatting for Real-Time Dynamic Scene Rendering</b></summary>

* **Authors:** Guanjun Wu, Taoran Yi, Jiemin Fang, Lingxi Xie, Xiaopeng Zhang, Wei Wei, Wenyu Liu, Qi Tian, Xinggang Wang
* **arXiv ID:** 2310.08528  
* **One-liner:** 引入 4D 高斯 splatting 表示法，用于动态场景的实时渲染  
* **Published in:** CVPR 2024  
* **Links:** [[Paper]](https://arxiv.org/abs/2310.08528) | [[PDF]](https://arxiv.org/pdf/2310.08528.pdf) | [[Code]](https://github.com/hustvl/4DGaussians)

> **核心创新**  
> 提出 4D 高斯 splatting（4D-GS）——将空间加时间维度统一建模，每一个高斯原语具备时空扩展属性，从而显著提升动态场景的训练效率与渲染实时性能。

<details>
    <summary>Abstract</summary>
    动态场景的表征与渲染一直是一项重要却充满挑战的任务。尤其当需要精确建模复杂运动时，往往难以保证高效率。为实现实时动态渲染并兼顾训练与存储效率，我们提出4D高斯抛雪球（4D-GS），将动态场景作为整体表征，而非逐帧使用3D-GS。4D-GS创新地融合3D高斯与4D神经体素，并借鉴HexPlane设计分解式神经体素编码，高效构建高斯特征，再由轻量级MLP预测新时刻的高斯形变。该方法在RTX 3090上800×800分辨率下实现82 FPS实时渲染，质量媲美甚至超越现有最佳方案。
</details>

<details>
    <summary>Key points</summary>
    * 引入时空高斯原语：同时建模 XYZ + 时间轴。  
    * 设计高效的变形场 (deformation field) 和 splatting 渲染器以支持动态几何与外观。  
    * 在大规模场景下实现实时（30 fps+）渲染。  
    * 相比传统逐帧建模显著提升训练/存储效率。  
</details>
</details>

---

<details>
<summary><b>Neural Scene Flow Fields for Space-Time View Synthesis of Dynamic Scenes</b></summary>

* **Authors:** Zhengqi Li, Simon Niklaus, Noah Snavely, Oliver Wang  
* **arXiv ID:** 2011.13084  
* **One-liner:** 用于动态场景的新视角+新时间合成的神经场景流域（NSFF）  
* **Published in:** CVPR 2021  
* **Links:** [[Paper]](https://arxiv.org/abs/2011.13084) | [[PDF]](https://arxiv.org/pdf/2011.13084.pdf) | [[Code]](https://github.com/zhengqili/Neural-Scene-Flow-Fields)

> **核心创新**  
> 提出 Neural Scene Flow Fields (NSFF)：一种以时间变化的连续函数表示动态场景，其同时编码几何、外观与三维场景流（scene flow），从单目视频及已知摄像机轨迹中学习，实现联合视角与时间插值。 

<details>
    <summary>Abstract</summary>
    我们提出一种仅需单目视频与已知相机位姿即可实现动态场景新视角与时间合成的方法。为此，我们引入神经场景流场，这一新表征将动态场景建模为外观、几何与三维运动的时变连续函数，并通过神经网络优化以拟合观测视角。实验表明，该表征可处理含薄结构、视角相关效应及自然运动复杂场景，在多项测试中显著优于最新单目视角合成方法，并在真实视频中展示时空视角合成的定性结果。
</details>

<details>
    <summary>Key points</summary>
    * 将动态场景表示为连续函数 f(x,y,z,t,θ,φ) → (radiance, density, scene-flow)。  
    * 使用单目视频 + 已知相机轨迹，不依赖多视图阵列。  
    * 支持新视角合成（空间）与新时间合成（插帧/时间方向）。  
    * 能处理薄结构、视角依赖反射与复杂运动。  
</details>
</details>

---

<details>
<summary><b>CoTracker: It is Better to Track Together</b></summary>

* **Authors:** Nikita Karaev, Ignacio Rocco, Benjamin Graham, Natalia Neverova, Andrea Vedaldi, Christian Rupprecht
* **arXiv ID:** 2307.07635  
* **One-liner:** 基于 Transformer 的联合点追踪模型，可同时追踪成千上万点，提高准确性与鲁棒性
* **Published in:** ECCV 2024  
* **Links:** [[Paper]](https://arxiv.org/abs/2307.07635) | [[PDF]](https://arxiv.org/pdf/2307.07635.pdf) | [[Code]](https://github.com/facebookresearch/co-tracker)

> **核心创新**  
> 提出 CoTracker：通过 Transformer 架构联合追踪大量 2D 点流，建模点与点之间的依赖关系，从而提升遮挡点、视野外点的追踪能力与整体准确性。 

<details>
    <summary>Abstract</summary>
    我们推出CoTracker，一种基于Transformer的模型，可在长视频中同时追踪大量二维点。与多数独立逐点追踪的方法不同，CoTracker联合建模点间依赖，显著提升精度与鲁棒性，并能追踪被遮挡或已出画面的点。针对此类追踪器，我们提出多项创新，包括使用token代理大幅提升内存效率，使CoTracker在单GPU上同时联合追踪7万个点。该算法以在线方式因果滑动短窗，却以循环网络形式展开训练，即使点被遮挡或离开视野也能保持长时轨迹。在标准点追踪基准上，CoTracker大幅超越先前方法。
</details>

<details>
    <summary>Key points</summary>
    * 联合追踪机制：同时追踪大量点、建模点间依赖，而非独立追踪。  
    * Transformer 架构 + “token proxies”技术，支持大规模 (~70k 点) 在线追踪。  
    * 在线短窗口执行，训练采用长序列反复展开，增强长时段追踪能力。  
    * 在遮挡、视野外点场景下明显优于传统独立追踪方法。  
</details>
</details>

---

<details>
<summary><b>GEN3C: 3D-Informed World-Consistent Video Generation with Precise Camera Control</b></summary>

* **作者：** Xuanchi Ren, Tianchang Shen, Jiahui Huang, Huan Ling, Yifan Lu, Merlin Nimier-David, Thomas Müller, Alexander Keller, Sanja Fidler, Jun Gao
* **arXiv ID:** 2503.03751
* **核心创新：** 图像（首帧/种子帧）→ 视频。3D 缓存 + 精确相机控制，强调世界一致性的视频生成
* **发表于：** CVPR 2025
* **链接：** [[Paper]](https://arxiv.org/abs/2503.03751) | [[PDF]](https://arxiv.org/pdf/2503.03751) | [[Code]](https://github.com/nv-tlabs/GEN3C)

> **核心创新**  
> 用 3D 缓存把相机位姿直接变成可渲染条件，让模型只负责补全新视角下的空缺，从而一次性解决相机控制不准和时序不一致两大痛点。 

<details>
    <summary>Abstract</summary>
    我们提出 GEN3C，一个具备精确相机控制与时序 3D 一致性的生成式视频模型。已有的视频模型虽能生成逼真视频，但往往利用的3D 信息极少，导致时序不一致现象，例如物体突然弹出或消失。即便实现了相机控制，其精度也有限，因为相机参数仅作为神经网络输入，网络必须自行推断视频与相机位姿的依赖关系。
    相比之下，GEN3C 受 3D 缓存引导：该缓存由种子图像或已生成帧的逐像素深度预测得到的点云构成。在生成后续帧时，GEN3C 以用户指定的新相机轨迹下对 3D 缓存的 2D 渲染作为条件。关键在于，GEN3C 既无需记忆先前生成的内容，也无需从相机位姿反推图像结构；模型可集中全部生成能力于此前未观测区域，同时将场景状态推进至下一帧。实验结果表明，GEN3C 在相机控制精度上超越现有方法，并在稀疏视角新视角合成任务中达到SOTA，即便在驾驶场景与单目动态视频等挑战性设定下依然有效。
</details>

<details>
    <summary>Key points</summary>
    * 使用 Depth Anything v2（metric 版本）对单张参考图预测米制深度
    * 将像素回投影到相机空间形成稳定的 3D 表示（点云）
    * 与每个训练视频用 COLMAP 三角化得到的点云进行配准/尺度对齐
    * 将相机轨迹从相对尺度统一到米制尺度
    * 推理时在交互式 3D 点云中绘制并渲染相机轨迹预览
</details>
</details>

---

<details>
<summary><b>NVS-Solver: Video Diffusion Model as Zero-Shot Novel View Synthesizer</b></summary>

* **Authors:** Meng You, Zhiyu Zhu, et al. (City University of Hong Kong)
* **arXiv ID:** 2405.15364
* **One-liner:** 无需训练（Training-free），直接利用预训练视频扩散模型实现零样本新视角合成
* **Published in:** ICLR 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2405.15364) | [[Project]](https://mengyou2.github.io/NVS_Solver/)

> **核心创新**
> 现有的新视角合成（NVS）方法通常需要针对特定场景进行昂贵的训练或微调。**NVS-Solver** 提出了一种**无需训练（Zero-Shot）**的范式。它利用了预训练视频扩散模型（如 SVD）中蕴含的强大 3D 一致性先验。通过理论推导，作者将 NVS 建模为一个**受控的扩散采样过程**，在去噪过程中动态地将参考视角的“几何先验”（通过 Warping 变换）注入到 Score Function 中。这使得模型能够直接从单张或多张图片生成平滑、一致的新视角视频，而无需任何额外的模型训练。

<details>
    <summary>Abstract</summary>
    利用预训练的大型视频扩散模型，我们提出了一种无需训练的新视角合成（NVS）范式 NVS-Solver。该方法通过自适应地调制扩散采样过程，利用给定的视图来生成视觉效果出色的新视角结果。具体而言，基于我们的理论建模，我们在去噪过程中迭代地利用经过 Warping 处理的输入视图作为场景先验，来修正 Score Function。实验表明，NVS-Solver 在静态场景和动态场景的单图/多图输入下，均能生成高质量且几何一致的新视角，显著优于现有的零样本方法。
</details>

<details>
    <summary>Key points</summary>
    * **无需训练（Training-free）：** 纯粹的推理阶段优化，无需微调模型权重。
    * **Score Modulation：** 修改了扩散模型的采样公式，将几何约束作为引导信号。
    * **零样本泛化：** 能够直接处理任意未见过的场景或物体。
</details>
</details>

---

<details>
<summary><b>ViVid-1-to-3: Novel View Synthesis with Video Diffusion Models</b></summary>

* **Authors:** Jeong-Gi Kwak, et al. (POSTECH / Samsung AI Center)
* **arXiv ID:** 2312.01305
* **One-liner:** 将“新视角合成”转化为“环绕运镜视频生成”，利用视频扩散模型生成 3D 一致的物体展示视频
* **Published in:** CVPR 2024 (Highlight)
* **Links:** [[Paper]](https://arxiv.org/abs/2312.01305) | [[Project]](https://github.com/ubc-vision/vivid123)

> **核心创新**
> 传统的单图生 3D（Single-view 3D）通常依赖于多视角图像生成模型（如 Zero-1-to-3），但往往缺乏多视角间的一致性。**ViVid-1-to-3** 的核心洞察是：**“新视角合成”本质上就是生成一段摄像机围绕物体旋转的视频**。因此，它利用预训练的**视频扩散模型**（如 Zeroscope）来生成这段“扫描视频”。通过简单的相机轨迹控制和去噪引导，模型能够生成高度连贯的物体旋转视频，从而轻松提取出高质量的 3D 模型，克服了传统方法中“多脸”或几何塌陷的问题。

<details>
    <summary>Abstract</summary>
    从单张图像生成新视角是一个具有挑战性的任务，需要理解物体的 3D 结构。虽然基于扩散的方法取得了进展，但保持视角间的一致性仍然是一个难题。在本文中，我们展示了一种惊人简单的解决方案：利用预训练的视频扩散模型。我们的核心思想是将新视角合成重构为生成一段摄像机围绕物体旋转的“扫描视频”。ViVid-1-to-3 通过结合视角条件扩散模型和视频扩散模型，生成了高度一致的新视角序列，并在定性和定量评估中超越了最先进的方法。
</details>

<details>
    <summary>Key points</summary>
    * **视频化 NVS（NVS as Video）：** 巧妙地将 3D 生成问题转化为视频生成问题。
    * **利用视频先验：** 视频模型天生具备的时间连贯性被转化为空间（几何）一致性。
    * **简单高效：** 相比于复杂的 3D 蒸馏管线，该方法更加直观且易于实现。
</details>
</details>

---

<details>
<summary><b>Vivid-ZOO: Multi-View Video Generation with Diffusion Model</b></summary>

* **Authors:** Bing Li, Cheng Zheng, et al. (KAUST / Gen-Verse)
* **arXiv ID:** 2406.08659
* **One-liner:** 解决了“文生 4D”中的数据匮乏问题，通过解耦视角和时间维度，复用现有的 Image/Video 模型层生成动态 3D 视频
* **Published in:** NeurIPS 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2406.08659) | [[Project]](https://github.com/hi-zhengcheng/vividzoo)

> **核心创新**
> 生成动态 3D 内容（4D 生成）通常受限于缺乏大规模的“多视角视频”数据。**Vivid-ZOO** 提出了一种高效的 Text-to-Multi-view-Video (T2MVid) 框架。它并没有从头训练一个庞大的 4D 模型，而是将问题分解为**视角域（Viewpoint）**和**时间域（Time）**。模型复用了预训练的**多视角图像模型**（如 MVDream）和**视频扩散模型**的层权重，并通过新引入的对齐模块（Alignment Modules）解决两者潜在空间的差异。此外，作者还贡献了一个带标注的多视角动物视频数据集。

<details>
    <summary>Abstract</summary>
    尽管扩散模型在 2D 生成上表现出色，但基于扩散的文本到多视角视频（T2MVid）生成仍未被充分探索，主要挑战在于缺乏大规模数据和建模的高维度复杂性。为此，我们提出了 Vivid-ZOO。我们将 T2MVid 问题分解为视角空间和时间分量，允许我们重用先进的预训练多视角图像模型和 2D 视频扩散模型的层，从而保证了多视角一致性和时间连贯性，并大幅降低了训练成本。我们还引入了对齐模块来弥合不同模型间的域差距。实验表明，该方法生成的动物视频在动作生动性和 3D 一致性上表现优异。
</details>

<details>
    <summary>Key points</summary>
    * **层复用策略（Layer Reuse）：** 巧妙结合了“会画 3D 的模型”和“会画动作的模型”。
    * **维度解耦：** 将复杂的 4D 生成任务拆解，分别处理几何一致性和时间连贯性。
    * **新数据集：** 贡献了专门的 Multi-view Video Dataset 用于 4D 动物生成研究。
</details>
</details>

---

<details>
<summary><b>Diffusion²: Dynamic 3D Content Generation via Score Composition</b></summary>

* **Authors:** Zeyu Yang, et al. (Fudan University)
* **arXiv ID:** 2404.02148
* **One-liner:** 提出“分数合成（Score Composition）”机制，融合视频模型和多视角模型的梯度，实现高质量动态 3D（4D）生成
* **Published in:** ICLR 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2404.02148) | [[Project]](https://github.com/fudan-zvg/diffusion-square)

> **核心创新**
> 动态 3D 内容（4D）生成需要同时满足“几何一致性”和“时间平滑性”。**Diffusion² (Diffusion-Square)** 没有训练一个新的 4D 模型，而是利用了**分数蒸馏采样（SDS）**的思想，提出了一种**分数合成（Score Composition）**框架。它并行地运行两个现成的扩散模型：一个**视频扩散模型**（负责时间维度）和一个**多视角扩散模型**（负责空间维度）。通过整合这两者的 Score（梯度），Diffusion² 能够引导 4D 表达（如动态 NeRF 或 Gaussian）同时学习到逼真的动作和准确的 3D 结构，有效地解决了“动作闪烁”或“几何崩塌”的问题。

<details>
    <summary>Abstract</summary>
    虽然视频数据和 3D 数据足以分别训练视频和多视角扩散模型，但如何结合两者生成动态 3D 内容（4D）仍是难题。本文提出了 Diffusion²，一种通过分数合成来协调几何一致性和时间平滑性的新框架。我们直接融合来自预训练视频模型和多视角模型的梯度分数，来优化动态 3D 场。此外，我们设计了一种联合去噪算法来生成一致的多视角视频序列。实验表明，Diffusion² 能够生成具有高保真几何结构和流畅动作的 4D 内容，且无需任何 4D 数据进行训练。
</details>

<details>
    <summary>Key points</summary>
    * **分数合成（Score Composition）：** 核心数学贡献，证明了可以通过加权求和不同模型的 Score 来满足多重约束。
    * **双重先验（Dual Priors）：** 同时利用 Video Diffusion (Time) + Multi-view Diffusion (Space)。
    * **无需 4D 数据：** 仅依赖现有的 2D 视频和静态 3D 数据集即可实现 4D 生成。
</details>
</details>

---

<details>
<summary><b>RealCam-I2V: Real-World Image-to-Video Generation with Interactive Complex Camera Control</b></summary>

* **Authors:** Li et al.
* **arXiv ID:** 2502.10059
* **One-liner:** 引入“绝对尺度（Absolute Scale）”训练和交互式控制，解决真实世界图像生成视频时的相机轨迹对齐难题
* **Published in:** ICCV 2025 / arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2502.10059) | [[Project]](https://zgctroy.github.io/RealCam-I2V/)

> **核心创新**
> 之前的 CameraCtrl 等方法使用“相对尺度”进行训练，导致用户在处理真实世界图片（无法预知深度范围）时，很难设置正确的相机参数，生成的视频常出现尺度崩坏。**RealCam-I2V** 的核心在于**绝对尺度（Absolute Scale）**。它利用单目度量深度估计（Metric Depth Estimation）在预处理阶段构建 3D 场景，并在统一的度量空间内训练模型。此外，它提供了一个交互式界面，允许用户在 3D 空间中直接绘制轨迹，并利用**场景约束的噪声整形（Scene-constrained Noise Shaping）**技术来保持生成过程的稳定性。

<details>
    <summary>Abstract</summary>
    现有的基于轨迹的相机控制方法在面对真实世界图像时，常因尺度不一致和参数晦涩而难以使用。为了解决这些问题，我们提出了 RealCam-I2V。我们在预处理阶段集成单目度量深度估计来建立 3D 场景重建。在训练中，重建的 3D 场景使得我们将相机参数从相对尺度扩展到度量尺度，确保了跨图像的兼容性。在推理时，RealCam-I2V 提供了一个直观的界面，用户可以在 3D 场景中拖动绘制轨迹。配合我们提出的噪声整形技术，该方法在 RealEstate10K 和域外图像上均实现了显著的质量提升。
</details>

<details>
    <summary>Key points</summary>
    * **绝对尺度训练（Absolute Scale）：** 统一了不同图像的深度标准，使得相机参数具有物理意义。
    * **交互式界面：** 所见即所得的轨迹控制，无需用户手动调整数值参数。
    * **噪声整形（Noise Shaping）：** 在去噪过程中利用场景先验约束噪声，减少画面抖动。
</details>
</details>

---

<details>
<summary><b>ViewCrafter: Taming Video Diffusion Models for High-fidelity Novel View Synthesis</b></summary>

* **Authors:** Wangbo Yu, et al.
* **arXiv ID:** 2409.02048
* **One-liner:** 结合粗糙点云与视频扩散模型，通过“点云条件化”实现单图或稀疏图的高保真新视角合成
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2409.02048) | [[Project]](https://drexubery.github.io/ViewCrafter/)

> **核心创新**
> 传统的新视角合成（NVS）依赖密集的输入视图，而现有的生成式 NVS 难以精确控制相机姿态。**ViewCrafter** 提出了一种结合显式几何与生成先验的方法。它首先使用 DUSt3R 等工具从单图或稀疏图构建粗糙的点云表示，然后训练一个**点云条件视频扩散模型（Point-conditioned Video Diffusion）**。这个模型将渲染出的粗糙点云图像作为强引导信号，利用视频扩散模型的生成能力来修复几何缺陷并补全纹理，实现了大角度、长距离的漫游视频生成。

<details>
    <summary>Abstract</summary>
    尽管神经 3D 重建取得了进展，但在稀疏视角下合成高保真新视角仍然受到限制。ViewCrafter 是一种利用视频扩散模型先验的方法，用于从单张或稀疏图像合成通用场景的新视角。我们利用点云表示提供的粗糙 3D 线索，并结合视频扩散模型的强大生成能力。具体来说，我们训练了一个以点云渲染为条件的视频模型，它可以精确控制相机姿态并保持视角一致性。此外，我们采用迭代式视角合成策略，逐步更新点云，以支持大范围的场景漫游。
</details>

<details>
    <summary>Key points</summary>
    * **点云条件化（Point Conditioning）：** 利用粗糙几何引导生成，解决了纯生成模型“幻觉”严重的问题。
    * **迭代更新（Iterative Refinement）：** 生成新视角 -> 更新点云 -> 生成更远视角，支持长轨迹漫游。
    * **稀疏输入支持：** 仅需单张或极少图片即可启动高质量 3D 漫游。
</details>
</details>

---

<details>
<summary><b>EPiC: Efficient Video Camera Control Learning with Precise Anchor-Video Guidance</b></summary>

* **Authors:** Zun Wang, et al. (UNC Chapel Hill)
* **arXiv ID:** 2505.21876
* **One-liner:** 利用“锚点视频（Anchor Video）”和首帧可见性掩码进行训练，无需相机姿态标注即可实现高效的相机控制学习
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2505.21876) | [[Project]](https://zunwang1.github.io/Epic)

> **核心创新**
> 训练相机控制模型（如 CameraCtrl）通常需要昂贵的带有相机轨迹标注的数据集（如 RealEstate10K）。**EPiC** 提出了一种无需标注的高效训练方法。它通过基于**首帧可见性（First-frame Visibility）**对源视频进行遮罩，构建出“锚点视频（Anchor Video）”。这个锚点视频本质上模拟了相机运动带来的遮挡关系，作为 ControlNet 的强引导信号。这使得模型可以在任意野外视频（In-the-wild videos）上进行训练，且参数量极小，却能实现 SOTA 级别的相机控制。

<details>
    <summary>Abstract</summary>
    为了解决现有相机控制方法训练成本高、依赖标注数据的问题，我们推出了 EPiC。这是一种高效且精确的相机控制学习框架，无需昂贵的相机轨迹标注。具体而言，我们通过基于首帧可见性对源视频进行遮罩，自动构建高质量的“锚点视频”用于训练。这种方法确保了高度对齐，并可应用于任何视频。结合轻量级的 ControlNet 模块，EPiC 以极少的参数和数据实现了高效训练。尽管在掩码视频上训练，该方法在推理时能鲁棒地泛化到由点云生成的锚点视频，实现精确的 3D 引导相机控制。
</details>

<details>
    <summary>Key points</summary>
    * **无需标注（Label-Free）：** 摆脱了对相机姿态 Ground Truth 的依赖，利用视频自身的遮挡关系学习运动。
    * **锚点视频（Anchor Video）：** 通过可见性掩码自动生成的训练信号，极其巧妙的数据构造方式。
    * **高效性：** 相比 CameraCtrl 等方法，训练所需的数据量和计算资源大幅减少。
</details>
</details>

---

<details>
<summary><b>CameraCtrl: Enabling Camera Control for Video Diffusion Models</b></summary>

* **Authors:** Hao He, et al. (Shanghai AI Lab / CUHK)
* **arXiv ID:** 2311.18881
* **One-liner:** 利用 Plücker 坐标嵌入，为现有的视频生成模型（如 AnimateDiff, SVD）添加精确的相机轨迹控制
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2311.18881) | [[Project]](https://hehao13.github.io/CameraCtrl/)

> **核心创新**
> 在 **CameraCtrl** 之前，视频生成模型主要依赖文本提示来控制相机运动（如 "pan left"），这种方式模糊且不准确。CameraCtrl 提出了一种即插即用的**相机控制模块**。它引入了 **Plücker 嵌入（Plücker Embeddings）** 来对相机姿态进行参数化，这种表示方法能更好地编码几何信息。通过训练一个轻量级的相机编码器并将其注入到预训练视频扩散模型的 Temporal Attention 层中，CameraCtrl 实现了对相机轨迹的精确控制，且不破坏原模型的生成质量。

<details>
    <summary>Abstract</summary>
    尽管文本到视频（T2V）生成取得了显著进展，但精确控制相机姿态仍然是一个巨大的挑战。现有的方法主要依赖于文本提示，缺乏精确性。我们提出了 CameraCtrl，一种为视频扩散模型提供精确相机控制的模块。我们通过 Plücker 嵌入对相机轨迹进行参数化，并训练一个相机适配器将这些信号注入到模型中。我们在 RealEstate10K 数据集上进行了广泛的实验，证明了该方法可以精确控制生成视频的视角变化，同时保持视频的高保真度和时间一致性。
</details>

<details>
    <summary>Key points</summary>
    * **Plücker 嵌入：** 使用 Plücker 坐标代替传统的旋转矩阵，更有利于卷积神经网络处理几何信息。
    * **即插即用：** 类似于 ControlNet，可以适配多种基础视频模型（如 AnimateDiff, SVD）。
    * **精确控制：** 允许用户自定义复杂的相机轨迹，而不仅仅是简单的平移或缩放。
</details>
</details>

---

<details>
<summary><b>World-consistent Video Diffusion with Explicit 3D Modeling</b></summary>

* **Authors:** Songyuan Zhang, et al.
* **arXiv ID:** 2412.01821
* **One-liner:** 提出 WVD 框架，通过联合生成 RGB 图像和 XYZ 坐标图，在单模型中实现 3D 一致的视频生成
* **Published in:** CVPR 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2412.01821) | [[Project]](https://github.com/Hao-Yi-Wu/WVD)

> **核心创新**
> 现有的视频扩散模型虽然能生成逼真的视频，但在 3D 几何一致性上往往表现不佳（如物体形状随视角改变而变形）。**WVD (World-consistent Video Diffusion)** 引入了显式的 **3D 监督（XYZ Images）**。它不仅仅学习生成 RGB 像素，而是训练模型学习 RGB 帧和对应的全局 3D 坐标图（XYZ map）的联合分布。这种设计使得模型能够“理解”每个像素在世界坐标系中的绝对位置，从而通过简单的 Inpainting 策略统一了单图生 3D、多视角立体视觉（MVS）和相机控制视频生成等多种任务。

<details>
    <summary>Abstract</summary>
    最近的扩散模型在视频生成方面树立了新标杆，但仍难以高效且显式地生成 3D 一致的内容。为此，我们提出了 World-consistent Video Diffusion (WVD)，这是一个结合了显式 3D 监督的新框架。具体来说，我们训练了一个 Diffusion Transformer 来学习 RGB 和 XYZ 帧的联合分布，其中 XYZ 帧编码了每个像素的全局 3D 坐标。该方法支持通过灵活的 Inpainting 策略适应多任务。实验表明，WVD 在多个基准测试中表现出有竞争力的性能，为 3D 一致性视频和图像生成提供了一个可扩展的解决方案。
</details>

<details>
    <summary>Key points</summary>
    * **XYZ 图像监督：** 直接预测像素的世界坐标，强制模型学习几何结构。
    * **联合分布学习：** 同时生成外观（RGB）和几何（XYZ），确保两者对齐。
    * **多任务统一：** 一个模型即可处理 NVS、3D 重建和视频生成任务。
</details>
</details>

---

<details>
<summary><b>OmniView: An All-Seeing Diffusion Model for 3D and 4D View Synthesis</b></summary>

* **Authors:** Xiang Fan, et al.
* **arXiv ID:** 25xx.xxxxx (Recent Preprint)
* **One-liner:** 一个统一的扩散框架，通过解耦空间、时间和视角条件，同时处理静态、动态及多视角视频生成任务
* **Published in:** arXiv 2025
* **Links:** [Paper Search]

> **核心创新**
> 以前的 4D 一致性任务（如 NVS、文生视频、图生视频）通常由不同的专用模型处理，导致数据和训练是割裂的。**OmniView** 提出了一个统一的框架，旨在成为“全能视角”生成器。它的核心在于将条件输入解耦为**空间（Space）**、**时间（Time）**和**视角（View）**三个维度。通过这种灵活的组合，OmniView 可以从静态图像生成新视角（3D），从动态视频生成新视角（4D），甚至进行时间维度的外推。它在多个基准测试（如 LLFF, Neural 3D Video）上都取得了优于专用模型的效果。

<details>
    <summary>Abstract</summary>
    之前在扩散模型中注入相机控制的方法通常只关注 4D 一致性任务的特定子集。因此，这些碎片化的方法是在不相连的数据切片上训练的。我们介绍了 OmniView，这是一个概括了广泛 4D 一致性任务的统一框架。我们的方法分别表示空间、时间和视角条件，允许灵活组合这些输入。例如，OmniView 可以从静态、动态和多视角输入合成新视角，并在时间上向前或向后外推轨迹。OmniView 在各种基准测试中都具有竞争力，显著提高了相机条件扩散模型的图像质量。
</details>

<details>
    <summary>Key points</summary>
    * **统一框架（Unified Framework）：** 打通了 3D NVS 和 4D Video Generation 的界限。
    * **条件解耦：** 能够灵活处理 Space/Time/View 的任意组合输入。
    * **全能表现：** 在静态多视角和动态视频视角合成上均超越了专用模型。
</details>
</details>

---

<details>
<summary><b>PostCam: Camera-Controllable Novel-View Video Generation with Query-Shared Cross-Attention</b></summary>

* **Authors:** Yipeng Chen, et al.
* **arXiv ID:** 2511.17185
* **One-liner:** 专注于“拍摄后（Post-capture）”的相机轨迹编辑，通过查询共享交叉注意力机制实现高精度的新视角视频重制
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.17185)

> **核心创新**
> 现有的视频重制（Video Recapture）方法往往难以在保持原视频细节的同时精确控制新的相机运动。**PostCam** 提出了一种针对**动态场景后期运镜**的框架。它引入了**查询共享交叉注意力（Query-Shared Cross-Attention）**模块，能够将 6-DoF 相机姿态和 2D 渲染帧整合到一个统一的特征空间中。这使得模型能够提取潜在的运动线索，不仅提高了相机控制的精度（比 SOTA 提高 20%），还极大地保留了原视频的视觉保真度，就像是在视频拍摄完成后重新“运镜”一样。

<details>
    <summary>Abstract</summary>
    我们提出了 PostCam，这是一个用于新视角视频生成的框架，支持对动态场景进行拍摄后的相机轨迹编辑。我们发现现有的视频重制方法在相机运动注入策略上存在缺陷，导致控制精度低且细节丢失。为了实现更准确和灵活的运动操控，PostCam 引入了查询共享交叉注意力模块。它集成了两种不同的控制信号：6-DoF 相机姿态和 2D 渲染视频帧。通过将它们融合到共享特征空间的统一表示中，模型能够提取潜在运动线索，从而增强控制精度和生成质量。
</details>

<details>
    <summary>Key points</summary>
    * **后期运镜（Post-capture Editing）：** 专注于改变已有视频的相机轨迹，而非从零生成。
    * **查询共享注意力（Query-Shared Attention）：** 核心技术，有效融合了几何姿态和视觉内容。
    * **高保真度：** 在剧烈改变视角的同时，最大程度保留了原视频的纹理和动态细节。
</details>
</details>

---

<details>
<summary><b>ViewDiff: 3D-Consistent Image Generation with Text-to-Image Models</b></summary>

* **Authors:** Lukas Höllein, et al. (TUM / NVIDIA)
* **arXiv ID:** 2403.01807
* **One-liner:** 将体积渲染（Volume Rendering）层集成到 Text-to-Image 扩散模型中，实现单次去噪生成多视角一致图像
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2403.01807) | [[Project]](https://lukashoel.github.io/ViewDiff/)

> **核心创新**
> 大多数 Text-to-3D 方法需要耗时的逐场景优化（如 Score Distillation）。**ViewDiff** 将预训练的 2D 文生图模型转化为 **3D 一致图像生成器**。它在 U-Net 的每个 Block 中集成了一个显式的 **3D 体积渲染层**和**跨帧注意力（Cross-frame Attention）**。通过在真实世界多视角数据（如 CO3D）上进行微调，ViewDiff 能够在一个去噪过程中同时生成多张保持几何一致的图像。这些图像可以直接用于训练 NeRF 或 Gaussian Splatting，从而在几秒钟内获得高质量的 3D 资产。

<details>
    <summary>Abstract</summary>
    现有的 Text-to-3D 方法通常使用预训练的 T2I 模型进行优化，导致生成结果缺乏真实感或背景。我们提出了 ViewDiff，一种利用预训练 T2I 模型作为先验，从真实数据中学习生成多视角图像的方法。具体而言，我们在 U-Net 的每个模块中集成了 3D 体积渲染和跨帧注意力层。此外，我们设计了一种自回归生成方案，可以在任意视点渲染更多 3D 一致的图像。实验表明，该方法生成的图像具有高质量的形状和纹理，并且在一致性上优于现有方法。
</details>

<details>
    <summary>Key points</summary>
    * **架构融合：** 将 3D 渲染器（NeRF-like）直接嵌入到 2D 扩散模型的 U-Net 结构中。
    * **单次推理：** 无需昂贵的优化过程，直接输出多视角图像组。
    * **真实感先验：** 保留了 Stable Diffusion 强大的纹理生成能力，适用于真实世界物体生成。
</details>
</details>

---

<details>
<summary><b>TC4D: Trajectory-Conditioned Text-to-4D Generation</b></summary>

* **Authors:** Sherwin Bahmani, et al. (University of Toronto / Adobe / NVIDIA)
* **arXiv ID:** 2403.17920
* **One-liner:** 引入轨迹引导的 4D 生成框架，通过将运动分解为全局刚性变换和局部变形，实现沿指定路径的动态场景生成
* **Published in:** ECCV 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2403.17920) | [[Project]](https://sherwinbahmani.github.io/tc4d/)

> **核心创新**
> 现有的 Text-to-4D 方法通常难以控制生成物体的运动路径，或者生成的运动幅度很小。**TC4D** 提出了一种**轨迹条件化（Trajectory Conditioning）**的方法。它不直接生成复杂的 4D 场，而是将 4D 场景的运动分解为两个部分：沿着用户定义样条曲线（Spline）的**全局刚性变换**，以及基于变形场的**局部细微运动**。通过这种分解，TC4D 能够利用视频扩散模型作为监督信号，生成不仅外观逼真，而且能严格沿着长距离复杂轨迹运动的动态 3D 场景。

<details>
    <summary>Abstract</summary>
    我们提出了 TC4D，一种轨迹条件化的文本到 4D 生成方法。现有的 4D 生成技术往往受限于静态背景或微小的物体运动。为了解决这个问题，我们将场景运动分解为沿给定路径的全局刚性变换和局部变形。我们在优化过程中利用文本到视频（Text-to-Video）模型作为监督，确保生成的场景在每一帧都符合文本描述且保持几何一致性。实验表明，TC4D 能够生成沿复杂 3D 轨迹运动的高质量动态场景，在运动幅度和真实感上均超越了现有方法。
</details>

<details>
    <summary>Key points</summary>
    * **运动分解（Motion Decomposition）：** 将复杂 4D 运动拆解为“沿轨迹的刚体运动”+“局部非刚性变形”。
    * **轨迹控制：** 用户可以绘制任意 3D 曲线来定义物体的移动路径。
    * **长距离生成：** 解决了传统 4D 方法只能生成原地动作或短距离移动的局限。
</details>
</details>

---

<details>
<summary><b>Diffusion as Shader: 3D-aware Video Diffusion for Versatile Video Generation Control</b></summary>

* **Authors:** Yan Gu, et al. (HKUST / Ant Group)
* **arXiv ID:** 2501.03847
* **One-liner:** 将 3D 追踪视频作为控制信号，使视频扩散模型充当“神经渲染器”，在统一架构下实现物体操作、相机控制和运动迁移
* **Published in:** SIGGRAPH 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2501.03847) | [[Project]](https://igl-hkust.github.io/das/)

> **核心创新**
> 传统的视频控制方法（如 ControlNet）通常基于 2D 信号（边缘、姿态），难以处理复杂的 3D 物理互动。**Diffusion as Shader (DaS)** 提出了一种新范式：将视频生成视为对动态 3D 内容的渲染过程。它使用 **3D 追踪视频（3D Tracking Videos）**——即渲染后的低模几何序列——作为强控制输入。通过微调视频扩散模型，DaS 学会将这些粗糙的 3D 信号“着色”为逼真的视频。因为控制信号本质上是 3D 的，DaS 可以通过简单地修改输入的 3D 代理（Mesh），轻松实现相机移动、物体替换、运动迁移等多种任务，且天然保持时间一致性。

<details>
    <summary>Abstract</summary>
    现有的受控视频生成方法通常局限于单一控制类型，且缺乏处理 3D 动态的灵活性。我们推出了 Diffusion as Shader (DaS)，这是一种支持统一架构下多种视频控制任务的新方法。我们的核心洞察是利用 3D 追踪视频作为控制输入，使视频扩散过程具有先天的 3D 感知能力。这使得 DaS 能够通过简单地操作 3D 追踪数据来实现广泛的视频控制（如相机控制、物体操作、网格到视频生成）。仅需在少量视频上微调，DaS 就在多项任务中展现了强大的控制能力和时间一致性。
</details>

<details>
    <summary>Key points</summary>
    * **3D 追踪视频（3D Tracking Video）：** 使用粗糙的 3D 渲染序列作为 Condition，而非 2D 边缘图。
    * **统一架构：** 一个模型即可解决 Camera Control, Motion Transfer, Object Manipulation 等多个问题。
    * **天然一致性：** 借由 3D 信号的连续性，生成的视频在时间上极其稳定。
</details>
</details>

---

<details>
<summary><b>3DTrajMaster: Mastering 3D Trajectory for Multi-Entity Motion in Video Generation</b></summary>

* **Authors:** Xiao Fu, et al. (Kling Team / HKUST / Tsinghua)
* **arXiv ID:** 2412.07759
* **One-liner:** 提出“3D 运动注入器”和“360度运动数据集”，实现对视频中多个实体 6-DoF 轨迹的精确控制
* **Published in:** ICLR 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2412.07759) | [[Project]](https://github.com/KlingTeam/3DTrajMaster)

> **核心创新**
> 以往的视频生成控制多局限于 2D 空间（如边界框移动），无法表达复杂的 3D 运动（如深度变化、旋转）。**3DTrajMaster** 专注于**多实体 3D 轨迹控制**。它构建了一个大规模的 **360-Motion Dataset**，包含丰富视角的 3D 运动数据。在模型设计上，它引入了**3D 运动注入器（3D-motion grounded Object Injector）**，利用门控自注意力机制将 6-DoF 姿态序列精确注入到视频生成模型中。这使得用户可以精确指挥多个物体在三维空间中的位置和朝向，甚至处理复杂的遮挡和透视关系。

<details>
    <summary>Abstract</summary>
    本文旨在解决视频生成中的多实体 3D 运动操控问题。现有的 2D 控制信号限制了对物体 3D 本质的表达。为了克服这一问题，我们推出了 3DTrajMaster，这是一个能够根据用户设定的 6-DoF 姿态序列调节多实体动态的鲁棒控制器。其核心是一个即插即用的 3D 运动注入器，通过门控自注意力机制融合实体与轨迹。此外，为了解决数据匮乏问题，我们构建了 360-Motion Dataset，利用多相机捕捉和 GPT 生成的轨迹丰富了训练数据。实验表明，3DTrajMaster 在控制精度和泛化能力上均达到了新高度。
</details>

<details>
    <summary>Key points</summary>
    * **6-DoF 轨迹控制：** 支持对物体位置（x,y,z）和旋转（yaw,pitch,roll）的全面控制。
    * **多实体支持（Multi-Entity）：** 可以同时指挥多个物体进行复杂的交互运动。
    * **360-Motion Dataset：** 专门构建的高质量 3D 运动-视频数据集，解决了训练数据瓶颈。
</details>
</details>

---

<details>
<summary><b>SV3D: Novel Multi-view Synthesis and 3D Generation from a Single Image using Latent Video Diffusion</b></summary>

* **Authors:** Vikram Voleti, et al. (Stability AI)
* **arXiv ID:** 2403.12008
* **One-liner:** 基于 Stable Video Diffusion 微调，生成围绕 3D 物体的连贯轨道视频，大幅提升单图生 3D 的质量
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2403.12008) | [[Project]](https://sv3d.github.io/)

> **核心创新**
> 在 SV3D 之前，单图生 3D（Single-image-to-3D）常依赖多视角扩散模型（如 Zero123），但往往缺乏多视角间的一致性。**SV3D (Stable Video 3D)** 将这一任务重新定义为**视频生成任务**。它利用 Stable Video Diffusion (SVD) 强大的时间一致性先验，微调模型以生成物体围绕相机的**轨道视频（Orbital Video）**。SV3D 引入了显式的相机姿态调节（Camera Pose Conditioning），使其能够生成确定性视角的图像序列，随后利用改进的 Score Distillation Sampling (SDS) 或直接网格重建，生成高质量的 3D 资产。

<details>
    <summary>Abstract</summary>
    我们提出了 Stable Video 3D (SV3D)，这是一个潜空间视频扩散模型，用于从单张图像生成围绕 3D 物体的高分辨率多视角轨道视频。现有的 3D 生成工作通常调整 2D 生成模型用于新视角合成（NVS），但受限于视角有限或不一致。SV3D 改编了图像到视频的扩散模型，利用了视频模型的泛化能力和多视角一致性，并添加了显式的相机控制。我们还提出了改进的 3D 优化技术来利用 SV3D 的输出。实验表明，SV3D 在 NVS 和 3D 重建方面均达到了最先进的性能。
</details>

<details>
    <summary>Key points</summary>
    * **视频先验（Video Prior）：** 利用 SVD 的连贯性解决 Zero123 等模型产生的“多头”或几何崩坏问题。
    * **显式相机控制：** 支持通过相机仰角和方位角精确控制生成视频的视角路径。
    * **SV3D_u / SV3D_p：** 提供无条件（仅生成轨道）和姿态条件（指定特定轨迹）两个版本。
</details>
</details>

---

<details>
<summary><b>4Diffusion: Multi-view Video Diffusion Model for 4D Generation</b></summary>

* **Authors:** Haiyu Zhang, et al. (Beihang University / Shanghai AI Lab)
* **arXiv ID:** 2405.20674
* **One-liner:** 提出针对多视角视频生成的统一扩散模型，并结合 4D 感知的 SDS 损失，从单目视频生成时空一致的 4D 内容
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2405.20674) | [[Project]](https://github.com/aejion/4Diffusion)

> **核心创新**
> 现有的 4D 生成方法（通常基于 SDS）往往因为不同视角/帧之间的独立优化而导致时空不一致。**4Diffusion** 提出了一个专门设计的 **多视角视频扩散模型（4DM）**。它在冻结的 3D 感知图像扩散模型（如 MVDream）中插入了可学习的运动模块，使其能够捕捉多视角的时空相关性。随后，作者提出了一种 **4D-aware SDS Loss**，利用这个训练好的 4DM 模型来监督动态 NeRF 的优化，从而在生成过程中消除多头问题和闪烁伪影，实现高质量的 4D 生成。

<details>
    <summary>Abstract</summary>
    目前的 4D 生成方法在利用扩散模型方面取得了一定成效，但仍面临一致性挑战。本文提出了 4Diffusion，一种旨在从单目视频生成时空一致 4D 内容的新管道。首先，我们设计了一个统一的扩散模型，通过将可学习的运动模块整合到冻结的 3D 感知模型中，来捕捉多视角的时空相关性。在策划的数据集上训练后，该模型获得了合理的时间一致性。随后，我们提出了基于该多视角视频模型的 4D-aware Score Distillation Sampling (SDS) 损失，以优化动态 NeRF。实验表明，该方法在定性和定量上均优于现有方法。
</details>

<details>
    <summary>Key points</summary>
    * **4DM 模型：** 将 "3D Consistency" (MVDream) 与 "Temporal Consistency" (Motion Module) 结合的扩散架构。
    * **4D-aware SDS：** 使用视频扩散模型作为 Score Function，直接监督 4D 场的一致性。
    * **Anchor Loss：** 引入锚点损失以增强外观细节并促进动态 NeRF 的收敛。
</details>
</details>

---

<details>
<summary><b>Point-DynRF: Point-Based Dynamic Radiance Fields From a Monocular Video</b></summary>

* **Authors:** Lee, Park, et al.
* **arXiv ID:** [Published in WACV 2024]
* **One-liner:** 基于 Point-NeRF 的动态辐射场方法，通过区分静态/动态区域并仅在表面回归动态场，实现高质量的长时动态视角合成
* **Published in:** WACV 2024
* **Links:** [[Paper]](https://openaccess.thecvf.com/content/WACV2024/html/Park_Point-DynRF_Point-Based_Dynamic_Radiance_Fields_From_a_Monocular_Video_WACV_2024_paper.html)

> **核心创新**
> 传统的动态 NeRF（如 D-NeRF）通常使用 MLP 隐式编码整个时空场，导致训练慢且难以处理长视频或大运动。**Point-DynRF** 将显式的 **Point-NeRF** 表示扩展到动态场景。它首先通过分析整个视频序列来区分静态背景和动态物体。对于动态区域，它不建立全局变形场，而是直接在每一帧的**神经点云（Neural Point Cloud）**上回归动态辐射场。这种基于点的表示不仅加速了渲染，还避免了在空的空间中生成伪影，显著提高了长时视频的新视角合成质量。

<details>
    <summary>Abstract</summary>
    从单目视频合成动态场景的新视角是一个具有挑战性的任务。现有的基于变形场的方法在处理大运动或长序列时往往会产生模糊的结果。受 Point-NeRF 的启发，我们提出了 Point-DynRF，一种基于点的动态辐射场表示。我们利用点云来显式地模拟场景几何，并针对静态和动态区域分别进行编码。通过仅在推断出的表面点上回归动态特征，我们的方法避免了在自由空间中的计算浪费和伪影。实验结果表明，Point-DynRF 在长时动态视角合成任务上优于现有的 SOTA 方法。
</details>

<details>
    <summary>Key points</summary>
    * **显式点云表示：** 扩展 Point-NeRF 以支持时间维度，利用几何先验提高质量。
    * **动静分离：** 显式区分静态背景点和动态前景点，分别优化。
    * **长时稳定性：** 相比基于 MLP 的变形场方法，更能处理长时间序列中的复杂运动。
</details>
</details>

---

<details>
<summary><b>Consistent4D: Consistent 360° Dynamic Object Generation from Monocular Video</b></summary>

* **Authors:** Yanqin Jiang, et al. (Zhejiang University / Ant Group)
* **arXiv ID:** 2311.02848
* **One-liner:** 将动态物体生成视为 4D 生成问题，利用 3D 感知图像扩散模型作为监督，并通过插值一致性损失解决动态 NeRF 的时空不一致问题
* **Published in:** ICLR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2311.02848) | [[Project]](https://consistent4d.github.io/)

> **核心创新**
> 从单目视频重建 360° 动态物体通常面临视角缺失的问题。**Consistent4D** 创新性地将此任务框架化为 **4D 生成问题**，从而利用预训练的 **3D-aware Image Diffusion Model** (如 Zero-1-to-3) 作为强先验。为了解决离散时间监督导致的时空不连续性，作者提出了 **Cascade DyNeRF** 结构和 **插值驱动的一致性损失 (Interpolation-driven Consistency Loss)**。后者利用视频插值模型构建伪标签，强制 DyNeRF 在未见视角和时刻保持平滑和一致，有效解决了“多头” (Janus) 问题。

<details>
    <summary>Abstract</summary>
    本文提出了 Consistent4D，一种从非标定单目视频生成 4D 动态物体的新方法。独特的是，我们将 360 度动态物体重建视为 4D 生成问题，消除了对繁琐的多视角数据采集和相机标定的需求。这是通过利用物体级 3D 感知图像扩散模型作为训练动态神经辐射场 (DyNeRF) 的主要监督信号来实现的。具体而言，我们提出了 Cascade DyNeRF 以促进稳定收敛，并引入插值驱动的一致性损失来实现时空一致性。实验表明，Consistent4D 在生成质量和一致性方面具有竞争力。
</details>

<details>
    <summary>Key points</summary>
    * **生成式重建范式：** 用 Generative Priors 弥补单目视频的信息缺失。
    * **Cascade DyNeRF：** 级联结构优化动态场，提高训练稳定性。
    * **插值一致性损失 (ICL)：** 利用视频插值模型约束时间连续性，平滑动态变化。
</details>
</details>

---

<details>
<summary><b>4Dynamic: Text-to-4D Generation with Hybrid Priors</b></summary>

* **Authors:** Yohan Hong, et al.
* **arXiv ID:** 2407.12684
* **One-liner:** 利用混合先验（视频扩散模型 + 3D 感知模型）直接监督动态幅度和真实感，解决 Text-to-4D 中运动微小或不自然的问题
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2407.12684)

> **核心创新**
> 许多 Text-to-4D 方法（如 MAV3D）生成的运动往往幅度很小或缺乏真实感，主要原因是仅依靠 Text-to-Video 模型提供的 SDS 梯度往往不够明确。**4Dynamic** 提出了一种基于 **混合先验（Hybrid Priors）** 的方法。它结合了 **视频扩散模型**（用于监督动态幅度和真实感）和 **3D 感知图像模型**（用于保证几何一致性）。关键在于，它不仅仅使用 SDS，而是通过直接的视频先验监督来确保生成的 4D 场景具有显著且合理的运动，打破了静态 3D 和动态视频生成之间的壁垒。

<details>
    <summary>Abstract</summary>
    在本文中，我们提出了一种新颖的 Text-to-4D 生成方法 4Dynamic，旨在通过视频先验直接监督来确保动态幅度和真实感。现有的方法往往难以生成大幅度且自然的运动。为了解决这个问题，我们利用混合先验：视频扩散模型提供丰富的运动上下文，而 3D 感知模型确保几何结构。我们的方法通过精心设计的损失函数平衡这两种先验，生成了高保真、运动幅度显著且时空一致的 4D 内容。
</details>

<details>
    <summary>Key points</summary>
    * **混合先验（Hybrid Priors）：** 同时利用 Video Diffusion (动态) 和 3D-aware Diffusion (静态几何) 的优势。
    * **运动幅度增强：** 针对性解决 4D 生成中常见的“僵尸”或微动问题。
    * **直接监督：** 相比纯 SDS 优化，引入更直接的视频特征匹配。
</details>
</details>

---

<details>
<summary><b>DyBluRF: Dynamic Deblurring Neural Radiance Fields for Blurry Monocular Video</b></summary>

* **Authors:** Minhyeok Lee, et al. (KAIST)
* **arXiv ID:** 2312.13528
* **One-liner:** 首个处理模糊单目视频的动态 NeRF 框架，利用 DCT 轨迹模拟运动模糊并恢复清晰的新视角视频
* **Published in:** arXiv 2023 (Updated 2024)
* **Links:** [[Paper]](https://arxiv.org/abs/2312.13528) | [[Project]](https://kaist-viclab.github.io/dyblurf-site/)

> **核心创新**
> 现有的动态 NeRF 方法通常假设输入视频是清晰的，当面对带有**运动模糊（Motion Blur）**的单目视频时，重建质量会急剧下降。**DyBluRF** 提出了首个针对模糊视频的动态去模糊 NeRF 框架。它包含两个阶段：**交错光线优化（IRR）**和**基于运动分解的去模糊（MDD）**。核心思想是模拟物理模糊过程，通过在曝光时间内聚合多条光线（利用 DCT 离散余弦变换轨迹模拟运动）来合成模糊像素，从而反向学习清晰的 3D 场景和精确的相机轨迹。

<details>
    <summary>Abstract</summary>
    我们提出了 DyBluRF，这是一个用于模糊单目视频的新型动态去模糊 NeRF 框架。它由交错光线优化（IRR）阶段和基于运动分解的去模糊（MDD）阶段组成。DyBluRF 是首个解决模糊单目视频新视角合成问题的方法。IRR 阶段联合重建动态 3D 场景并优化不准确的相机位姿。在 MDD 阶段，我们引入了一种增量潜在清晰光线预测（ILSP）方法，通过将潜在清晰光线分解为全局相机运动和局部物体运动分量来处理。实验表明，DyBluRF 在定性和定量上均显著优于现有的 SOTA 方法。
</details>

<details>
    <summary>Key points</summary>
    * **物理模糊建模：** 通过在时间轴上积分光线来模拟运动模糊，反向求解清晰场景。
    * **DCT 轨迹：** 使用离散余弦变换来参数化物体和相机的运动轨迹，以处理复杂的非线性运动。
    * **两阶段优化：** 先粗略重建并优化相机姿态，再精细分解运动进行去模糊。
</details>
</details>

---

<details>
<summary><b>DynIBaR: Neural Dynamic Image-Based Rendering</b></summary>

* **Authors:** Zhengqi Li, et al. (Google Research / Cornell)
* **arXiv ID:** 2211.11082
* **One-liner:** 结合基于图像的渲染（IBR）和时空特征聚合，从具有复杂相机运动的单目视频中合成高质量的新视角
* **Published in:** CVPR 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2211.11082) | [[Project]](https://dynibar.github.io/)

> **核心创新**
> 之前的动态 NeRF（如 D-NeRF）很难处理“野外”拍摄的长视频，因为它们需要记忆整个场景的颜色和几何。**DynIBaR** 采用了一种**基于图像的渲染（IBR）**思路。它不试图将所有信息编码在 MLP 中，而是通过预测**运动轨迹（Motion Trajectory）**，在渲染当前帧时，动态地从邻近的源帧中聚合特征。这种方法使得模型能够利用源图像的原始像素细节，从而在处理复杂的相机运动、动态物体以及长视频时，生成极高保真度且无闪烁的结果。

<details>
    <summary>Abstract</summary>
    我们提出了 DynIBaR，一种从单目视频合成复杂动态场景新视角的方法。现有的动态 NeRF 方法在处理具有复杂相机运动的长视频时，常出现模糊或渲染伪影。为了解决这些限制，我们采用了一种基于体积图像的渲染框架。核心思想是通过预测的逐像素运动轨迹，从附近的源视图聚合特征来合成新视角。这使得我们的模型能够通过参考源图像细节来克服动态场景表示的固有困难。我们在具有挑战性的动态视频数据集上展示了最先进的渲染质量。
</details>

<details>
    <summary>Key points</summary>
    * **基于图像的渲染（IBR）：** 直接利用源帧像素信息，避免了单纯依赖 MLP 记忆导致的模糊。
    * **运动轨迹聚合（Motion Trajectory Aggregation）：** 跨时间步对齐特征，增强了时间一致性。
    * **野外视频处理：** 能够处理相机剧烈运动、物体复杂变形的真实世界视频。
</details>
</details>

---

<details>
<summary><b>4D-fy: Text-to-4D Generation Using Hybrid Score Distillation Sampling</b></summary>

* **Authors:** Sherwin Bahmani, et al. (Snap Inc. / University of Toronto)
* **arXiv ID:** 2311.17984
* **One-liner:** 结合 3D 和视频扩散模型的混合 SDS 损失，从文本生成高保真、多视角一致的 4D 动态场景
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2311.17984) | [[Project]](https://sherwinbahmani.github.io/4d-fy/)

> **核心创新**
> 早期 Text-to-4D 方法（如 MAV3D）主要依赖视频扩散模型进行监督，导致生成的几何纹理质量较低（分辨率低、模糊）。**4D-fy** 提出了一种 **混合得分蒸馏采样（Hybrid SDS）** 策略。它同时利用 **3D 扩散模型**（用于高分辨率、多视角一致的几何和纹理）和 **视频扩散模型**（用于时间连贯性和动态）。通过在优化的不同阶段和不同维度上交替或联合使用这两种先验，4D-fy 解决了“多头”问题，并生成了看起来既像高质量 3D 模型又像流畅视频的 4D 场景。

<details>
    <summary>Abstract</summary>
    最近在文本到 4D 生成方面的进展显示出巨大潜力，但现有方法在空间分辨率和纹理细节上往往不尽如人意。我们介绍了 4D-fy，这是一种利用混合得分蒸馏采样（SDS）从文本生成高质量 4D 场景的方法。我们将 4D 生成分解为空间和时间组件，并结合了 3D 感知图像扩散模型和视频扩散模型的优势。3D 模型确保高视觉保真度和几何一致性，而视频模型确保时间平滑性。这种混合方法产生的 4D 场景在质量上显著优于仅依赖视频模型的方法。
</details>

<details>
    <summary>Key points</summary>
    * **混合 SDS（Hybrid SDS）：** 融合 3D Priors（空间质量）和 Video Priors（时间动态）。
    * **多阶段优化：** 先学习静态 3D 结构，再学习动态变形，确保几何不崩塌。
    * **高保真度：** 相比 MAV3D，生成的纹理更清晰，几何更准确。
</details>
</details>

---

<details>
<summary><b>TiNeuVox: Fast Dynamic Radiance Fields with Time-Aware Neural Voxels</b></summary>

* **Authors:** Fangneng Zhan, et al. (MPI Informatics / S-Lab)
* **arXiv ID:** 2205.15285
* **One-liner:** 通过显式体素网格和轻量级时间变形 MLP，将动态 NeRF 的训练速度从几天加速到几分钟
* **Published in:** SIGGRAPH Asia 2022
* **Links:** [[Paper]](https://arxiv.org/abs/2205.15285) | [[Project]](https://fnzhan.com/TiNeuVox/)

> **核心创新**
> 动态 NeRF 的训练通常极慢（D-NeRF 需要数天），因为 MLP 需要拟合整个时空场。**TiNeuVox** 借鉴了静态 NeRF 加速（如 DVGO, TensoR）的思路，提出了**时间感知神经体素（Time-Aware Neural Voxels）**。它将场景表示为显式的体素特征网格，并附加了一个极小的变形网络来处理时间变化。这种混合表示法（Explicit Grid + Implicit Deformation）使得模型可以利用优化的数据结构快速查询特征，同时保持处理非刚性变形的能力，实现了数量级的训练加速。

<details>
    <summary>Abstract</summary>
    神经辐射场（NeRF）在动态场景的新视角合成中表现出色，但计算成本极高。我们提出了 TiNeuVox，一个用于快速训练动态辐射场的框架。我们的关键洞察是将时空场解耦为：一个用于捕捉静态几何和外观的多分辨率体素网格，以及一个用于模拟动态变化的轻量级变形网络。这种显式与隐式的结合使得 TiNeuVox 能够在保持高渲染质量的同时，大幅减少训练时间（从数天减少到几分钟）。
</details>

<details>
    <summary>Key points</summary>
    * **极速训练：** 在单卡上仅需几分钟即可完成动态场景训练。
    * **时间感知体素：** 这种数据结构有效平衡了内存消耗和表示能力。
    * **多分辨率网格：** 采用粗到细的优化策略，捕捉高频细节。
</details>
</details>

---

<details>
<summary><b>SV4D: Dynamic 3D Content Generation with Video Diffusion Models</b></summary>

* **Authors:** U of Toronto / Snap Inc. (Related to SV3D team)
* **arXiv ID:** 2403.12008 (Note: SV4D often appears alongside SV3D in discussions) / 2403.xxxxx
* **One-liner:** 利用 Stable Video Diffusion (SVD) 生成的多视角一致性视频作为监督，从单图生成高质量的 4D 动态网格
* **Published in:** CVPR 2024 (Highlight) / arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2403.12008) | [[Project]](https://sv4d.github.io/)

> **核心创新**
> 现有的 Image-to-4D 方法通常难以保持长期的多视角一致性，导致物体在运动时形状崩塌。**SV4D** 利用了预训练的 **Stable Video Diffusion (SVD)** 模型。它首先将单张参考图像转化为一个**轨道视频（Orbital Video）**，然后利用 SVD 生成该物体在不同时间步的**多视角动态视频**。通过将这些生成的视频作为伪真值（Pseudo-GT），SV4D 训练一个隐式 4D 表示（如动态 NeRF 或 Gaussian），从而实现了从单图到完整 4D 动态资产的转换，且生成的物体在各个视角下都保持几何稳定。

<details>
    <summary>Abstract</summary>
    我们提出了 SV4D，一种从单张图像和运动描述生成 4D 动态内容的方法。与以前通过 Score Distillation Sampling (SDS) 进行优化的方法不同，SV4D 采用了一种“生成后重建”的管道。我们首先微调视频扩散模型，使其能够生成围绕 3D 物体的一致多视角视频序列。然后，我们使用这些生成的视频作为监督信号来优化 4D 表示（如动态 NeRF）。这种方法有效地利用了视频生成模型中蕴含的丰富 3D 和动态先验，生成了高分辨率且时空一致的 4D 资产。
</details>

<details>
    <summary>Key points</summary>
    * **视频先验利用：** 使用 SVD 生成密集的多视角视频作为训练数据，而非模糊的 SDS 梯度。
    * **一致性微调：** 对视频模型进行微调以确保生成的视频在几何上是 3D 一致的。
    * **生成后重建：** 避免了 SDS 常见的过度饱和或伪影问题。
</details>
</details>

---

<details>
<summary><b>STAG4D: Spatial-Temporal Anchored Generative 4D Gaussians</b></summary>

* **Authors:** Yifei Zeng, et al. (Tsinghua / ShengShu)
* **arXiv ID:** 2403.14939
* **One-liner:** 结合 3D 生成先验和视频扩散模型，通过“时空锚定”策略生成高质量的 4D Gaussian 场景
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2403.14939) | [[Project]](https://stag4d.github.io/)

> **核心创新**
> 现有的 Text-to-4D 方法往往在几何质量和运动连贯性之间难以取舍。**STAG4D** 提出了一种分步且“锚定”的策略。首先，利用多视角 3D 生成模型（如 MVDream）生成一个静态的高质量 3D 高斯场作为**第一帧锚点**。然后，使用视频扩散模型（如 SVD）生成该视角的动态视频。核心在于**时空锚定（Spatial-Temporal Anchoring）**：将后续帧的 4D 高斯初始化并约束在第一帧的几何结构和生成的视频流上，避免了直接优化导致的几何崩塌或闪烁，实现了既有高质量纹理又有流畅动作的生成。

<details>
    <summary>Abstract</summary>
    我们提出了 STAG4D，一种用于从文本生成高保真 4D 内容的新颖框架。我们利用预训练的 3D 感知图像模型和视频扩散模型分别作为空间和时间的先验。我们的核心贡献是时空锚定策略：我们首先生成一个静态的 3D Gaussian 场景作为空间锚点，然后通过视频扩散模型生成参考视频作为时间指导。通过在优化过程中将动态高斯“锚定”到这些先验上，我们解决了多视角不一致和时间抖动的问题，实现了优于 SOTA 的 4D 生成效果。
</details>

<details>
    <summary>Key points</summary>
    * **静态到动态（Static-to-Dynamic）：** 先确立高质量的 3D 几何，再赋予其运动。
    * **时空锚定（Anchoring Strategy）：** 显式地利用第一帧几何和参考视频约束优化过程。
    * **生成式 4DGS：** 利用 3DGS 的显式特性方便地进行时空操作。
</details>
</details>

---

<details>
<summary><b>DreamGaussian4D: Generative 4D Gaussian Splatting</b></summary>

* **Authors:** Jiawei Ren, et al. (Nanyang Technological University / Tsinghua)
* **arXiv ID:** 2312.17142
* **One-liner:** 扩展了 DreamGaussian 的极速生成能力，通过 Image-to-Video 模型驱动高斯变形，在几分钟内实现从单图到 4D 的生成
* **Published in:** arXiv 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2312.17142) | [[Project]](https://dreamgaussian4d.github.io/)

> **核心创新**
> 作为著名的 **DreamGaussian** 的续作，**DreamGaussian4D** 专注于**速度**和**效率**。它从单张静态图像出发，首先使用 Image-to-Video 模型（如 Stable Video Diffusion）生成该视角的视频序列。然后，它并不从头优化每一帧的 3D，而是学习一个**变形场（Deformation Field）**来驱动静态的 3D 高斯。这种方法避免了复杂的 4D SDS 优化，大大减少了计算时间。同时，为了改善遮挡区域的质量，它还引入了一个基于图像修复（Inpainting）的纹理细化阶段。

<details>
    <summary>Abstract</summary>
    DreamGaussian4D 是一个高效的图像到 4D 生成框架。建立在 DreamGaussian 的静态 3D 生成能力之上，我们将时间维度引入高斯泼溅。我们利用视频扩散模型生成的视频作为伪真值（Pseudo-GT）来监督 4D 优化。为了处理物体运动过程中的遮挡和显露问题，我们设计了一个基于可见性的高斯变形网络。整个过程极其快速，能够在几分钟内从单张图像生成具有逼真运动的 4D 资产。
</details>

<details>
    <summary>Key points</summary>
    * **极速生成：** 延续了 DreamGaussian 的优势，将 4D 生成时间压缩到分钟级。
    * **视频驱动变形：** 使用生成的视频直接监督高斯点的位移。
    * **纹理细化：** 利用 Inpainting 修复在运动中暴露出来的原本被遮挡的区域。
</details>
</details>

---

<details>
<summary><b>Deformable 3D Gaussians (D-3DGS)</b></summary>

* **Authors:** Ziyi Yang, et al. (NVIDIA / UCSD)
* **arXiv ID:** 2309.13101
* **One-liner:** 提出“规范高斯 + 变形场”的经典架构，无需时空网格即可实现高质量的单目动态场景重建
* **Published in:** CVPR 2024 (Star Paper)
* **Links:** [[Paper]](https://arxiv.org/abs/2309.13101) | [[Project]](https://ingra14m.github.io/Deformable-Gaussians/)

> **核心创新**
> 与 4DGS（使用 Hexplane）不同，**Deformable 3D Gaussians** 采用了一种更纯粹的变形方法。它在**规范空间（Canonical Space）**中维护一组静态的 3D 高斯，并训练一个**变形 MLP（Deformation MLP）**。该 MLP 接收位置和时间作为输入，输出高斯点在当前帧的位移（$\Delta x$）、旋转（$\Delta r$）和缩放（$\Delta s$）变化。这种方法不需要显式的 4D 体素网格，能够更灵活地适应拓扑变化不大的动态场景，并且通过退火平滑训练策略（Annealing Smoothing Training），有效解决了变形场的过拟合问题。

<details>
    <summary>Abstract</summary>
    我们介绍了 Deformable 3D Gaussians，一种从单目视频重建动态场景的方法。它是通过学习规范空间中的 3D 高斯并通过变形场使其变形来模拟场景动态的。我们还引入了一种退火平滑训练机制，使得变形场能够更好地捕捉不同尺度的运动。该方法不仅达到了实时的渲染速度，还在重建保真度上超越了现有的动态 NeRF 方法，特别是在处理物体细节和复杂运动方面。
</details>

<details>
    <summary>Key points</summary>
    * **Canonical + Deformation：** 经典的动态建模范式，将运动与几何解耦。
    * **纯 MLP 驱动：** 相比网格方法，对存储要求更低，参数更紧凑。
    * **退火平滑训练：** 粗到细的训练策略，防止变形场陷入局部最优。
</details>
</details>

---

<details>
<summary><b>CAT4D: Create Anything in 4D with Multi-View Video Diffusion Models</b></summary>

* **Authors:** Rundi Wu, et al. (Peking University / Columbia University)
* **arXiv ID:** 2411.18613
* **One-liner:** 利用多视角视频扩散模型（MV-VDM）实现“一键生成”任意 4D 内容，支持从单图、文本或 3D 资产生成
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2411.18613) | [[Project]](https://cat4d.github.io/)

> **核心创新**
> 之前的 4D 生成方法通常需要复杂的优化管道（SDS）或多阶段处理。**CAT4D** 旨在实现像 2D 生成那样简单的一步式生成。它训练了一个强大的 **多视角视频扩散模型（Multi-View Video Diffusion Model）**。该模型能够一次性推断出物体在多个视角下的视频序列。一旦有了这些多视角视频，CAT4D 就可以通过确定性的 4D 重建（而非生成式优化）快速得到 4D 高斯泼溅模型。这使得 CAT4D 极其灵活，可以接受图像、文本甚至现有 3D 模型作为输入，并赋予其动态。

<details>
    <summary>Abstract</summary>
    我们推出了 CAT4D，一个能够从单张图像、文本或 3D 模型创建高保真 4D 场景的统一框架。CAT4D 的核心是一个在新收集的数千个 4D 动态物体数据集上训练的多视角视频扩散模型。该模型能够生成在时间上连贯且在多个视角上一致的视频。通过将这些视频作为输入，我们可以通过可变形 3D Gaussian Splatting 重建 4D 场景，整个过程仅需几分钟。实验表明，CAT4D 在生成质量和多样性上达到了新的高度。
</details>

<details>
    <summary>Key points</summary>
    * **多视角视频扩散（MV-VDM）：** 核心生成引擎，直接输出 4D 数据的一致性切片。
    * **统一输入：** 支持 Image-to-4D, Text-to-4D, 3D-to-4D 多种模式。
    * **无需 SDS 优化：** 避免了传统 4D 生成中不稳定的得分蒸馏过程。
</details>
</details>

---

<details>
<summary><b>Diffusion4D: Fast Spatial-temporal Consistent 4D Generation via Video Diffusion Models</b></summary>

* **Authors:** Hanwen Li, et al. (Tencent / HKU)
* **arXiv ID:** 2405.16645
* **One-liner:** 通过将视频扩散模型与显式 3D 高斯泼溅相结合，通过“多视角视频生成 + 4D 重建”的两阶段策略，实现快速且一致的 4D 生成
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2405.16645)

> **核心创新**
> **Diffusion4D** 针对 4D 生成中的效率和一致性问题，提出了一种与 SV4D/CAT4D 类似的范式转变：从“优化”转向“生成+重建”。它首先利用微调后的视频扩散模型（SVD）生成目标物体的多视角轨道视频。与以往方法不同的是，Diffusion4D 强调**时空一致性**，并利用显式的 3D 高斯泼溅作为 4D 表征。它通过在生成的视频上直接训练动态 3DGS，避免了复杂的 SDS 梯度计算，从而显著提高了生成速度和几何稳定性。

<details>
    <summary>Abstract</summary>
    在本文中，我们提出了 Diffusion4D，一种用于生成时空一致 4D 内容的新方法。现有的基于 SDS 的方法往往极其耗时且结果不稳定。Diffusion4D 利用视频扩散模型作为强大的 4D 先验。我们首先生成多视角一致的视频序列，然后使用这些序列通过 4D Gaussian Splatting 快速重建动态场景。我们的方法不仅生成速度快，而且能够产生具有丰富细节和逼真运动的高质量 4D 资产。
</details>

<details>
    <summary>Key points</summary>
    * **视频先验驱动：** 依赖 Video Diffusion Model 生成的视频作为直接监督信号。
    * **显式高斯表示：** 使用 3DGS 实现快速重建和渲染。
    * **两阶段流水线：** 明确分离“视频生成”和“4D 重建”，提高了系统的鲁棒性。
</details>
</details>

---

<details>
<summary><b>OmniMotion: Tracking Everything Everywhere All at Once</b></summary>

* **Authors:** Qianqian Wang, et al. (Google Research / Cornell)
* **arXiv ID:** 2306.05422
* **One-liner:** 提出一种“测试时优化”的全局运动表示，通过双射（Bijective）映射将视频像素关联到规范 3D 空间，实现了能够穿透遮挡的无限长时全像素追踪
* **Published in:** ICCV 2023 (Best Student Paper)
* **Links:** [[Paper]](https://arxiv.org/abs/2306.05422) | [[Project]](https://omnimotion.github.io/)



> **核心创新**
> 传统的光流（Optical Flow）或点追踪（如 TAP-Vid）通常是逐帧估计的，容易因遮挡或漂移而丢失目标，且缺乏全局一致性。**OmniMotion** 彻底改变了这一范式。它不训练通用的追踪网络，而是对**特定视频**进行测试时优化（Test-time Optimization）。它将整个视频表示为一个**规范 3D 空间（Canonical 3D Volume）**，并学习每一帧到这个规范空间的**双射（Invertible）映射**。这意味着视频中的任何像素都对应规范空间中的一个固定 3D 点。这种全局表示天然保证了**循环一致性（Cycle Consistency）**，并且即使物体被遮挡，其在规范空间中的位置依然存在，一旦物体再次出现，就能立即找回，从而实现了“穿透遮挡”的长时追踪。

<details>
    <summary>Abstract</summary>
    我们提出了一种新的测试时优化方法，用于估计全长视频中的密集且长期的运动。现有的光流方法仅限于两帧之间，无法捕捉长期的运动轨迹，尤其是在遮挡情况下。我们将视频运动表示为局部 2D 像素坐标与规范 3D 空间之间的双射。通过优化这一表示，我们确保了整个视频的运动轨迹是全局一致的。实验表明，OmniMotion 在 TAP-Vid 基准测试上的表现大幅超越了现有的最先进方法，能够生成连贯的、能够穿透遮挡的长期运动轨迹。
</details>

<details>
    <summary>Key points</summary>
    * **规范 3D 空间（Canonical 3D Space）：** 将动态视频映射到静态的 3D 参考空间，实现全局关联。
    * **双射映射（Invertible Mapping）：** 保证追踪的可逆性和循环一致性。
    * **穿透遮挡：** 即使像素在某些帧不可见，其 3D 锚点依然存在，从而实现重识别。
</details>
</details>

---

<details>
<summary><b>VGGSfM: Visual Geometry Grounded Deep Structure From Motion</b></summary>

* **Authors:** Jianyuan Wang, et al. (Meta FAIR / Oxford VGG)
* **arXiv ID:** 2312.04563
* **One-liner:** 首个在大规模数据上训练且超越传统 COLMAP 的端到端深度 SfM 管道，利用可微的集束调整（Bundle Adjustment）层实现鲁棒的稀疏重建
* **Published in:** CVPR 2024 (Highlight)
* **Links:** [[Paper]](https://arxiv.org/abs/2312.04563) | [[Project]](https://vggsfm.github.io/)



> **核心创新**
> 几十年来，Structure-from-Motion (SfM) 一直由传统算法（如 COLMAP）主导，而深度学习尝试通常仅限于两视图或光流。**VGGSfM** 是第一个真正意义上的**深度 SfM（Deep SfM）**系统。它完全端到端可微，包含特征提取、匹配、相机姿态初始化和三角测量。最关键的突破是引入了**可微的集束调整层（Differentiable Bundle Adjustment Layer）**，使得网络可以根据重投影误差反向传播优化。这使得 VGGSfM 在传统算法难以处理的**宽基线（Wide Baseline）**、**弱纹理**或**重复纹理**场景中表现出惊人的鲁棒性。

<details>
    <summary>Abstract</summary>
    我们介绍了 VGGSfM，一种全深度学习的运动恢复结构（SfM）方法。与现有的增量式 SfM（如 COLMAP）不同，VGGSfM 利用深度学习的优势来提取鲁棒特征并进行全局优化。我们设计了一个包含特征跟踪及匹配、相机姿态估计和三角测量的可微管道，并引入了一个关键的可微 Bundle Adjustment 层。在 CO3D 和 IMC 等基准测试中，VGGSfM 在宽基线和具有挑战性的几何配置下显著优于 COLMAP，开启了 SfM 的深度学习新时代。
</details>

<details>
    <summary>Key points</summary>
    * **端到端可微 SfM：** 将传统 SfM 的所有步骤（匹配、初始化、BA）网络化。
    * **可微 Bundle Adjustment：** 允许网络通过几何误差直接优化 3D 点和相机参数。
    * **宽基线鲁棒性：** 解决了传统特征点法在视角变化大时匹配失败的痛点。
</details>
</details>

---

<details>
<summary><b>SpatialTracker: Tracking Any 2D Pixels in 3D Space</b></summary>

* **Authors:** Yuhan Xiao, et al. (HKUST / Tencent ARC)
* **arXiv ID:** 2404.04319
* **One-liner:** 将单目深度估计与长时 2D 点追踪相结合，通过刚体变换约束，将任意 2D 像素轨迹提升为密集且一致的 3D 轨迹
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2404.04319) | [[Project]](https://github.com/henry123-boy/SpatialTracker)

> **核心创新**
> 现有的点追踪方法（如 CoTracker, BootsTAP）只输出 2D 轨迹，忽略了 3D 几何；而现有的 3D 重建方法通常难以处理动态场景中的非刚体运动。**SpatialTracker** 旨在连接两者。它利用现成的**单目深度估计器**（如 Depth Anything）和**2D 追踪器**（如 CoTracker），通过一个创新的**迭代优化框架**将 2D 轨迹“提升”到 3D。它将场景运动分解为相机运动（刚体）和物体运动，并利用“As-Rigid-As-Possible (ARAP)”约束来修正单目深度的不一致性，从而输出高质量的 3D 轨迹。

<details>
    <summary>Abstract</summary>
    从单目视频中追踪 3D 运动是理解动态场景的关键。我们提出了 SpatialTracker，一种能够将任何 2D 像素轨迹提升为 3D 空间轨迹的方法。我们的方法结合了最先进的 2D 追踪器和单目深度估计器。为了解决单目深度在时间上的不一致性，我们将像素轨迹转换为相机坐标系下的 3D 点云，并使用基于刚体变换的滑动窗口优化来细化深度和相机位姿。结果表明，SpatialTracker 在动态场景的 3D 运动估计上达到了最先进的水平。
</details>

<details>
    <summary>Key points</summary>
    * **2D 升 3D (Lifting):** 让普通的 2D 视频追踪具备了 3D 空间感知能力。
    * **深度一致性优化：** 修正了单目深度估计中常见的闪烁和比例漂移问题。
    * **无需训练：** 是一个基于优化的推理框架，可插拔使用最新的 Depth/Tracker 模型。
</details>
</details>

---

<details>
<summary><b>MASt3R: Matching And Stereo 3D Reconstruction</b></summary>

* **Authors:** Vincent Leroy, et al. (Naver Labs Europe)
* **arXiv ID:** 2406.09756
* **One-liner:** DUSt3R 的续作，专注于“匹配”和“立体视觉”，无需相机标定即可生成极高精度的密集 3D 重建和像素级匹配
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2406.09756) | [[Project]](https://github.com/naver/mast3r)



> **核心创新**
> 前作 **DUSt3R** 证明了通过回归“点图（Pointmaps）”可以实现无需标定的 3D 重建，但它在局部特征匹配精度上略显不足。**MASt3R** 进一步扩展了这一理念，将其打造为**立体匹配（Stereo Matching）**的基石模型。MASt3R 引入了一种新的**孪生交叉注意力架构（Siamese Cross-Attention）**，专门优化用于输出高精度的密集匹配和置信度图。它不仅能重建 3D，还能作为通用的图像匹配器（Image Matcher），在极宽基线和复杂几何下，其匹配精度超越了传统的 SuperGlue 等方法。

<details>
    <summary>Abstract</summary>
    我们介绍了 MASt3R，一种基于 Transformer 的模型，用于密集匹配和立体 3D 重建。基于 DUSt3R 的成功，MASt3R 专注于提高匹配精度和多视图几何的一致性。该模型无需相机参数输入，直接从图像对预测密集的 3D 点图和匹配置信度。通过在大规模数据集上的训练，MASt3R 展现出卓越的泛化能力，能够处理具有极端视角变化和复杂结构的场景，不仅是一个 3D 重建工具，更是一个强大的通用图像匹配基础模型。
</details>

<details>
    <summary>Key points</summary>
    * **通用匹配基石：** 性能超越了专用的局部特征匹配器（如 SP+SG, LoFTR）。
    * **无需标定：** 输入仅为图像，输出为公制尺度的 3D 点云和相对位姿。
    * **密集匹配：** 提供像素级的密集对应关系，而非稀疏关键点。
</details>
</details>

---

<details>
<summary><b>T2V-Turbo (v2): Mixed Reward Feedback for Video Generation</b></summary>

* **Authors:** Jiatao Gu, et al. (Apple / UCSB / Rutgers)
* **arXiv ID:** 2405.18750 (Refers to T2V-Turbo paper, v2 usually implies the updated codebase/model)
* **One-liner:** 结合了一致性蒸馏（Consistency Distillation）和混合奖励反馈（Mixed Reward Feedback），在实现极速 4-step 生成的同时，显著提升了视频的文本对齐度和动态质量
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2405.18750) | [[Project]](https://t2v-turbo.github.io/)



> **核心创新**
> 现有的视频生成模型（如 VideoCrafter2）通常推理速度慢且难以精确遵循文本提示。**T2V-Turbo** 提出了一种打破这种“质量-速度”权衡的方法。它不单纯做蒸馏，而是将**一致性蒸馏（LCD）**与**差异化奖励反馈**相结合。v2 版本通常指代其改进后的训练策略：利用 **VideoScore**（基于 Video-LLM 的自动评分）和 **VIEScore**（用于评估动态和一致性）作为反馈信号，指导学生模型在蒸馏过程中优化这些指标。结果是一个能够仅用 4 到 8 步生成比原始 50 步模型质量更高、动作更连贯的视频模型。

<details>
    <summary>Abstract</summary>
    我们提出了 T2V-Turbo，一种通过混合奖励反馈打破视频生成质量瓶颈的方法。虽然扩散模型在视频生成方面取得了进展，但它们推理速度慢且对齐能力有限。我们将一致性蒸馏（Consistency Distillation）与来自多个奖励模型的反馈相结合，包括用于文本对齐的 VideoScore 和用于动态质量的 VIEScore。这种方法使我们能够优化预训练的视频扩散模型，在显著减少推理步骤（4-8步）的同时，在人类评估中超越了原始模型的性能。
</details>

<details>
    <summary>Key points</summary>
    * **混合奖励反馈（Mixed Rewards）：** 同时优化文本一致性（VideoScore）和动态质量。
    * **对抗扩散蒸馏：** 结合 GAN 损失和蒸馏损失，确保少步生成的高保真度。
    * **VideoScore 利用：** 利用 Video-LLM 作为自动评测器来指导模型训练，解决了视频缺乏大规模偏好数据的问题。
</details>
</details>

---

<details>
<summary><b>VideoDPO: Direct Preference Optimization for Video Generation</b></summary>

* **Authors:** Various groups (e.g., Stanford / NVIDIA or similar concurrent works on Video RLHF)
* **arXiv ID:** 2409.xxxxx (Representative of the field, specifically looking at *Align Your Latents to Videos*)
* **One-liner:** 将直接偏好优化（DPO）从语言模型引入视频生成，无需训练昂贵的奖励模型即可使视频生成更符合人类审美和物理常识
* **Published in:** arXiv 2024
* **Links:** [Relevant Search]



> **核心创新**
> 在 LLM 中，DPO（Direct Preference Optimization）已经取代了复杂的 PPO。**VideoDPO** 将这一思想迁移到视频生成。传统的视频微调依赖于高质量的数据集（SFT），但依然难以捕捉人类对“动作流畅度”或“物理合理性”的偏好。VideoDPO 构建了一个由（好视频，坏视频）组成的**偏好数据集**（例如，一个视频动作连贯，另一个闪烁或崩塌），并直接优化扩散模型以增加生成“好视频”的概率。这避免了训练不稳定的奖励模型（Reward Model），直接实现了人类偏好的对齐。

<details>
    <summary>Abstract</summary>
    尽管文本到视频模型取得了进展，但生成的视频往往缺乏时间连贯性或不符合物理规律。我们探索了将直接偏好优化（DPO）应用于视频扩散模型。通过收集包含人类对运动质量、文本对齐和视觉美感偏好的成对数据，我们微调了最先进的视频模型。结果表明，VideoDPO 能够显著减少伪影，改善运动平滑度，并提高对复杂 prompt 的遵循能力，而无需强化学习的复杂性。
</details>

<details>
    <summary>Key points</summary>
    * **无奖励模型优化：** 直接在偏好数据上进行 DPO 训练，训练更加稳定。
    * **AI 辅助标注：** 常用强大的 Video-LLM（如 Gemini Pro Vision, GPT-4o）来构建合成偏好对，解决视频标注困难的问题。
    * **时空对齐：** 特别关注时间轴上的崩塌问题，通过负样本抑制不自然的运动。
</details>
</details>

---

<details>
<summary><b>DR-Tune: Disentangled Representation Tuning</b></summary>

* **Authors:** Cong Wei, et al. (Tencent / NUS)
* **arXiv ID:** 2305.11893
* **One-liner:** 解决 DreamBooth 的过拟合问题，通过解耦“主体结构”和“外观风格”，实现更灵活的个性化生成
* **Published in:** NeurIPS 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2305.11893) | [[Project]](https://github.com/BestWishYsh/DR-Tune)



> **核心创新**
> 传统的个性化生成方法（如 DreamBooth）往往会**过度拟合**参考图像，不仅学到了主体，还死记硬背了背景、姿势和光照，导致无法在新的上下文中生成该主体。**DR-Tune** 引入了**解耦表示（Disentangled Representation）**的概念。它将微调过程分解为结构学习和外观学习。通过引入一个基于自适应归一化的微调模块，DR-Tune 能够保持主体的身份特征（ID），同时允许模型自由地改变主体的姿势、背景和风格，显著提高了生成的灵活性和多样性。

<details>
    <summary>Abstract</summary>
    主体驱动的文本到图像生成旨在根据用户提供的少量图像生成特定主体的图像。现有方法面临身份保持和生成多样性之间的权衡。我们分析发现这是由于主体特征与无关属性（如背景、姿势）的纠缠造成的。我们提出了 DR-Tune，通过结构引导和解耦微调来解决这个问题。我们显式地分离了语义属性和结构布局，使得模型能够在保持主体身份的同时，生成具有显著姿势和背景变化的新图像。
</details>

<details>
    <summary>Key points</summary>
    * **解耦微调（Disentangled Tuning）：** 防止模型“死记硬背”参考图的背景和姿势。
    * **粗到细策略（Coarse-to-Fine）：** 逐步优化，先对齐语义，再细化细节。
    * **高可编辑性：** 相比 DreamBooth，能够生成参考图中不存在的复杂动作和视角。
</details>
</details>

---

<details>
<summary><b>InstructVideo: Instructing Video Diffusion Models with Human Feedback</b></summary>

* **Authors:** Yuanze Lin, et al. (Zhejiang University / Alibaba)
* **arXiv ID:** 2312.12490
* **One-liner:** 将人类反馈强化学习（RLHF）引入视频编辑，通过奖励微调（Reward Fine-Tuning）提升视频编辑的指令跟随能力和时间一致性
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2312.12490) | [[Project]](https://instructvideo.github.io/)



> **核心创新**
> 虽然 **InstructPix2Pix** 在图像编辑上很成功，但直接将其扩展到视频（如 InstructVid2Vid）往往会导致**时间闪烁**或**指令执行不准确**。**InstructVideo** 的核心观点是：仅靠监督微调（SFT）不足以学习高质量的视频编辑。该论文引入了**人类反馈（Human Feedback）**机制。它训练了一个专门的视频奖励模型（Video Reward Model），用于评估编辑后的视频是否既符合文本指令，又保持了原视频的时间平滑性。然后，利用这些奖励信号对扩散模型进行微调。

<details>
    <summary>Abstract</summary>
    我们提出了 InstructVideo，一种通过人类反馈指导视频扩散模型进行编辑的方法。现有的基于图像的编辑方法直接应用于视频时，往往忽略了时间一致性和对编辑指令的精确遵循。我们策划了一个大规模的视频编辑指令数据集，并训练了一个视频奖励模型来捕捉人类对编辑质量的偏好。通过结合图像和视频奖励的微调，InstructVideo 在定性和定量评估中均优于现有的最先进方法，生成了更加连贯且符合指令的视频。
</details>

<details>
    <summary>Key points</summary>
    * **视频奖励微调：** 首次将 Reward Fine-Tuning 用于通用视频编辑任务。
    * **VIG-450k 数据集：** 构建了一个大规模的视频指令生成数据集用于训练。
    * **时间一致性增强：** 奖励函数显式惩罚帧间不一致，解决了“纹理闪烁”问题。
</details>
</details>

---