<p align="center">
  <a href="README.md">English</a> | <a href="README_zh.md">中文</a>
</p>

### 具身智能系统

为机器人控制和自主智能体设计的模型，必须整合感知、空间推理和时间预测以执行真实世界任务。

**关键特征：**
- 多模态指令遵循
- 3D 空间导航和操作规划
- 动作后果的预测建模

#### 代表性工作

<details>
<summary><b>RT-2: Vision-Language-Action Models</b></summary>

* **Authors:** Anthony Brohan, Noah Brown, Justice Carbajal, Yevgen Chebotar, Xi Chen, Krzysztof Choromanski, Tianli Ding, Danny Driess, Avinava Dubey, Chelsea Finn, Pete Florence, Chuyuan Fu, Montse Gonzalez Arenas, Keerthana Gopalakrishnan, Kehang Han, Karol Hausman, Alexander Herzog, Jasmine Hsu, Brian Ichter, Alex Irpan, Nikhil Joshi, Ryan Julian, Dmitry Kalashnikov, Yuheng Kuang, Isabel Leal, Lisa Lee, Tsang-Wei Edward Lee, Sergey Levine, Yao Lu, Henryk Michalewski, Igor Mordatch, Karl Pertsch, Kanishka Rao, Krista Reymann, Michael Ryoo, Grecia Salazar, Pannag Sanketi, Pierre Sermanet, Jaspiar Singh, Anikait Singh, Radu Soricut, Huong Tran, Vincent Vanhoucke, Quan Vuong, Ayzaan Wahid, Stefan Welker, Paul Wohlhart, Jialin Wu, Fei Xia, Ted Xiao, Peng Xu, Sichun Xu, Tianhe Yu, Brianna Zitkovich
* **arXiv ID:** 2307.15818
* **One-liner:** 将大规模网络 VLM 与机器人动作训练结合，将视觉与语言直接转化为真实机器人动作，实现零样本现实操控。
* **Published in:** CoRL 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2307.15818) | [[PDF]](https://arxiv.org/pdf/2307.15818.pdf) | [[Project Page]](https://robotics-transformer2.github.io/)

> **核心创新**  
> 将大模型从“看图 + 说话”扩展为“看图 + 理解 + 动作执行”，首次将互联网视觉-语言知识迁移到真实机器人动作层面，使机器人具备开放世界推理和零样本动作能力。

<details>
    <summary>Abstract</summary>
    我们研究如何将互联网级视觉-语言模型直接融入端到端机器人控制，以提升泛化能力并激发语义推理。目标是让单一端到端模型既能将观测映射为动作，又能享用网络图文预训练成果。为此，我们在机器人轨迹与互联网级视觉-语言任务（如视觉问答）上联合微调前沿视觉-语言模型。不同于其他方法，我们给出简洁通用方案：把动作表示为文本token，与语言token同等对待并纳入训练集。这类模型称为视觉-语言-动作模型（VLA），我们实例化出RT-2。6千次评估表明，该方法催生高性能策略，使RT-2从互联网训练中获得涌现能力：显著泛化到新物体，理解训练数据未见的指令（如把物体放到特定数字或图标上），并执行基础推理（如取最小/最大或离某物最近的物体）。引入思维链后，RT-2可进行多阶段语义推理，例如判断用哪块石头当临时锤子，或给疲惫的人挑能量饮料。
</details>

<details>
    <summary>Key points</summary>
    * 将 VLM 扩展到机器人动作空间  
    * 互联网数据 + 机器人数据联合训练  
    * 输出离散化机器人动作 token 序列  
    * 强零样本操控能力：可执行未示教任务/对象/指令  
</details>
</details>

---

<details>
<summary><b>GAIA-1: A Generative World Model for Autonomous Driving</b></summary>

* **Authors:** Anthony Hu, Lloyd Russell, Hudson Yeo, Zak Murez, George Fedoseev, Alex Kendall, Jamie Shotton, Gianluca Corrado
* **arXiv ID:** 2311.07541
* **One-liner:** 面向自动驾驶的生成式世界模型，实现多智能体运动预测与闭环模拟训练。
* **Published in:** arXiv 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2309.17080) | [[PDF]](https://arxiv.org/pdf/2309.17080.pdf)

> **核心创新**  
> 不止是轨迹预测，而是学习“世界演化”——可生成多智能体动态、真实交通行为与传感器信号，用于闭环仿真与安全稀有场景合成。

<details>
    <summary>Abstract</summary>
    自动驾驶有望带来交通领域的变革性改善，但构建能在真实世界复杂无序场景中安全导航的系统仍面临挑战。关键难题在于，如何有效预测随车辆动作演进可能出现的多种潜在结果。为此，我们提出GAIA-1（Generative AI for Autonomy），一个生成式世界模型，它利用视频、文本与动作输入生成逼真驾驶场景，并可精细控制自车行为与场景特征。该方法将世界建模转化为无监督序列建模：把输入映射为离散token，再预测序列中的下一token。模型涌现的能力包括学习高层结构与场景动力学、上下文感知、泛化及几何理解。GAIA-1对未来事件的期望表征与逼真采样能力相结合，为自动驾驶领域开辟新可能，加速并提升自动驾驶技术的训练水平。
</details>

<details>
    <summary>Key points</summary>
    * 生成式世界模型：不仅预测轨迹，还模拟整个交通生态  
    * 支持多智能体时空建模（车-人-交通灯-环境）  
    * 用于闭环 AD 仿真、鲁棒性测试和长尾案例生成  
    * 提高数据效率与泛化能力的同时提升安全性  
</details>
</details>

---

<details>
<summary><b>PaLM-E: An Embodied Multimodal Language Model</b></summary>

* **Authors:** Danny Driess, Fei Xia, Mehdi S. M. Sajjadi, Corey Lynch, Aakanksha Chowdhery, Brian Ichter, Ayzaan Wahid, Jonathan Tompson, Quan Vuong, Tianhe Yu, Wenlong Huang, Yevgen Chebotar, Pierre Sermanet, Daniel Duckworth, Sergey Levine, Vincent Vanhoucke, Karol Hausman, Marc Toussaint, Klaus Greff, Andy Zeng, Igor Mordatch, Pete Florence
* **arXiv ID:** 2303.03378
* **One-liner:** 将真实世界传感输入嵌入 PaLM 大模型，实现具身智能中的视觉-语言-机器人统一推理与任务执行。
* **Published in:** ICLR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2303.03378) | [[PDF]](https://arxiv.org/pdf/2303.03378.pdf) | [[Project Page]](https://palm-e.github.io/)

> **核心创新**  
> 把机器人视觉、状态信息作为“token”输入 LLM，使语言模型成为具身智能决策系统，能理解环境、规划动作并执行任务。

<details>
    <summary>Abstract</summary>
    大语言模型在诸多复杂任务中表现卓越，但在现实世界（如机器人问题）中进行通用推理时，面临 grounding 挑战。我们提出具身语言模型，将连续的实境传感器模态直接融入语言模型，从而建立词汇与感知之间的连接。模型输入为多模态句子，交织视觉、连续状态估计与文本编码。我们与预训练大语言模型端到端联合训练这些编码，用于序列机器人操作规划、视觉问答和描述等具身任务。评估显示，单一大规模具身多模态模型 PaLM-E 可处理多种具身推理任务，适配不同观测模态与 embodiment，并表现出正向迁移：模型受益于互联网级语言、视觉及视觉-语言联合训练。最大的 PaLM-E-562B 含 5620 亿参数，除机器人任务外，还是视觉-语言通才，在 OK-VQA 上达最佳水平，并随规模保持通用语言能力。
</details>

<details>
    <summary>Key points</summary>
    * 将机器人传感信息 token 化输入 LLM  
    * 视觉-语言-动作统一模型  
    * 具备长期规划、任务分解与泛化能力  
    * 推动“机器人 = LLM + 具身输入”研究范式  
</details>
</details>

---

<details>
<summary><b>Genie 3: General-Purpose World Model</b></summary>

* **Authors:** Google DeepMind Team
* **arXiv ID:** 2508.xxxxx (August 2025 Release)
* **One-liner:** 实现了 720p/24fps 实时生成的通用世界模型，支持无限时长的连贯探索和复杂的“文本-环境”交互，被视为迈向 AGI 的重要一步
* **Published in:** Google DeepMind Research / arXiv 2025
* **Links:** [[Blog]](https://deepmind.google/models/genie-3) | [[Paper]](https://arxiv.org/abs/2508.xxxxx)



> **核心创新**
> 相比于 2024 年发布的初代 Genie（只能生成低分辨率、低帧率的类似 Platformer 游戏视频），**Genie 3** 是一个巨大的飞跃。它不再局限于 2D 游戏，而是能够生成**照片级写实（Photorealistic）**的 3D 风格环境。核心突破在于其**自回归架构**的优化，支持以 **24fps** 的速度实时生成 **720p** 视频，并且具备**长时记忆（Persistent Memory）**——即当你离开一个房间再回来时，房间的布局和物品状态保持不变。它还支持**Promptable World Events**，允许用户通过自然语言实时改变环境（如“把天气变成暴风雨”）。

<details>
    <summary>Abstract (Reconstructed)</summary>
    我们介绍了 Genie 3，一种通用的世界模型，能够根据简单的文本描述生成动态、可交互的环境。与其前身不同，Genie 3 实现了 720p 分辨率和 24fps 的实时生成，同时保持了长达数分钟的时间一致性。该模型展现了涌现的物体恒常性（Object Permanence），并允许通过自然语言指令实时修改环境状态。Genie 3 为训练具身智能体（Embodied Agents）提供了无需人工数据的无限模拟环境。
</details>

<details>
    <summary>Key points</summary>
    * **实时交互（Real-Time）：** 首个达到 24fps 可玩帧率的高清世界模型。
    * **物体恒常性（Object Permanence）：** 解决了视频生成中物体“凭空消失”或“变形”的难题。
    * **代理训练场：** 被设计为 SIMA 等通用 AI 代理的训练环境，无需手动搭建 3D 资产。
</details>
</details>

---

<details>
<summary><b>Matrix-Game 2.0: Open-Source Interactive World Model</b></summary>

* **Authors:** Skywork AI Team (昆仑万维 / 天工)
* **arXiv ID:** 2508.13009
* **One-liner:** 开源界首个支持实时流式交互（Streaming Interaction）的世界模型，以 25FPS 的速度生成分钟级的高质量视频，打破了闭源模型的垄断
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2508.13009) | [[GitHub]](https://github.com/SkyworkAI/Matrix-Game)



> **核心创新**
> 针对世界模型推理速度慢、闭源等问题，Skywork AI 推出了 **Matrix-Game 2.0**。它提出了一种高效的**流式推理架构（Streaming Inference Architecture）**，能够将用户操作实时转化为视频反馈，延迟极低。与 Genie 3 类似，它也能达到 **25FPS** 的流畅度，但最大的不同在于它是**完全开源**的（Open Weights）。该模型在多样化的游戏场景和物理模拟中表现出色，证明了无需 Google 级别的算力资源，也能训练出高性能的实时交互式世界模型。

<details>
    <summary>Abstract</summary>
    我们介绍了 Matrix-Game 2.0，一个开源的实时流式交互世界模型。针对现有模型在长序列一致性和推理速度上的瓶颈，我们设计了一种新的流式架构。Matrix-Game 2.0 能够在消费级硬件上以 25 FPS 的速度生成高质量、分钟级的视频，并对用户的按键输入做出即时响应。我们公开了模型权重和代码，以促进交互式世界模型社区的研究。
</details>

<details>
    <summary>Key points</summary>
    * **流式交互（Streaming Interaction）：** 极低的输入-输出延迟，适合实时游戏模拟。
    * **开源 SOTA：** 提供了可复现的训练代码和权重，是学术界研究世界模型的首选基座。
    * **高效推理：** 优化了 Attention 机制，使其能够在有限显存下运行长序列生成。
</details>
</details>

---

<details>
<summary><b>HunyuanWorld 1.0: 3D World Generation</b></summary>

* **Authors:** Tencent Hunyuan Team
* **arXiv ID:** 2507.21809
* **One-liner:** 腾讯推出的 3D 世界生成模型，通过“全景代理（Panoramic Proxy）”技术，能够从单图或文本直接生成可自由漫游的 360° 沉浸式 3D 场景
* **Published in:** arXiv 2025 / GitHub
* **Links:** [[Paper]](https://arxiv.org/abs/2507.21809) | [[Project]](https://github.com/Tencent-Hunyuan/HunyuanWorld-1.0)



> **核心创新**
> 与生成视频的“世界模型”不同，**HunyuanWorld 1.0** 专注于生成**真正的 3D 空间**。传统 3D 生成往往局限于单个物体，而 HunyuanWorld 旨在生成整个场景（Scene-scale）。它引入了**全景世界代理（Panoramic World Proxies）**的概念，首先生成高一致性的全景图，然后利用分层 3D 重建技术将其转化为可导出的 Mesh 或高斯泼溅（Gaussian Splats）。这使得用户输入一句话，就能得到一个可以戴上 VR 眼镜走进去的 3D 世界，且生成成本极低（约 0.3 美元/次）。

<details>
    <summary>Abstract</summary>
    我们提出了 HunyuanWorld 1.0，一个新的框架，用于从文本和图像条件生成沉浸式、可探索的交互式 3D 场景。我们的方法利用全景代理生成和语义分层重建，实现了高质量的场景级 360° 3D 世界生成。该模型支持网格（Mesh）导出，与现有的计算机图形管线无缝兼容，为游戏开发和元宇宙内容创作提供了高效的工具。
</details>

<details>
    <summary>Key points</summary>
    * **场景级生成（Scene-Scale）：** 突破了单物体生成的限制，构建完整的环境。
    * **全景代理技术：** 利用 2D 扩散模型的强大会生成能力来指导 3D 结构的构建。
    * **可漫游性：** 生成的结果不是静态图片，而是支持自由视角浏览的 3D 资产。
</details>
</details>

---

<details>
<summary><b>Cosmos: World Foundation Model Platform for Physical AI</b></summary>

* **Authors:** NVIDIA Research (Niket Agarwal, et al.)
* **arXiv ID:** 2501.03575
* **One-liner:** NVIDIA 专为“物理 AI”打造的基础模型平台，包含 Cosmos Predict（预测未来）、Transfer（数据生成）和 Reason（物理推理），是机器人和自动驾驶领域的数字孪生基石
* **Published in:** arXiv 2025 / CES 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2501.03575) | [[Website]](https://www.nvidia.com/en-us/ai/cosmos/)



> **核心创新**
> **Cosmos** 不是一个单一的模型，而是一个**世界基础模型平台（World Foundation Model Platform）**。NVIDIA 认为物理 AI（机器人、自动驾驶车）需要先在数字孪生中训练。Cosmos 提供了高质量的预训练模型：**Cosmos Predict** 用于根据当前状态预测物理世界的未来演变（视频生成）；**Cosmos Reason** 用于理解复杂的物理规律和因果关系。它采用了 tokenizer 和 transformer 的混合架构，特别强调对物理规律（重力、碰撞、摩擦）的遵循，而非仅仅是视觉上的好看。

<details>
    <summary>Abstract</summary>
    物理 AI 需要先在数字世界中进行训练。我们提出了 Cosmos 世界基础模型平台，帮助开发者构建定制化的世界模型。Cosmos 包含了一系列在数百万小时视频上训练的扩散和自回归 Transformer 模型。它可以作为通用的世界模拟器，支持视频预测、合成数据生成和物理推理。我们开源了模型权重和数据处理流程，以解决物理 AI 数据稀缺和模拟失真的问题。
</details>

<details>
    <summary>Key points</summary>
    * **物理一致性：** 相比 Sora，Cosmos 更注重物理规律的准确性，专为机器人训练设计。
    * **模块化设计：** 分为 Predict（预测）、Transfer（迁移）和 Reason（推理）三个子模块。
    * **开放生态：** NVIDIA 开源了权重，使其成为工业界构建 Sim-to-Real 系统的标准。
</details>
</details>

---

<details>
<summary><b>UniAD: Planning-oriented Autonomous Driving</b></summary>

* **Authors:** Yihan Hu, et al. (OpenDriveLab / SenseTime)
* **arXiv ID:** 2212.10156
* **One-liner:** CVPR 2023 最佳论文，首个将感知、预测、规划整合在一个统一 Transformer 架构中的端到端自动驾驶模型，是自动驾驶“世界模型化”的开山之作
* **Published in:** CVPR 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2212.10156) | [[Project]](https://github.com/OpenDriveLab/UniAD)



> **核心创新**
> 在 **UniAD** 之前，自动驾驶通常是模块化的（感知->预测->规划），模块间信息有损耗且无法联合优化。UniAD 提出了一种**以规划为导向（Planning-oriented）**的统一架构。它通过**Query**机制将检测、跟踪、建图、预测和规划串联起来，前一阶段的 Query 成为下一阶段的输入。这实际上构建了一个驾驶场景的**预测性世界模型**，模型不仅仅是在“看”路，而是在预测周围所有车辆的未来轨迹及其对自己规划的影响，从而做出更拟人的驾驶决策。

<details>
    <summary>Abstract</summary>
    现代自动驾驶系统通常由顺序的模块化任务组成。我们推出了 UniAD，一个全面的端到端框架，将全栈驾驶任务整合到一个网络中。UniAD 利用统一的查询（Query）接口在任务间通信，以规划为最终目标。在 nuScenes 基准测试中，UniAD 在所有方面均大幅超越了之前的 SOTA 方法，证明了这种以规划为导向的理念不仅提升了感知能力，更显著提高了规划的安全性和拟人化程度。
</details>

<details>
    <summary>Key points</summary>
    * **统一 Query 接口：** 解决了不同模块间特征不对齐的问题。
    * **端到端优化：** 整个网络以前方车辆预测和最终路径规划为 Loss 进行联合训练。
    * **交互式预测：** 模型隐式地学习了自车与其他车辆的博弈与交互。
</details>
</details>

---

<details>
<summary><b>V-JEPA: Non-Generative World Model</b></summary>

* **Authors:** Meta FAIR (Yann LeCun, et al.)
* **arXiv ID:** 2404.08471
* **One-liner:** Yann LeCun “世界模型”愿景的实体化——不通过生成像素，而是通过预测抽象特征来理解世界，实现了极高的训练效率和强大的表征能力
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2404.08471) | [[Blog]](https://ai.meta.com/blog/v-jepa-yann-lecun-ai-model-video-joint-embedding-predictive-architecture/)



> **核心创新**
> 与 Sora 或 Hunyuan 等“生成式”世界模型不同，**V-JEPA** 代表了 LeCun 的**联合嵌入预测架构（JEPA）**路线。它认为生成每一个像素是浪费且不必要的（世界充满不可预测的随机细节）。V-JEPA 在**特征空间（Latent Space）**中进行预测：它遮蔽掉视频的时空区域，并训练模型预测这些区域的抽象特征。这种方法使得模型能够忽略不重要的视觉细节（如树叶的随机摆动），而专注于理解物体运动和物理交互的高层语义，其训练效率比生成式模型高出数个数量级。

<details>
    <summary>Abstract</summary>
    我们提出了 V-JEPA，一种用于自监督视频表征学习的方法。V-JEPA 基于联合嵌入预测架构，通过在潜在空间中预测视频的缺失部分来进行学习。与生成式方法不同，V-JEPA 不重建像素，而是预测抽象的嵌入表示。我们在大规模视频数据集上训练了 V-JEPA，证明了它在下游图像和视频任务（如动作识别、物体分类）中表现出卓越的性能，且训练效率远高于像素生成模型。
</details>

<details>
    <summary>Key points</summary>
    * **非生成式（Non-Generative）：** 只预测特征，不生成像素，规避了“幻觉”和计算浪费。
    * **语义聚焦：** 强迫模型学习高级语义而非低级纹理。
    * **高效缩放：** 极高的计算效率使其能够扩展到巨大的模型规模。
</details>
</details>

---

<details>
<summary><b>DreamerV3: General RL World Model</b></summary>

* **Authors:** Danijar Hafner, et al. (DeepMind / UofT)
* **arXiv ID:** 2301.04104
* **One-liner:** 强化学习领域的里程碑，首个使用“固定超参数”就能在 Minecraft、Atari 和机器人控制等完全不同的领域通过世界模型训练实现 SOTA 的算法
* **Published in:** ICLR 2024 / arXiv 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2301.04104) | [[Project]](https://danijar.com/project/dreamerv3/)



> **核心创新**
> **DreamerV3** 解决了基于世界模型的强化学习（MBRL）难以调节的痛点。以往的模型在不同任务（如 2D 游戏 vs 3D 机器人）需要调整大量参数。DreamerV3 引入了 **Symlog 变换**来处理不同数量级的回报（Rewards），并使用了鲁棒的归一化技术。这使得它能够在不修改任何一行代码或参数的情况下，从零开始学会**在 Minecraft 中挖钻石**（这是之前只有模仿学习才能做到的），同时在 Atari 游戏和连续控制任务上击败专门优化的算法。

<details>
    <summary>Abstract</summary>
    通用人工智能需要能够跨越不同领域的算法。我们推出了 DreamerV3，一种基于世界模型的强化学习算法，它使用固定的超参数在广泛的领域中优于先前的方法。DreamerV3 学习一个离散的世界模型，并在想象中训练一个演员-评论家（Actor-Critic）策略。我们观察到，通过 Symlog 预测和鲁棒的归一化，DreamerV3 成为首个在不利用人类数据的情况下在 Minecraft 中收集钻石的算法，并掌握了数百个其他任务。
</details>

<details>
    <summary>Key points</summary>
    * **通用性（Generality）：** 一套参数走天下，解决了 RL 对超参敏感的问题。
    * **Symlog 预测：** 巧妙处理了从微小到巨大的数值范围差异。
    * **Minecraft 突破：** 证明了纯粹的探索和世界模型可以解决长视界（Long-horizon）复杂任务。
</details>
</details>

---

<details>
<summary><b>WorldVLA: Unified Action-World Model</b></summary>

* **Authors:** DAMO Academy, Alibaba Group (Jun Cen, et al.)
* **arXiv ID:** 2506.21539
* **One-liner:** 阿里巴巴推出的统一框架，打破了“世界模型”与“动作模型”的界限，证明了动作生成和视频预测可以互相增强，实现了更符合物理规律的机器人控制
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2506.21539)



> **核心创新**
> 现有的具身智能模型通常将 VLA（视觉-语言-动作）和世界模型分开训练。**WorldVLA** 提出了一种**自回归动作世界模型（Autoregressive Action World Model）**。它在一个单一的 Transformer 框架中同时进行两项任务：1) **世界模型**利用动作预测未来图像（学习物理规律）；2) **动作模型**利用图像观测生成动作。研究发现，这种联合训练产生了显著的**互惠效应（Mutual Enhancement）**：理解了物理规律的模型能生成更合理的动作，而学会了操作的模型能预测更准确的视频。

<details>
    <summary>Abstract</summary>
    现有的 VLA 模型缺乏对动作与环境动态之间关系的深入理解。我们提出了 WorldVLA，一个统一动作和图像生成的世界模型。WorldVLA 通过利用动作和图像理解来预测未来帧，从而学习环境的底层物理；同时，它根据观测生成后续动作。实验表明，WorldVLA 在动作生成和视频预测任务上均优于独立的模型，突显了世界模型与 VLA 之间的协同增强作用。
</details>

<details>
    <summary>Key points</summary>
    * **联合架构：** 将 Video Generation 和 Action Prediction 视为统一的序列建模问题。
    * **互惠增强：** 证明了“会预测未来”有助于“当下决策”，“会操作”有助于“预测未来”。
    * **物理一致性：** 相比纯 VLA，其生成的动作更符合环境的物理约束。
</details>
</details>

---

<details>
<summary><b>LingBot-World: Open-Source Interactive Simulator</b></summary>

* **Authors:** Robbyant Team (Ka Leong Cheng, et al.)
* **arXiv ID:** 2601.20540 (Jan 2026)
* **One-liner:** 2026年最新的开源世界模型里程碑，实现了**分钟级**的长时记忆和**实时**交互，旨在弥合开源与闭源（如 Google Genie 3）之间的差距
* **Published in:** arXiv 2026
* **Links:** [[Paper]](https://arxiv.org/abs/2601.20540) | [[Code]](https://github.com/Robbyant/LingBot-World)



> **核心创新**
> 针对世界模型通常存在的“短期记忆”（几秒后场景就崩坏）和“推理延迟高”的问题，**LingBot-World** 提出了全新的解决方案。作为 Robbyant 团队 LingBot 系列（包括 LingBot-VA, LingBot-VLA）的核心组件，它不仅支持**高保真（High-Fidelity）**的物理动态模拟，还实现了**分钟级的时间一致性（Long-term Memory）**。更重要的是，它极度优化了推理速度，在消费级硬件上实现了 **<1秒** 的低延迟交互，使其成为首个真正可用的开源实时世界模拟器，适用于游戏、内容创作和机器人训练。

<details>
    <summary>Abstract</summary>
    我们介绍了 LingBot-World，一个源自视频生成的开源世界模拟器。作为一个顶级的世界模型，LingBot-World 具备三个核心特性：1) 在广泛的环境（现实、科学、卡通）中保持高保真度和鲁棒的动态；2) 实现了分钟级的时间跨度，同时保持上下文一致性（长时记忆）；3) 支持实时交互，在生成 16fps 视频时延迟低于 1 秒。我们开源了代码和模型，旨在缩小开源与闭源技术之间的差距，赋能社区在内容创作和机器人学习方面的应用。
</details>

<details>
    <summary>Key points</summary>
    * **分钟级一致性：** 突破了现有开源模型只能维持几秒钟连贯性的瓶颈。
    * **实时低延迟：** 专门优化了推理管道，支持实时的人机交互体验。
    * **全面开源：** 提供了完整的训练和推理代码，是 2026 年初开源社区的重要资产。
</details>
</details>

---

<details>
<summary><b>3D-VLA: 3D Generative World Model</b></summary>

* **Authors:** Chuang Gan, et al. (UMass Amherst / MIT-IBM Watson)
* **arXiv ID:** 2403.09631
* **One-liner:** 首次将“生成式世界模型”引入 3D 具身智能，不仅能感知 3D 场景，还能**想象**点云和深度的未来变化，从而规划出更精准的机器人动作
* **Published in:** ICML 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2403.09631) | [[Project]](https://vis-www.cs.umass.edu/3d-vla/)



> **核心创新**
> 传统的 VLA 模型（如 RT-2）大多基于 2D 图像，缺乏空间深度感，导致在处理复杂 3D 操作时笨拙。**3D-VLA** 引入了一个基于 **3D LLM** 的架构，通过在一系列交互 Token 中注入 3D 位置信息。其最大的创新是构建了一个**生成式世界模型**，该模型不是生成像素视频，而是直接生成**未来的 3D 点云（Point Cloud）和深度图**。这使得机器人可以在执行动作前，先在“脑海”中模拟出物体被移动后的 3D 状态，从而极大地提高了规划的成功率。

<details>
    <summary>Abstract</summary>
    最近的 VLA 模型依赖于 2D 输入，缺乏与 3D 物理世界的整合。我们提出了 3D-VLA，通过引入生成式世界模型无缝连接 3D 感知、推理和动作。3D-VLA 建立在 3D-LLM 之上，引入了一组交互 Token。通过我们在大规模 3D 具身指令数据集上的训练，3D-VLA 展示了强大的 3D 推理、多模态目标生成（图像、深度、点云）和动作规划能力。生成式世界模型允许机器人预测其动作对 3D 环境的影响。
</details>

<details>
    <summary>Key points</summary>
    * **3D 想象力：** 能够生成未来的 3D 几何结构（点云/深度），而非仅仅是 2D 像素。
    * **空间推理：** 解决了 2D VLM 在空间关系理解上的先天不足。
    * **数据构建：** 提出了从现有机器人数据集提取 3D 信息的大规模数据管线。
</details>
</details>

---

<details>
<summary><b>DriveVLM: VLM for Autonomous Driving</b></summary>

* **Authors:** Tsinghua University / Li Auto
* **arXiv ID:** 2402.12289
* **One-liner:** 探索大语言模型（LLM/VLM）在自动驾驶中的潜力，利用**思维链（Chain-of-Thought）**推理来解决长尾场景和复杂交互，并发布了 SUP-AD 数据集
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2402.12289) | [[Project]](https://tsinghua-mars-lab.github.io/DriveVLM/)



> **核心创新**
> 传统的自动驾驶系统往往是“黑盒”或基于规则的，难以处理罕见的角落案例（Corner Cases，如路边奇怪的动物或复杂的手势）。**DriveVLM** 提出利用大视觉语言模型（VLM）的常识推理能力。它不直接输出控制信号，而是先进行**场景描述**，再进行**场景分析**，最后形成**分层规划**。这种类似人类的 **Chain-of-Thought (CoT)** 过程使得决策更加透明和鲁棒。此外，为了克服推理速度慢的问题，它提出了 **DriveVLM-Dual**，将慢速的 VLM 推理与快速的传统自动驾驶管线结合。

<details>
    <summary>Abstract</summary>
    自动驾驶不仅需要感知，还需要理解复杂的场景并进行推理。我们提出了 DriveVLM，一个利用大视觉语言模型（VLM）进行场景理解和规划的自动驾驶系统。我们设计了一个思维链（CoT）机制，通过描述、分析和规划三个步骤来模拟人类的驾驶决策过程。此外，我们提出了 DriveVLM-Dual，通过混合系统协同传统规划器与 VLM，确保了实时性和高性能。我们还发布了 SUP-AD 数据集用于相关的研究。
</details>

<details>
    <summary>Key points</summary>
    * **思维链驾驶（CoT Driving）：** 将驾驶任务分解为逻辑推理步骤，提升了可解释性。
    * **双流系统（Dual System）：** 解决了大模型推理延迟高无法上车的工程难题。
    * **长尾处理：** 利用 VLM 的世界知识有效处理罕见和复杂的交通场景。
</details>
</details>

---