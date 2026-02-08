<p align="center">
  <a href="README.md">English</a> | <a href="README_zh.md">中文</a>
</p>

### 文本到世界生成器

从语言描述生成动态、空间一致的虚拟环境的模型。

**关键特征：**
- ✅ 模态一致性：自然语言理解和像素空间生成
- ✅ 空间一致性：具有物体恒存性的 3D 感知场景组合
- ✅ 时间一致性：物理上可信的动力学和运动

#### 代表性工作

<details>
<summary><b>OpenAI Sora</b></summary>

* **Authors:** OpenAI (团队)  
* **Model ID:** Sora (2024)  
* **One-liner:** 支持从文本、图像、视频输入生成新视频的通用视觉数据模型。 
* **Published in:** 2024（开放形式）
* **Links:** [[Model Page]](https://openai.com/sora/) | [[Technical Overview]](https://openai.com/index/video-generation-models-as-world-simulators/)

> **核心创新**  
> Sora 引入了将视觉数据（如视频）视作“补丁（patches）”训练的大规模通用生成模型，支持多种输入模态（例如文本、图像、视频）并输出新视频，时长、分辨率、长短多样。

<details>
    <summary>Abstract</summary>
    Sora 是一种通用视觉数据生成模型——能够生成视频与图像，跨越不同持续时间、纵横比与分辨率。我们借鉴大型语言模型中 token 化方式，将视觉数据转换为补丁表示，并训练一个压缩编码网络以把原始视频降维，再训练对应解码器将生成的 latent 映射回像素空间。
</details>

<details>
    <summary>Key points</summary>
    * 使用补丁（patch）作为视觉数据单位，构建可扩展的生成模型。   
    * 引入视频压缩网络，将原始视频编码为时空 latent 表示。
    * 支持灵活的输入模态（文本、图像、视频）与多样的视频输出格式。  
    * 强调通用性与规模化：目标是构建类似“世界模型”的视觉生成系统。  
</details>
</details>

---

<details>
<summary><b>Open-Sora: Democratizing Efficient Video Production for All</b></summary>

* **Authors:** HPC-AI Tech Team (Colossal-AI)
* **arXiv ID:** 2412.20404 (v1.2/v2 Report)
* **One-liner:** 致力于“复现 Sora”的开源先锋，通过 ST-DiT 架构和高效的训练策略（如动态分辨率加载），将 Sora 级别的训练成本大幅降低
* **Published in:** arXiv 2024 / GitHub
* **Links:** [[Paper]](https://arxiv.org/abs/2412.20404) | [[Project]](https://github.com/hpcaitech/Open-Sora)



> **核心创新**
> OpenAI 不开源 Sora，而 **Open-Sora** 旨在填补这一空白。它不仅仅是复现，更侧重于**训练效率**和**民主化**。核心架构采用 **ST-DiT（Spatiotemporal DiT）**，将空间和时间注意力解耦以降低计算复杂度。Open-Sora 引入了动态分辨率加载（Dynamic Resolution Loading）和一种多阶段训练策略（从图像预训练到视频微调），成功地以极低的成本（早期版本仅需 $10k-$200k 算力成本）训练出了具有长时一致性的视频模型。最新的 Open-Sora 2.0 更是进一步优化了 3D VAE 和流匹配（Flow Matching）策略。

<details>
    <summary>Abstract</summary>
    为了促进视觉智能的发展，我们推出了 Open-Sora，一项致力于高效生产高质量视频的开源计划。我们提出了一种基于 ST-DiT 的架构，并实施了多种系统优化以支持动态分辨率和长序列训练。通过开源模型权重、训练代码和数据处理流程，我们证明了训练顶级视频生成模型并非只有大厂才能完成，极大地降低了视频生成的准入门槛。
</details>

<details>
    <summary>Key points</summary>
    * **ST-DiT 架构：** 串行处理空间和时间注意力，比全 3D 注意力更节省显存。
    * **成本效益：** 证明了通过高质量数据筛选和多阶段训练，可以用有限预算训练高性能模型。
    * **全栈开源：** 提供了从数据清洗、VAE 训练到 DiT 训练的完整 pipeline。
</details>
</details>

---

<details>
<summary><b>Runway Gen-3 Alpha</b></summary>

* **Authors:** Runway AI (团队)  
* **Model ID:** Gen-3 Alpha (2024)  
* **One-liner:** 下一代多模态视频生成基础模型，在忠实度、一致性、运动表现方面较 Gen-2 有大幅提升。
* **Published in:** 2024 (Alpha) 
* **Links:** [[Model Page]](https://runwayml.com/research/introducing-gen-3-alpha)

> **核心创新**  
> Gen-3 Alpha 构建于全新大规模多模态训练基础设施之上，支持文本、图像、视频三种输入，并提供更优秀的运动表现、结构一致性与控制能力。

<details>
    <summary>Abstract</summary>
    该模型是 Runway 在其新一代基础模型上的开端，旨在提升视频生成的视觉忠实度、镜头运动一致性以及创意控制能力。用户可从静态图像或文本出发，生成动态视频、控制镜头运动、人物表现等。
</details>

<details>
    <summary>Key points</summary>
    * 支持文本→视频、图像→视频等多模态输入形式。  
    * 引入“Motion Brush”“高级摄像机控制”等工具，提升创意可控性。 
    * 在生成质量、速度、运动流畅度方面比上代显著改进。  
    * 面向创作者与影视制作流程，强调实用性与制作体验。  
</details>
</details>

---

<details>
<summary><b>Pika 1.0</b></summary>

* **Authors:** Pika Labs (团队)  
* **Model ID:** Pika 1.0 (2023)  
* **One-liner:** “想法到视频”平台中推出的版本 1.0 模型，可生成与编辑多种风格（3D 动画、卡通、电影风格）视频。 
* **Published in:** 2023 (11 月) 
* **Links:** [[Product Page]](https://pika.art/) | [[Launch Blog]](https://pika.art/blog) 

> **核心创新**  
> Pika 1.0 将视频生成编辑工具普及化：通过 Web 与 Discord 接入、支持从文本或图像创建视频及编辑已有视频，覆盖多种视觉风格。 

<details>
    <summary>Abstract</summary>
    Pika Labs 在 2023 年 11 月推出其 1.0 版本，引入了一个新的 AI 模型，能够在多种风格下生成视频（包括 3D 动画、动漫、卡通与电影风格），提供全新的网页使用体验。公司同期宣布融资 5500 万美元。用户可从文本或图像提示出发，部分支持已有视频编辑。
</details>

<details>
    <summary>Key points</summary>
    * 支持文本→视频、图像→视频与视频→视频编辑。
    * 多种视觉风格：3D 动画、动漫、卡通、电影级。  
    * 简化创作流程：Web 界面 + Discord 等平台接入，降低视频生成门槛。  
    * 快速增长用户基础：推出半年内已有数十万用户、每周生成百万级视频。 
</details>
</details>

---

<details>
<summary><b>CogVideoX: Text-to-Video Diffusion Models with An Expert Transformer</b></summary>

* **Authors:** Zhipu AI (THUDM)
* **arXiv ID:** 2408.06072
* **One-liner:** 提出了基于“3D 因果 VAE”和“专家 Transformer”的高效架构，以更小的潜空间维度实现了极其紧凑且语义对齐度极高的视频生成
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2408.06072) | [[Project]](https://github.com/THUDM/CogVideo)



> **核心创新**
> 许多视频模型受限于巨大的显存开销。**CogVideoX** 的核心突破在于其极其高效的 **3D Causal VAE**。它能够将视频在空间和时间上进行高倍率压缩（例如 4x4x4），从而显著减少 DiT 需要处理的 Token 数量。此外，为了解决文本与视频模态对齐的问题，它引入了 **Expert Transformer** 和 **Expert Adaptive LayerNorm**，专门用于融合两种模态。这使得 CogVideoX 即使在参数量较小（如 2B/5B）的情况下，也能生成提示词遵循度极高且运动流畅的视频。

<details>
    <summary>Abstract</summary>
    我们介绍了 CogVideoX，一种大规模文本到视频生成模型。为了有效建模视频数据，我们利用 3D 变分自编码器（VAE）在空间和时间维度上压缩视频。为了改善文本-视频对齐，我们提出了一种带有专家自适应层归一化（Expert Adaptive LayerNorm）的专家 Transformer，以促进模态间的深度融合。通过渐进式训练技术，CogVideoX 能够生成具有显著运动和连贯性的长视频，并在多个基准测试中展现了最先进的性能。
</details>

<details>
    <summary>Key points</summary>
    * **3D Causal VAE：** 关键组件，实现了时空维度的高效压缩，降低了序列长度。
    * **Expert Transformer：** 通过自适应归一化层增强了模型对文本 Prompt 的理解和执行。
    * **3D RoPE：** 使用 3D 旋转位置编码来更好地捕捉视频中的时空关系。
</details>
</details>

---

<details>
<summary><b>Wan 2.2 (Wan-Video): Mixture-of-Experts for Video Generation</b></summary>

* **Authors:** Alibaba Group (Tongyi Wanxiang Team)
* **arXiv ID:** 25xx.xxxxx (Referencing the Wan 2.1/2.2 Technical Report)
* **One-liner:** 首个将“混合专家模型（MoE）”引入视频扩散的 SOTA 开源模型，在保持推理效率的同时极大地扩展了模型容量（27B 参数），在复杂运动生成上超越了 Sora 和 Gen-3
* **Published in:** arXiv 2025
* **Links:** [[Project]](https://github.com/Wan-Video/Wan2.1)



> **核心创新**
> Wan 2.1 已经非常强大，而 **Wan 2.2** 引入了根本性的架构变革：**Mixture-of-Experts (MoE)**。传统的视频 DiT 随着参数增加推理会变慢，Wan 2.2 使用 MoE 架构，总参数量达到 27B，但每次推理仅激活 14B 参数。这使得它在不增加计算成本的前提下大幅提升了模型容量。结合其强大的 **Wan-VAE**（支持 1080P 无限长编码）和海量数据（比前代多 80% 视频数据），Wan 2.2 解决了视频生成中“动作幅度小”和“物理规律崩坏”的难题，能够生成极具电影感的大幅度运镜和复杂交互。

<details>
    <summary>Abstract (Reconstructed)</summary>
    我们推出了 Wan 2.2，这是 Wan 视频生成系列的最新版本。Wan 2.2 引入了混合专家（MoE）架构，将去噪过程分配给专门的专家模型，从而在保持计算效率的同时扩大了模型容量。基于大规模的审美和运动数据集训练，Wan 2.2 在生成复杂运动、电影级光影和长时一致性方面表现出卓越的性能。我们的 5B 和 14B 模型在多个基准测试中优于现有的闭源模型（如 Gen-3, Sora）。
</details>

<details>
    <summary>Key points</summary>
    * **Video MoE 架构：** 视频生成领域的首个大规模 MoE 应用，平衡了巨量参数与推理速度。
    * **Wan-VAE：** 极其强大的 3D 压缩能力，支持任意长宽比和长时间序列。
    * **数据规模：** 训练数据量相比 2.1 版本增加了近一倍，显著提升了泛化能力。
</details>
</details>

---

<details>
<summary><b>HailuoAI (海螺AI / MiniMax Video-01)</b></summary>

* **Authors:** MiniMax Team (Chinese AI Startup)
* **arXiv ID:** N/A (Proprietary Service)
* **One-liner:** 中国大模型独角兽 MiniMax 推出的“Sora 级”视频生成服务，以极高的指令遵循度、由文本直接生成的音效以及超长连贯时长（6s+）著称
* **Published in:** Product Release (Sep 2024)
* **Links:** [[Website]](https://hailuoai.com/video) | [[Tech Blog]](https://www.minimaxi.com/)



> **核心创新**
> 在 Runway 和 Luma AI 占据主导地位时，**HailuoAI (MiniMax)** 作为一匹黑马杀出。与传统的 UNet 模型不同，HailuoAI 背后的 Video-01 模型采用了大规模的 **DiT (Diffusion Transformer)** 架构。其核心优势在于对**复杂指令的理解能力**（例如精确控制光影变化、物体形变）和**人物动作的流畅度**。它极大地缓解了视频生成中常见的“崩坏”和“闪烁”问题，并且是首批支持**原生高帧率**和**文本生成音效**的模型之一，被广泛认为是目前中文语境下最强的闭源视频模型。

<details>
    <summary>Abstract (Product Description)</summary>
    HailuoAI 是由 MiniMax 推出的一款革命性视频生成工具。基于我们自研的 Video-01 模型，它能够在几秒钟内将文本提示转化为高清晰度、高帧率的电影级视频。该模型在语义理解、动作连贯性和画面细节上取得了重大突破，支持从写实电影到二次元动画的多种风格，并具备强大的图生视频（I2V）能力，致力于为创作者提供无需昂贵设备的虚拟制片体验。
</details>

<details>
    <summary>Key points</summary>
    * **超强语义对齐：** 能够精确理解复杂的 Prompt，包括镜头语言和物理交互。
    * **高动态范围：** 生成的视频不仅清晰，而且动作幅度大，极少出现“PPT式”移动。
    * **生态整合：** 整合了 MiniMax 强大的语音生成技术，支持视频配音和音效生成。
</details>
</details>

---

<details>
<summary><b>HunyuanVideo: Open-Source SOTA Video Generation</b></summary>

* **Authors:** Tencent Hunyuan Team
* **arXiv ID:** 2412.03603
* **One-liner:** 当前开源界最强的视频生成模型，采用统一的 DiT 架构和 3D VAE，支持 720p/129帧生成，并在多项评测中击败了 Gen-3 和 Kling
* **Published in:** arXiv 2024 / GitHub
* **Links:** [[Paper]](https://arxiv.org/abs/2412.03603) | [[Project]](https://github.com/Tencent/HunyuanVideo)



> **核心创新**
> **HunyuanVideo** 的发布标志着开源视频生成进入了 DiT 时代。它没有沿用 VideoCrafter 的 UNet 路线，而是构建了一个全新的**双流 DiT (Dual-Stream DiT)**。其核心贡献包括：1) **统一的图像-视频训练**，利用图像数据学习空间细节，利用视频数据学习动态；2) **MLLM 重打标 (Re-captioning)**，使用多模态大模型对训练视频进行极度详细的描述，显著提升了文本控制力；3) **因果 3D VAE (Causal 3D VAE)**，实现了极高压缩率且无损画质的视频编码。由于其全权重的开源，它迅速成为了社区微调（Fine-tuning）的首选基座。

<details>
    <summary>Abstract</summary>
    我们介绍了 HunyuanVideo，一个开源的大规模视频生成模型。为了实现高质量生成，我们设计了一个包含数据处理、模型架构和训练策略的系统框架。我们提出了一个统一的 DiT 架构，能够同时从图像和视频数据中学习。通过结合 MLLM 生成的详细描述和高效的 3D VAE，HunyuanVideo 在主体一致性、动作流畅度和画面质量上均达到了业界领先水平，甚至在某些指标上超越了闭源商业模型。
</details>

<details>
    <summary>Key points</summary>
    * **双流 DiT (Dual-Stream DiT)：** 分别处理内容和文本信息，类似于 Stable Diffusion 3 的设计。
    * **数据工程：** 强调了 MLLM 详细标注对视频生成质量的决定性作用。
    * **开源基石：** 提供了完整的推理代码和权重，支持 LoRA 微调，生态极佳。
</details>
</details>

---

<details>
<summary><b>VideoCrafter2: Overcoming Data Limitations</b></summary>

* **Authors:** Haoxin Chen, et al. (Tencent AI Lab)
* **arXiv ID:** 2401.09047
* **One-liner:** 经典的开源 UNet 视频生成基线，通过解耦运动和外观，证明了即使利用低质量视频数据也能通过微调获得高质量的生成结果
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2401.09047) | [[Project]](https://github.com/AILab-CVC/VideoCrafter)



> **核心创新**
> 在 DiT 爆发之前，**VideoCrafter2** 是最强大的开源 UNet 视频模型之一。其核心痛点在于：高质量的视频数据（如 4K 电影片段）非常稀缺，而网络视频虽然海量但质量低劣。VideoCrafter2 提出了一种训练策略：首先在海量低质量视频上训练以学习**通用的运动概念（Motion Concept）**，然后通过微调将模型迁移到高质量的视觉分布上。它通过分析发现，运动模式和视觉质量是可以**解耦**的。这使得 VideoCrafter2 成为了当时许多研究者（如 AnimateDiff 社区）的重要参考基线。

<details>
    <summary>Abstract</summary>
    训练高质量视频模型受到高画质视频数据稀缺的阻碍。我们提出了 VideoCrafter2 来解决这一限制。我们观察到，低质量视频虽然视觉上不佳，但包含丰富的运动模式。因此，我们提出了一种将运动学习与外观学习解耦的方法。我们首先在低质量但大规模的数据集上训练模型以学习运动，然后通过高质量图像和视频进行微调以提升视觉质量。结果表明，VideoCrafter2 在通用视频生成质量上显著优于 VideoCrafter1 和其他同期模型。
</details>

<details>
    <summary>Key points</summary>
    * **解耦训练策略：** 证明了“烂视频学动作，好图片学画质”的可行性。
    * **UNet 架构巅峰：** 代表了传统 2D/3D UNet 架构在视频生成领域的成熟形态。
    * **广泛兼容性：** 由于架构标准，适配了大量的 ControlNet 和 LoRA 插件。
</details>
</details>

---

<details>
<summary><b>LTX-Video: High-Resolution Video Generation with Latent Flow Matching</b></summary>

* **Authors:** Lightricks R&D (Creators of Facetune/Videoleap)
* **arXiv ID:** 2501.00103
* **One-liner:** 首个致力于**实时性**和**推理速度**的开源 DiT 视频模型，通过潜空间流匹配（Latent Flow Matching）实现了比 Hunyuan 更快的生成速度，适合消费级显卡
* **Published in:** arXiv 2025 / GitHub
* **Links:** [[Paper]](https://arxiv.org/abs/2501.00103) | [[Project]](https://github.com/Lightricks/LTX-Video)



> **核心创新**
> 在大多数 DiT 模型（如 Sora, Hunyuan）追求极致画质而牺牲速度时，Lightricks 推出的 **LTX-Video** 走了另一条路：**效率**。它虽然也是基于 DiT，但采用了**潜空间流匹配（Latent Flow Matching）**技术，并对 Transformer 结构进行了大幅剪枝和优化。LTX-Video 能够在保持 24fps 高流畅度的同时，将推理延迟降低到接近实时的水平。它的显存占用相对较小，使得在消费级 GPU（如 RTX 3090/4090）上运行微调和推理成为可能，是目前“轻量级”视频生成的代表。

<details>
    <summary>Abstract</summary>
    大规模视频生成模型通常计算昂贵且推理缓慢。我们提出了 LTX-Video，一种基于 DiT 的高效视频生成模型。通过结合潜空间流匹配（Latent Flow Matching）和一种新颖的时空压缩方案，我们在不显著牺牲视觉质量的情况下大幅减少了计算开销。LTX-Video 能够以比实时更快的速度生成高分辨率视频，并在人类评估中显示出优异的运动一致性和文本对齐能力。这也是首个真正面向消费者硬件优化的 DiT 视频模型。
</details>

<details>
    <summary>Key points</summary>
    * **流匹配（Flow Matching）：** 替代了传统的扩散过程，采样路径更直，推理步数更少。
    * **消费级友好：** 优化了显存占用和推理速度，降低了 DiT 视频生成的门槛。
    * **高帧率支持：** 专注于生成高帧率（24fps+）视频，避免了插帧带来的伪影。
</details>
</details>

---