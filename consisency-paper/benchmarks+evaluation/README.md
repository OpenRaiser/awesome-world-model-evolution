<p align="center">
  <a href="./README.md">English</a> | <a href="./README_zh.md">中文</a>
</p>

## 📊 Benchmarks and Evaluation

**Current Challenge**: Existing metrics (FID, FVD, CLIP Score) inadequately assess world model capabilities, focusing on perceptual quality rather than physical understanding.

**Need for Comprehensive Benchmarks:**

A true world model benchmark should evaluate:
- 🧩 **Commonsense Physics Understanding**: Does the model respect gravity, momentum, conservation laws?
- 🔮 **Counterfactual Reasoning**: Can it predict outcomes of hypothetical interventions?
- ⏳ **Long-term Consistency**: Does coherence break down over extended simulation horizons?
- 🎯 **Goal-Directed Planning**: Can it chain actions to achieve complex objectives?
- 🎛️ **Controllability**: How precisely can users manipulate simulated elements?

#### Representative Works

<details>
<summary><b>WISE: A World Knowledge-Informed Semantic Evaluation for Text-to-Image Generation</b></summary>

* **Authors:** Yuwei Niu, Munan Ning, Mengren Zheng, Weiyang Jin, Bin Lin, Peng Jin, Jiaqi Liao, Chaoran Feng, Kunpeng Ning, Bin Zhu, Li Yuan
* **arXiv ID:** 2503.07265
* **One-liner:** Introduces WISE, a world-knowledge-aware evaluation framework that measures semantic alignment and common-sense correctness in text-to-image generation.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2503.07265) | [[PDF]](https://arxiv.org/pdf/2503.07265.pdf) | [[Code]](https://github.com/PKU-YuanGroup/WISE)

> **Core Innovation**  
> WISE argues that “evaluation must incorporate world knowledge” and constructs a text-to-image consistency assessment framework grounded in real-world semantic constraints, conceptual relations, and commonsense reasoning. This approach significantly improves measurement of text–image alignment and comprehension beyond mere CLIP similarity.

<details>
    <summary>Abstract</summary>
    Text-to-Image (T2I) models are capable of generating high-quality artistic creations and visual content. However, existing research and evaluation standards predominantly focus on image realism and shallow text-image alignment, lacking a comprehensive assessment of complex semantic understanding and world knowledge integration in text to image generation. To address this challenge, we propose WISE, the first benchmark specifically designed for World Knowledge-Informed Semantic Evaluation. WISE moves beyond simple word-pixel mapping by challenging models with 1000 meticulously crafted prompts across 25 sub-domains in cultural common sense, spatio-temporal reasoning, and natural science. To overcome the limitations of traditional CLIP metric, we introduce WIScore, a novel quantitative metric for assessing knowledge-image alignment. Through comprehensive testing of 20 models (10 dedicated T2I models and 10 unified multimodal models) using 1,000 structured prompts spanning 25 subdomains, our findings reveal significant limitations in their ability to effectively integrate and apply world knowledge during image generation, highlighting critical pathways for enhancing knowledge incorporation and application in next-generation T2I models. Code and data are available at this https URL.
</details>

<details>
    <summary>Key points</summary>
    * Evaluates world knowledge and common-sense reasoning in T2I models  
    * Measures entity correctness, relational consistency, attributes, and scene realism  
    * Shows stronger correlation with human preference vs CLIPScore/BERTScore  
    * Designed as a standardized benchmark for semantic T2I evaluation  
</details>
</details>

---

<details>
<summary><b>Are Video Models Ready as Zero-Shot Reasoners? An Empirical Study with the MME-COF Benchmark</b></summary>

* **Authors:** Ziyu Guo, Xinyan Chen, Renrui Zhang, Ruichuan An, Yu Qi, Dongzhi Jiang, Xiangtai Li, Manyuan Zhang, Hongsheng Li, Pheng-Ann Heng
* **arXiv ID:** 2510.26802
* **One-liner:** Proposes MME-COF benchmark to evaluate zero-shot video reasoning ability across memory, motion, events, causality, and forecasting — showing that current video models lag behind VLMs.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2510.26802) | [[PDF]](https://arxiv.org/pdf/2510.26802.pdf) | [[Code]](https://github.com/ZiyuGuo99/MME-CoF)

> **Core Innovation**  
> For the first time systematically evaluates “zero-shot reasoning” capability of large video models, introduces the MME-CoF benchmark (Memory, Motion, Event, Causality, Object, Future prediction), and reveals that video models lag markedly behind vision-language LLMs in fine-grained causal understanding.

<details>
    <summary>Abstract</summary>
    Recent video generation models can produce high-fidelity, temporally coherent videos, indicating that they may encode substantial world knowledge. Beyond realistic synthesis, they also exhibit emerging behaviors indicative of visual perception, modeling, and manipulation. Yet, an important question still remains: Are video models ready to serve as zero-shot reasoners in challenging visual reasoning scenarios? In this work, we conduct an empirical study to comprehensively investigate this question, focusing on the leading and popular Veo-3. We evaluate its reasoning behavior across 12 dimensions, including spatial, geometric, physical, temporal, and embodied logic, systematically characterizing both its strengths and failure modes. To standardize this study, we curate the evaluation data into MME-CoF, a compact benchmark that enables in-depth and thorough assessment of Chain-of-Frame (CoF) reasoning. Our findings reveal that while current video models demonstrate promising reasoning patterns on short-horizon spatial coherence, fine-grained grounding, and locally consistent dynamics, they remain limited in long-horizon causal reasoning, strict geometric constraints, and abstract logic. Overall, they are not yet reliable as standalone zero-shot reasoners, but exhibit encouraging signs as complementary visual engines alongside dedicated reasoning models.
</details>

<details>
    <summary>Key points</summary>
    * MME-COF benchmark: Memory, Motion, Event, Causality, Object, Future prediction  
    * Zero-shot evaluation — no task-specific video fine-tuning  
    * Reveals video models are weaker in causal & common-sense reasoning  
    * Shows video models rely on pattern recognition rather than deep inference  
</details>
</details>

---

<details>
<summary><b>PhysDreamer: Physics-Based Interaction from Videos</b></summary>

* **Authors:** Thurand et al. (TUM / Google)
* **arXiv ID:** 2404.13026
* **One-liner:** 通过从静态视频中推断物体材质属性，赋予 3D Gaussian Splatting 物理交互能力，实现逼真的“戳、扔、推”模拟
* **Published in:** ECCV 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2404.13026) | [[Project]](https://physdreamer.github.io/)

> **核心创新**
> 现有的 3D 重建（如 3DGS）通常是静态的，无法进行物理互动。**PhysDreamer** 旨在让静态的 3D 场景“动起来”。它利用视频生成模型作为先验，观察物体在视频中的微小运动来推断其**物理材质属性（Material Properties）**（如弹性、质量、摩擦力）。PhysDreamer 将这些属性赋予 3D 高斯基元，并结合基于粒子的物理模拟器（如 MPM）。结果是，用户可以在重建的场景中点击花草、扔出枕头，物体会根据牛顿力学做出逼真的响应，实现了从视觉重建到**物理重建**的跨越。

<details>
    <summary>Abstract</summary>
    我们提出了 PhysDreamer，一种从视频中通过逆向渲染学习物体物理属性并实现交互式模拟的方法。通过利用视频扩散模型作为动态先验，我们合成了物体在不同外力作用下的运动视频。然后，PhysDreamer 优化 3D 高斯场的物理参数（如杨氏模量、泊松比），使其模拟的动力学与生成的视频运动相匹配。这使得用户能够以物理上合理的方式与重建的 3D 场景进行实时交互。
</details>

<details>
    <summary>Key points</summary>
    * **物理属性推断：** 从视觉观察反推看不见的物理参数（软/硬，轻/重）。
    * **视频先验驱动：** 利用 Video Diffusion Model 生成“假想”的物体受力视频来指导物理参数优化。
    * **交互式 3DGS：** 赋予了 3D Gaussian Splatting 真实的物理模拟能力。
</details>
</details>

---

<details>
<summary><b>VBench: Comprehensive Benchmark for Video Generation Models</b></summary>

* **Authors:** Ziqi Huang, et al. (Shanghai AI Laboratory)
* **arXiv ID:** 2311.17982
* **One-liner:** 当前最权威的视频生成全维评估基准，涵盖 16 个维度（如主体一致性、运动平滑度、美学质量），提供了细粒度的量化评分
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2311.17982) | [[Project]](https://vchitect.github.io/VBench-project/)

> **核心创新**
> 在 VBench 之前，视频生成缺乏统一且细致的评估标准。**VBench** 将视频质量解耦为 **16 个独立的维度**（例如：背景一致性、运动幅度、美学评分、人类动作、时序闪烁等）。它不仅提供了一个包含 Prompt 的数据集，还为每个维度设计了专门的**自动评估模块（Evaluation Modules）**。这使得研究人员可以像看“体检报告”一样，清楚地知道自己的模型在哪个方面（如“画质好但动作小”）存在短板，是目前视频生成领域的黄金标准。

<details>
    <summary>Abstract</summary>
    视频生成模型的快速发展需要全面且细粒度的评估基准。我们提出了 VBench，这是一个用于评估文本到视频生成模型的综合基准。我们将视频生成的评估分解为 16 个分层维度，涵盖了视频质量、时间连贯性、运动复杂性和文本对齐等方面。我们精心设计了提示词套件和自动评估方法，以确保与人类感知的高度一致性。对主流模型的广泛评估揭示了它们在不同维度上的权衡，为未来的改进指明了方向。
</details>

<details>
    <summary>Key points</summary>
    * **16个评估维度：** 全面覆盖从单帧画质到长时动态的各个方面。
    * **自动评估器：** 提供了基于 AI 的自动打分工具，无需昂贵的人工评测。
    * **分层分析：** 能够区分模型在“静态画质”和“动态逻辑”上的不同表现。
</details>
</details>

---

<details>
<summary><b>UniSandbox: Understanding vs. Generation Analysis</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.20561
* **One-liner:** 首个深入探究“多模态理解能力”与“生成能力”之间是否存在因果关联的分析平台，并指出了统一模型（Unified Models）未来的改进路径。
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.20561)

> **核心创新**
> 目前的多模态大模型（如 Gemini, GPT-4o）通常即是“理解者”也是“创作者”。**UniSandbox** 提出了一个核心科学问题：**“理解得越好，生成的就越好吗？”** 该研究构建了一个受控的“沙盒”环境，在同一模型架构下解耦分析理解任务（如 VQA）和生成任务（如 T2I/T2V）的表现。研究发现两者并非总是正相关，并揭示了当今统一模型在特征对齐上的深层矛盾。

<details>
    <summary>Abstract</summary>
    统一多模态模型在理解和生成任务上都取得了巨大成功，但这两两种能力之间的相互作用机制仍不清楚。UniSandbox 是一个综合分析框架，旨在量化“理解”对“生成”的贡献。通过在涵盖细粒度视觉识别、空间推理和语义对齐的一系列受控实验中测试主流统一模型，我们发现强大的理解能力并不自动转化为生成质量。论文最后提出了“理解引导生成（Understanding-Informed Generation）”的新路径，旨在弥合这两个范式之间的差距。
</details>

<details>
    <summary>Key points</summary>
    * **相关性分析：** 打破了“理解强=生成强”的简单假设。
    * **统一架构评估：** 专注于在同一权重下进行双向能力的评估。
    * **未来路径：** 提出了利用判别式特征增强生成式扩散过程的新方法。
</details>
</details>

---

<details>
<summary><b>Rover: Reciprocal Omnimodal Reasoning</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.01163
* **One-liner:** 针对全模态（Omnimodal）生成的基准测试，利用“互惠推理（Reciprocal Reasoning）”机制（如生成后反向描述）来衡量模型的跨模态一致性。
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.01163)

> **核心创新**
> 传统的生成评测通常是单向的（文本->图像）。**Rover** 引入了**互惠性（Reciprocity）**的概念，即一个好的全模态模型应该能够在一个闭环中保持信息不丢失。例如，模型从文本生成音频，再从音频生成视频，最后生成的视频应能被反向描述回原始文本。Rover 建立了一套涵盖图像、视频、音频和 3D 的多跳推理任务，是衡量“全能模型”跨模态对齐能力的试金石。

<details>
    <summary>Abstract</summary>
    随着全模态生成模型的出现，单向评估已不足以捕捉模态间的复杂交互。我们提出了 Rover，一个用于基准测试互惠跨模态推理的框架。Rover 包含多个循环生成任务（例如 Text-to-Image-to-Text, Audio-to-Video-to-Audio）。通过衡量循环过程中的语义漂移（Semantic Drift）和信息丢失，Rover 量化了模型在不同模态间转换的鲁棒性。实验表明，即使是最先进的模型在多跳推理中也会出现严重的“电话传话”效应（信息逐级失真）。
</details>

<details>
    <summary>Key points</summary>
    * **互惠循环（Reciprocal Cycle）：** 使用闭环一致性作为核心评价指标。
    * **全模态覆盖：** 涵盖 Text, Image, Video, Audio, 3D 五大模态。
    * **语义漂移量化：** 精确测量模态转换过程中的信息损失。
</details>
</details>

---

<details>
<summary><b>VR-Bench: Maze-Solving Reasoning</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.15065
* **One-liner:** 独辟蹊径地通过“迷宫求解”任务来评估视频模型的时空规划与推理能力，考察模型是否具备长时程的路径规划智能。
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.15065)

> **核心创新**
> 许多视频基准测试只关注画面是否流畅，而忽略了模型是否真的“有脑子”。**VR-Bench** (Maze Edition) 提出了一个极其具体的挑战：**迷宫求解**。它输入迷宫的俯视图或第一人称视角，要求视频模型生成走出迷宫的正确路径视频。这强迫模型必须理解空间拓扑、具备前瞻性规划（Look-ahead Planning）能力，并严格遵循物理约束（不能穿墙），是检验视频模型“System 2”逻辑推理能力的硬核试题。

<details>
    <summary>Abstract</summary>
    视频生成不仅仅是像素的渲染，更是对动态世界的模拟。为了评估视频模型的深层推理能力，我们推出了 VR-Bench，这是首个基于迷宫求解任务的评测基准。我们构建了从简单 2D 迷宫到复杂 3D 环境的层级化数据集。模型需要生成从起点到终点的连贯视频序列。评估结果显示，现有的 SOTA 视频模型虽然画质精美，但在涉及多步决策和死胡同回溯的迷宫导航中表现往往不及简单的搜索算法，揭示了其在逻辑规划上的短板。
</details>

<details>
    <summary>Key points</summary>
    * **任务驱动评估：** 用具体的求解任务（Maze）替代主观打分。
    * **空间拓扑推理：** 测试模型对连通性、死胡同和路径规划的理解。
    * **智力测试：** 将视频生成模型作为智能体（Agent）进行 IQ 测试。
</details>
</details>

---

<details>
<summary><b>PhysBench: Physical Commonsense</b></summary>

* **Authors:** Wei Feng, et al.
* **arXiv ID:** 2404.01321
* **One-liner:** 专注于“物理常识”的视频生成基准，通过与物理引擎模拟的真值对比，量化评估模型对牛顿力学、流体和碰撞的遵循程度。
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2404.01321)

> **核心创新**
> 为了解决视频生成中常见的“物理幻觉”（如悬空物体、错误碰撞），**PhysBench** 建立了一个基于物理模拟器（Simulator-based）的评估体系。它不仅看视频像不像，更看**物理对不对**。通过涵盖刚体、柔体、流体等多种物理场景，PhysBench 直接比较生成视频中的物体轨迹与物理引擎计算出的真实轨迹，从而给出一个客观的“物理逼真度（SimRealism）”分数。

<details>
    <summary>Abstract</summary>
    我们介绍了 PhysBench，一个旨在评估文本到视频模型物理常识的基准。该基准包含各类物理现象，如碰撞、坠落、摩擦和流体动力学。不同于以往依赖人类评分的方法，PhysBench 利用物理引擎生成参考数据，或使用视觉基础模型检测生成内容中的物理违规行为。我们的评估表明，即便是先进的模型在处理简单的物理交互时也常违背基本物理定律。
</details>

<details>
    <summary>Key points</summary>
    * **硬物理约束：** 关注重力、碰撞、守恒定律等基本规则。
    * **模拟器验证：** 使用物理引擎作为 Ground Truth。
    * **客观指标：** 减少了人类主观审美对评分的干扰。
</details>
</details>

---

<details>
<summary><b>TiViBench: Think-in-Video Reasoning</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.13704
* **One-liner:** 借鉴大语言模型的 Chain-of-Thought，评估视频生成模型是否具备“视频思维链（Think-in-Video）”能力，即先规划后生成的推理过程。
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.13704)

> **核心创新**
> 现有的视频生成模型往往是“直觉式”的（从文本直接映射到像素）。**TiViBench** 提倡并评估一种新的范式：**Think-in-Video**。它考察模型是否能在生成最终视频前，隐式或显式地生成中间状态（如关键帧草图、动态流场或因果逻辑链）。TiViBench 设计了一系列需要多步推理才能正确生成的任务（如“多米诺骨牌效应”），并检查模型是否能通过“思考”过程来提高复杂动态生成的准确性。

<details>
    <summary>Abstract</summary>
    视频生成不仅仅是像素预测，它需要对事件演变进行连贯的推理。TiViBench 旨在基准测试视频生成模型的“视频内思考（Think-in-Video）”能力。我们定义了不同难度的推理任务，要求模型展示其生成过程中的因果逻辑。通过对比直接生成与包含中间推理步骤（如关键帧规划）的生成效果，TiViBench 验证了推理能力对视频时间一致性和逻辑正确性的关键作用。
</details>

<details>
    <summary>Key points</summary>
    * **过程导向评估：** 不仅看结果，更看生成背后的逻辑链条。
    * **因果推演：** 重点测试模型处理连锁反应（Chain Reaction）的能力。
    * **规划 vs 直觉：** 区分模型是靠记忆训练数据还是靠实时推理。
</details>
</details>

---

<details>
<summary><b>Weave: Interleaved Comprehension & Generation</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.11434
* **One-liner:** 针对“交织模态（Interleaved）”场景（图文混排输入输出）的综合基准，解锁并评估模型在长上下文中的上下文学习（In-Context Learning）能力。
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.11434)

> **核心创新**
> 真实世界的互联网数据往往是**图文交织（Interleaved）**的（如博客文章、幻灯片）。**Weave** 突破了单一的“文生图”或“图生文”界限，专注于评估模型处理**任意序列图文混合流**的能力。它测试模型能否通过阅读前面的“图1+文1+图2”，推断出接下来的“文2”或“图3”。这不仅考察了多模态理解，还重点测试了模型在混合模态下的**上下文学习（ICL）**和风格迁移能力。

<details>
    <summary>Abstract</summary>
    多模态交互的未来在于能够流畅处理交织的文本和视觉内容。Weave 是一个用于释放和基准测试上下文交织理解与生成能力的数据集。它包含从互联网构建的高质量图文序列，涵盖故事叙述、教程演示和对话记录。Weave 要求模型在长上下文中保持叙事连贯性和视觉风格一致性。我们的分析揭示了现有模型在处理长序列交织内容时的注意力衰减问题，并为下一代原生多模态模型提供了标准。
</details>

<details>
    <summary>Key points</summary>
    * **交织格式（Interleaved）：** 模拟真实的 Web/文档阅读体验。
    * **混合模态 ICL：** 测试模型能否通过示例学习新的视觉-文本模式。
    * **双向测试：** 同时包含 Next-Text Prediction 和 Next-Image Prediction。
</details>
</details>

---

<details>
<summary><b>Thinking with Video: Video Generation as Reasoning</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.04570
* **One-liner:** 提出“视频生成即推理”的新范式，认为预测视频的未来帧本质上就是对物理世界进行因果推理和模拟的过程。
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.04570)

> **核心创新**
> 长期以来，推理（Reasoning）被认为是语言模型的专属领域。**Thinking with Video** 挑战了这一观点，提出视频生成模型（Video Generation Models）通过模拟未来的像素变化，实际上是在进行非语言的、直觉物理层面的推理。文章展示了通过训练模型生成“解决问题”的视频序列（如堆叠积木、工具使用），模型能够涌现出类似于规划（Planning）和反事实推断的能力，证明了视频生成是一种有前景的多模态推理范式。

<details>
    <summary>Abstract</summary>
    我们探讨了视频生成作为一种通用多模态推理范式的潜力。不同于依赖符号逻辑的语言推理，视频生成要求模型内化物理定律、因果关系和物体恒常性。我们通过一系列复杂的物理交互任务证明，当视频生成模型被要求预测行动的后果时，它们表现出了强大的推理能力。我们提出了“Thinking with Video”框架，利用视频预测作为思维链的视觉模拟，显著提高了机器人在复杂环境中的决策准确性。
</details>

<details>
    <summary>Key points</summary>
    * **视觉模拟（Visual Simulation）：** 将生成未来帧视为一种思维过程。
    * **物理推理：** 验证了视频模型对重力、碰撞和流体动力学的隐式理解。
    * **非语言思维链：** 展示了视觉预测如何替代文本 CoT 进行任务规划。
</details>
</details>

---

<details>
<summary><b>V-ReasonBench: Unified Reasoning Suite</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.16668
* **One-liner:** 一个迈向统一化的视频生成推理评测套件，系统性地评估模型在时序逻辑、因果关系和物理一致性三大维度的“智商”。
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.16668)

> **核心创新**
> 现有的视频评测往往是碎片化的（有的测物理，有的测画质）。**V-ReasonBench** 旨在建立一个**统一的（Unified）**推理基准。它不再关注光影效果，而是构建了一个包含数百种逻辑模式的测试集，涵盖了从简单的物体追踪到复杂的蝴蝶效应（连锁反应）。该基准引入了自动化的“逻辑检查器（Logic Checkers）”，能够判断生成的视频内容是否违背了基本的时空逻辑，是目前最全面的视频模型逻辑能力体检表。

<details>
    <summary>Abstract</summary>
    视频生成模型的快速发展迫切需要对其推理能力进行标准化评估。V-ReasonBench 是一个统一的推理基准套件，旨在量化视频生成模型的认知能力。我们定义了一个包含时序逻辑、因果推理和物理一致性的三层分类法。通过大规模的自动评估和人工验证，我们发现当前的 SOTA 模型在处理长时序依赖和复杂因果链时仍表现脆弱。V-ReasonBench 为下一代具备更高逻辑一致性的视频模型指明了方向。
</details>

<details>
    <summary>Key points</summary>
    * **统一分类法：** 整合了时序、因果、物理三个维度的推理任务。
    * **逻辑检查器：** 引入程序化验证方法，减少人工主观偏差。
    * **长时序挑战：** 特别关注视频后半段的逻辑是否与前半段自洽。
</details>
</details>

---

<details>
<summary><b>GGBench: Geometric Generative Reasoning</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.11134
* **One-liner:** 专注于“几何生成推理”的基准，测试多模态模型在生成过程中是否理解空间变换、3D 结构和几何约束。
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.11134)

> **核心创新**
> 许多生成模型在处理透视关系和几何结构时经常出错（如画出扭曲的椅子或错误的镜像）。**GGBench** 是首个专注于**几何推理（Geometric Reasoning）**的生成基准。它要求模型完成诸如“生成一个物体旋转 90 度的视图”、“生成该物体的镜像”或“将两个物体以特定几何关系组合”等任务。GGBench 揭示了模型虽然能生成逼真的纹理，但在保持刚体几何结构和空间一致性方面仍有巨大缺陷。

<details>
    <summary>Abstract</summary>
    几何一致性是高质量多模态生成的基石。GGBench 提出了一个几何生成推理基准，旨在评估统一多模态模型对空间结构和几何变换的掌握程度。基准涵盖了 2D 几何变换、3D 视角合成和空间关系推理等任务。我们利用精确的几何度量标准（如关键点匹配误差、姿态估计误差）来评估生成结果。实验表明，即使是顶级的扩散模型在面对需要精确几何控制的任务时，也往往难以保持结构的完整性。
</details>

<details>
    <summary>Key points</summary>
    * **几何刚性（Geometric Rigidity）：** 测试物体在生成中是否变形。
    * **空间变换：** 考察旋转、缩放、镜像等操作的准确性。
    * **多模态对齐：** 验证文本描述的空间关系是否在图像中正确体现。
</details>
</details>

---

<details>
<summary><b>TempViz: Temporal Knowledge in T2I</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2601.14951
* **One-liner:** 探讨并评估静态文本到图像（T2I）模型中隐含的“时间知识”，如对历史年代、季节变化、运动模糊及时间流逝概念的理解。
* **Published in:** arXiv 2026
* **Links:** [[Paper]](https://arxiv.org/abs/2601.14951)

> **核心创新**
> 我们通常认为图像是静态的，但图像中蕴含着丰富的时间信息（如“维多利亚时代的服饰”或“疾驰汽车的模糊”）。**TempViz** 是一个专门评估 T2I 模型**时间知识（Temporal Knowledge）**的工具。它测试模型是否能准确生成特定历史时期的场景（Chronological Knowledge），是否能通过视觉元素表达“速度”和“过程”（Dynamic Implication），以及是否理解“古代”与“现代”的视觉差异。这是一项关于静态模型如何编码第四维度（时间）的新颖研究。

<details>
    <summary>Abstract</summary>
    尽管文本到图像模型主要生成静态内容，但它们必须具备丰富的时间知识才能生成连贯且符合上下文的图像。TempViz 是一个针对 T2I 模型时间知识的评估框架。我们从年代学准确性、动态运动暗示和时间因果快照（如破碎的玻璃暗示刚刚发生的动作）三个维度构建了数据集。评估发现，模型在生成具体历史细节时表现出色，但在表达抽象的时间流逝和瞬间动态（Instantaneous Dynamics）方面存在显著偏差，往往通过过度模糊或错误的物理状态来呈现。
</details>

<details>
    <summary>Key points</summary>
    * **年代学评估：** 测试模型对不同历史时期视觉风格的掌握。
    * **动态暗示（Implied Motion）：** 评估模型如何用静态像素表现“动感”。
    * **时间快照：** 考察模型对事件“发生中”或“发生后”状态的区分。
</details>
</details>

---