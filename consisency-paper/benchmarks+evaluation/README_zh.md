<p align="center">
  <a href="README.md">English</a> | <a href="README_zh.md">中文</a>
</p>

## 📊 基准测试与评估

**当前挑战**：现有指标（FID、FVD、CLIP Score）无法充分评估世界模型能力，侧重于感知质量而非物理理解。

**综合基准测试的需求：**

真正的世界模型基准应评估：
- 🧩 **常识物理理解**：模型是否遵守重力、动量、守恒定律？
- 🔮 **反事实推理**：能否预测假设干预的结果？
- ⏳ **长期一致性**：在扩展的模拟时间范围内连贯性是否会崩溃？
- 🎯 **目标导向规划**：能否链接动作以实现复杂目标？
- 🎛️ **可控性**：用户能多精确地操控模拟元素？

#### 代表性工作

<details>
<summary><b>WISE: A World Knowledge-Informed Semantic Evaluation for Text-to-Image Generation</b></summary>

* **Authors:** Yuwei Niu, Munan Ning, Mengren Zheng, Weiyang Jin, Bin Lin, Peng Jin, Jiaqi Liao, Chaoran Feng, Kunpeng Ning, Bin Zhu, Li Yuan
* **arXiv ID:** 2503.07265
* **One-liner:** 提出可感知世界知识的语义一致性评价指标（WISE），用以衡量文生图模型是否真正理解常识与世界事实。
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2503.07265) | [[PDF]](https://arxiv.org/pdf/2503.07265.pdf) | [[Code]](https://github.com/PKU-YuanGroup/WISE)

> **核心创新**  
> WISE 强调“评价应包含世界知识”，构建了一个包含真实世界语义约束、概念关系和常识推理的文生图一致性评估体系，能够显著更准确地衡量文本-图像对齐与理解能力，而非只依赖 CLIP 相似度。

<details>
    <summary>Abstract</summary>
    文本到图像模型能生成高质量的艺术作品与视觉内容，然而现有研究与评估标准主要关注图像逼真度和浅层图文对齐，缺乏对复杂语义理解与世界知识融入的综合衡量。为此，我们提出首个面向世界知识引导语义评估的基准 WISE，超越简单词-像素映射，用涵盖文化常识、时空推理、自然科学 25 子域的 1000 条精心构造提示挑战模型。针对传统 CLIP 指标局限，我们提出新的量化度量 WIScore 评估知识-图像对齐度。通过对 20 个模型（10 个专用 T2I 与 10 个统一多模态）在 1000 条结构化提示上的全面测试，发现其生成图像时整合并应用世界知识的能力显著不足，为下一代模型增强知识融入指明关键路径。代码与数据见 https 链接。
</details>

<details>
    <summary>Key points</summary>
    * 引入“世界知识 + 常识推理”评估框架  
    * 评价维度：实体正确性、关系合理性、属性一致性、场景常识  
    * 与人工偏好高度相关，优于 CLIPScore/BERTScore 等指标  
    * 可用作未来文生图模型 benchmark 的通用评价层  
</details>
</details>

---

<details>
<summary><b>Are Video Models Ready as Zero-Shot Reasoners? An Empirical Study with the MME-COF Benchmark</b></summary>

* **Authors:** Ziyu Guo, Xinyan Chen, Renrui Zhang, Ruichuan An, Yu Qi, Dongzhi Jiang, Xiangtai Li, Manyuan Zhang, Hongsheng Li, Pheng-Ann Heng
* **arXiv ID:** 2510.26802
* **One-liner:** 构建 MME-COF 基准测试多模态视频模型的零样本常识与因果推理能力，发现当前视频模型仍缺乏真正时序-因果理解。
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2510.26802) | [[PDF]](https://arxiv.org/pdf/2510.26802.pdf) | [[Code]](https://github.com/ZiyuGuo99/MME-CoF)

> **核心创新**  
> 首次系统评估视频大模型的“零样本推理”能力，提出 MME-COF 基准（Memory, Motion, Event, Causality, Object, Future prediction），发现视频模型在细粒度因果理解方面显著落后于视觉-语言大模型。

<details>
    <summary>Abstract</summary>
    最新视频生成模型可产出高保真、时序连贯的视频，暗示其编码了丰富的世界知识。除逼真合成外，它们还表现出视觉感知、建模与操控的涌现行为。然而，一个重要问题仍未解答：在挑战性视觉推理场景中，视频模型是否已具备零样本推理能力？为此，我们对领先且流行的 Veo-3 开展实证研究，从空间、几何、物理、时间、具身逻辑等 12 个维度系统评估其推理表现，刻画优势与失效模式。为标准化评估，我们构建紧凑基准 MME-CoF，深入测评逐帧链式（CoF）推理。结果显示，当前视频模型在短程空间连贯、细粒度定位与局部一致动态上展现可喜模式，但在长程因果、严格几何与抽象逻辑上仍受限。总体而言，它们尚不足以作为独立零样本推理器，但已显露作为专用推理模型补充视觉引擎的潜力。
</details>

<details>
    <summary>Key points</summary>
    * MME-COF 六大测试维度：对象识别、记忆、动作、事件、因果、未来预测  
    * 面向“零样本”评估，无视频任务微调  
    * 视频模型 vs 文本-图像模型：前者推理能力不足  
    * 揭示了当前视频模型更偏“模式拟合”而非“语义推理”  
</details>
</details>

---

<details>
<summary><b>PhysDreamer: Physics-Based Interaction from Videos</b></summary>

* **Authors:** Thurand et al. (TUM / Google)
* **arXiv ID:** 2404.13026
* **One-liner:** Infers material properties from static videos to endow 3D Gaussian Splatting with physical interaction capabilities, enabling realistic "poke, throw, push" simulations.
* **Published in:** ECCV 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2404.13026) | [[Project]](https://physdreamer.github.io/)

> **Core Innovation**
> Existing 3D reconstructions (like 3DGS) are typically static and non-interactive. **PhysDreamer** aims to bring static 3D scenes to life. It leverages video generation models as priors, observing subtle motions to infer **Material Properties** (elasticity, mass, friction). PhysDreamer assigns these properties to 3D Gaussian primitives and integrates a particle-based physics simulator (MPM). The result is that users can poke flowers or throw pillows in the reconstructed scene, and objects respond realistically according to Newtonian mechanics, bridging the gap from visual to **physical reconstruction**.

<details>
    <summary>Abstract</summary>
    We present PhysDreamer, a method for learning object physical properties from video via inverse rendering to enable interactive simulation. Leveraging video diffusion models as dynamic priors, we synthesize videos of objects moving under various forces. PhysDreamer then optimizes the physical parameters (e.g., Young's modulus, Poisson's ratio) of a 3D Gaussian field so that its simulated dynamics match the generated video motions. This allows users to interact with reconstructed 3D scenes in a physically plausible manner in real-time.
</details>

<details>
    <summary>Key points</summary>
    * **Material Inference:** Infers invisible physical parameters (soft/hard, light/heavy) from visual observations.
    * **Video Prior Driven:** Uses Video Diffusion Models to generate "imagined" object motion videos to guide physical parameter optimization.
    * **Interactive 3DGS:** Endows 3D Gaussian Splatting with real physics simulation capabilities.
</details>
</details>

---

<details>
<summary><b>VBench: Comprehensive Benchmark for Video Generation Models</b></summary>

* **Authors:** Ziqi Huang, et al. (Shanghai AI Laboratory)
* **arXiv ID:** 2311.17982
* **One-liner:** The current gold standard for full-dimensional video generation evaluation, covering 16 dimensions (e.g., subject consistency, motion smoothness, aesthetics) with fine-grained quantitative scoring.
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2311.17982) | [[Project]](https://vchitect.github.io/VBench-project/)

> **Core Innovation**
> Before VBench, video generation lacked a unified and granular evaluation standard. **VBench** decomposes video quality into **16 independent dimensions** (e.g., Background Consistency, Motion Magnitude, Aesthetic Score, Human Action, Temporal Flickering). It provides not only a dataset of prompts but also specialized **Evaluation Modules** for each dimension. This allows researchers to see a "health report" of their model, clearly identifying specific weaknesses (e.g., "good image quality but small motion"), making it the standard benchmark in the field.

<details>
    <summary>Abstract</summary>
    The rapid evolution of video generation models demands a comprehensive and fine-grained evaluation benchmark. We propose VBench, a benchmark for evaluating text-to-video generation models. We decompose video generation evaluation into 16 hierarchical dimensions, covering video quality, temporal coherence, motion complexity, and text alignment. We carefully design prompt suites and automatic evaluation methods to ensure high alignment with human perception. Extensive evaluation of mainstream models reveals trade-offs across different dimensions, guiding future improvements.
</details>

<details>
    <summary>Key points</summary>
    * **16 Evaluation Dimensions:** Comprehensively covers everything from single-frame quality to long-term dynamics.
    * **Automatic Evaluators:** Provides AI-based scoring tools, eliminating the need for expensive human evaluation.
    * **Hierarchical Analysis:** Distinguishes model performance between "static quality" and "dynamic logic."
</details>
</details>

---

<details>
<summary><b>UniSandbox: Understanding vs. Generation Analysis</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.20561
* **One-liner:** The first analytical platform to deeply investigate the causal link between "multimodal understanding" and "generation," outlining the path forward for unified models.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.20561)

> **Core Innovation**
> Current unified multimodal models (e.g., Gemini, GPT-4o) serve as both "understanders" and "creators." **UniSandbox** poses a critical scientific question: **"Does better understanding imply better generation?"** It constructs a controlled "sandbox" environment to decouple and analyze performance in understanding tasks (e.g., VQA) versus generation tasks (e.g., T2I/T2V) within the same model architecture. The study reveals that the two are not always positively correlated and exposes deep conflicts in feature alignment within current unified models.

<details>
    <summary>Abstract</summary>
    Unified multimodal models have achieved success in both understanding and generation, yet the interaction mechanism between these capabilities remains unclear. UniSandbox is a comprehensive analysis framework designed to quantify the contribution of "understanding" to "generation." By testing mainstream unified models across controlled experiments covering fine-grained visual recognition, spatial reasoning, and semantic alignment, we find that strong understanding capabilities do not automatically translate to generation quality. The paper concludes by proposing a new path for "Understanding-Informed Generation" to bridge the gap between these paradigms.
</details>

<details>
    <summary>Key points</summary>
    * **Correlation Analysis:** Challenges the simple assumption that "strong understanding = strong generation."
    * **Unified Architecture Eval:** Focuses on evaluating bidirectional capabilities under the same weights.
    * **Path Forward:** Proposes methods to enhance generative diffusion processes using discriminative features.
</details>
</details>

---

<details>
<summary><b>Rover: Reciprocal Omnimodal Reasoning</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.01163
* **One-liner:** A benchmark for omnimodal generation that uses "Reciprocal Reasoning" mechanisms (e.g., generation followed by reverse captioning) to measure cross-modal consistency.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.01163)

> **Core Innovation**
> Traditional generation evaluation is often unidirectional (Text->Image). **Rover** introduces the concept of **Reciprocity**, positing that a good omnimodal model should maintain information integrity within a closed loop. For instance, generating audio from text, then video from audio; the final output should be descriptively reversible to the original text. Rover establishes a set of multi-hop reasoning tasks covering Image, Video, Audio, and 3D, serving as a touchstone for the cross-modal alignment of "Omni-models."

<details>
    <summary>Abstract</summary>
    With the emergence of omnimodal generative models, unidirectional evaluation is insufficient to capture complex inter-modal interactions. We propose Rover, a framework for benchmarking reciprocal cross-modal reasoning. Rover includes multiple cyclic generation tasks (e.g., Text-to-Image-to-Text, Audio-to-Video-to-Audio). By measuring semantic drift and information loss during the cycle, Rover quantifies the robustness of model transitions between modalities. Experiments show that even SOTA models suffer from severe "telephone game" effects (progressive distortion) in multi-hop reasoning.
</details>

<details>
    <summary>Key points</summary>
    * **Reciprocal Cycle:** Uses closed-loop consistency as the core metric.
    * **Omnimodal Coverage:** Covers Text, Image, Video, Audio, and 3D.
    * **Drift Quantification:** Precisely measures information loss during modal transitions.
</details>
</details>

---

<details>
<summary><b>VR-Bench: Maze-Solving Reasoning</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.15065
* **One-liner:** Uniquely evaluates spatiotemporal planning and reasoning in video models via "Maze-Solving" tasks, testing long-horizon path planning intelligence.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.15065)

> **Core Innovation**
> Many video benchmarks focus on visual smoothness, ignoring whether the model has "brains." **VR-Bench** (Maze Edition) proposes a specific challenge: **Maze Solving**. It inputs a top-down or first-person view of a maze and requires the video model to generate the correct path out. This forces the model to understand spatial topology, exercise **Look-ahead Planning**, and strictly adhere to physical constraints (no wall-clipping), serving as a hardcore test for "System 2" logical reasoning.

<details>
    <summary>Abstract</summary>
    Video generation is not just pixel rendering but dynamic world simulation. To evaluate deep reasoning capabilities, we introduce VR-Bench, the first benchmark based on maze-solving tasks. We construct a hierarchical dataset ranging from simple 2D mazes to complex 3D environments. Models must generate coherent video sequences from start to finish. Results show that while current SOTA models produce beautiful visuals, they often perform worse than simple search algorithms in maze navigation involving multi-step decisions and backtracking, revealing significant deficits in logical planning.
</details>

<details>
    <summary>Key points</summary>
    * **Task-Driven Eval:** Replaces subjective scoring with concrete solving tasks (Maze).
    * **Topological Reasoning:** Tests understanding of connectivity, dead ends, and path planning.
    * **IQ Test:** Treats video generation models as agents undergoing an intelligence test.
</details>
</details>

---

<details>
<summary><b>PhysBench: Physical Commonsense</b></summary>

* **Authors:** Wei Feng, et al.
* **arXiv ID:** 2404.01321
* **One-liner:** A benchmark focused on "Physical Commonsense," quantifying adherence to Newtonian mechanics, fluids, and collisions by comparing generated videos against physics engine simulations.
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2404.01321)

> **Core Innovation**
> To address "physical hallucinations" in video generation (e.g., floating objects, incorrect collisions), **PhysBench** establishes a **Simulator-based** evaluation system. It looks not just at visual realism, but **Physical Correctness**. Covering rigid bodies, soft bodies, and fluids, PhysBench directly compares object trajectories in generated videos with ground truth from physics engines, providing an objective "SimRealism" score.

<details>
    <summary>Abstract</summary>
    We introduce PhysBench, a benchmark designed to evaluate physical commonsense in text-to-video models. The benchmark covers various physical phenomena such as collisions, falling, friction, and fluid dynamics. Unlike previous methods relying on human scoring, PhysBench utilizes physics engines to generate reference data or uses vision foundation models to detect physical violations. Our evaluation shows that even advanced models often violate basic physical laws when handling simple interactions.
</details>

<details>
    <summary>Key points</summary>
    * **Hard Physics Constraints:** Focuses on gravity, collisions, and conservation laws.
    * **Simulator Verification:** Uses physics engines as Ground Truth.
    * **Objective Metrics:** Reduces interference from subjective human aesthetics.
</details>
</details>

---

<details>
<summary><b>TiViBench: Think-in-Video Reasoning</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.13704
* **One-liner:** Inspired by Chain-of-Thought in LLMs, this benchmark evaluates "Think-in-Video" capabilities, assessing if models engage in planning-before-generating reasoning processes.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.13704)

> **Core Innovation**
> Current video models are often "intuitive" (mapping text directly to pixels). **TiViBench** promotes and evaluates a new paradigm: **Think-in-Video**. It tests whether models can implicitly or explicitly generate intermediate states (e.g., keyframe sketches, motion flows, or causal logic chains) before the final output. TiViBench designs tasks requiring multi-step reasoning (like "domino effects") to check if "thinking" improves the accuracy of complex dynamic generation.

<details>
    <summary>Abstract</summary>
    Video generation is not just pixel prediction; it requires coherent reasoning about event evolution. TiViBench aims to benchmark the "Think-in-Video" capability of generative models. We define reasoning tasks of varying difficulty, requiring models to demonstrate causal logic in their generation process. By comparing direct generation versus generation with intermediate reasoning steps (e.g., keyframe planning), TiViBench validates the critical role of reasoning in achieving temporal consistency and logical correctness.
</details>

<details>
    <summary>Key points</summary>
    * **Process-Oriented Eval:** Looks at the logic chain behind generation, not just the result.
    * **Causal Deduction:** Focuses on handling Chain Reactions.
    * **Planning vs. Intuition:** Distinguishes between rote memorization and real-time reasoning.
</details>
</details>

---

<details>
<summary><b>Weave: Interleaved Comprehension & Generation</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.11434
* **One-liner:** A comprehensive benchmark for "Interleaved" scenarios (mixed image-text I/O), unlocking and evaluating In-Context Learning capabilities within long multimodal contexts.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.11434)

> **Core Innovation**
> Real-world internet data is often **Interleaved** (e.g., blog posts, slides). **Weave** breaks the boundary of single "Text-to-Image" or "Image-to-Text" tasks, focusing on **Arbitrary Sequences of Mixed Image-Text Streams**. It tests if a model can infer the next "Text 2" or "Image 3" after reading "Image 1 + Text 1 + Image 2." This assesses not just understanding, but specifically **In-Context Learning (ICL)** and style transfer in mixed modalities.

<details>
    <summary>Abstract</summary>
    The future of multimodal interaction lies in fluently handling interleaved text and visual content. Weave is a dataset designed to unleash and benchmark in-context interleaved comprehension and generation. It comprises high-quality image-text sequences constructed from the web, covering storytelling, tutorials, and dialogue. Weave requires models to maintain narrative coherence and visual style consistency over long contexts. Our analysis reveals attention decay issues in current models when handling long interleaved sequences and sets a standard for next-gen native multimodal models.
</details>

<details>
    <summary>Key points</summary>
    * **Interleaved Format:** Simulates real Web/Document reading experiences.
    * **Mixed-Modal ICL:** Tests learning new visual-text patterns from examples.
    * **Bidirectional Test:** Includes both Next-Text Prediction and Next-Image Prediction.
</details>
</details>

---

<details>
<summary><b>Thinking with Video: Video Generation as Reasoning</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.04570
* **One-liner:** Proposes a new paradigm of "Video Generation as Reasoning," arguing that predicting future video frames is essentially a causal reasoning and simulation process of the physical world.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.04570)

> **Core Innovation**
> Reasoning has long been considered the domain of language models. **Thinking with Video** challenges this by proposing that Video Generation Models, by simulating future pixel changes, are effectively performing non-verbal, intuitive physical reasoning. The paper demonstrates that by training models to generate "problem-solving" video sequences (e.g., block stacking, tool use), capabilities akin to planning and counterfactual inference emerge, proving video generation to be a promising multimodal reasoning paradigm.

<details>
    <summary>Abstract</summary>
    We explore the potential of video generation as a general-purpose multimodal reasoning paradigm. Unlike language reasoning which relies on symbolic logic, video generation requires models to internalize physical laws, causality, and object permanence. We demonstrate through a series of complex physical interaction tasks that video generation models exhibit strong reasoning abilities when asked to predict the consequences of actions. We propose the "Thinking with Video" framework, using video prediction as a visual simulation of Chain-of-Thought, significantly improving robot decision-making in complex environments.
</details>

<details>
    <summary>Key points</summary>
    * **Visual Simulation:** Treats generating future frames as a thinking process.
    * **Physical Reasoning:** Validates implicit understanding of gravity, collisions, and fluid dynamics.
    * **Non-verbal CoT:** Shows how visual prediction can replace textual CoT for task planning.
</details>
</details>

---

<details>
<summary><b>V-ReasonBench: Unified Reasoning Suite</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.16668
* **One-liner:** A unified benchmark suite aimed at systematically evaluating the "IQ" of video generation models across temporal logic, causality, and physical consistency.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.16668)

> **Core Innovation**
> Existing video evaluations are often fragmented. **V-ReasonBench** aims to establish a **Unified** reasoning benchmark. Ignoring aesthetic quality, it constructs a test set containing hundreds of logic patterns, ranging from simple object tracking to complex butterfly effects (chain reactions). The benchmark introduces automated "Logic Checkers" capable of determining if generated video content violates basic spatiotemporal logic, serving as the most comprehensive health check for video model logic to date.

<details>
    <summary>Abstract</summary>
    The rapid development of video generation models urgently requires standardized evaluation of their reasoning abilities. V-ReasonBench is a unified reasoning benchmark suite designed to quantify the cognitive capabilities of video generation models. We define a three-tier taxonomy covering temporal logic, causal reasoning, and physical consistency. Through large-scale automated evaluation and human verification, we find that current SOTA models remain fragile when handling long-term dependencies and complex causal chains. V-ReasonBench points the way for next-generation video models with higher logical consistency.
</details>

<details>
    <summary>Key points</summary>
    * **Unified Taxonomy:** Integrates temporal, causal, and physical reasoning tasks.
    * **Logic Checkers:** Introduces programmatic verification to reduce subjective bias.
    * **Long-term Challenge:** Specifically focuses on whether the logic in the latter half of the video is consistent with the first half.
</details>
</details>

---

<details>
<summary><b>GGBench: Geometric Generative Reasoning</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2511.11134
* **One-liner:** A benchmark focused on "Geometric Generative Reasoning," testing whether multimodal models understand spatial transformations, 3D structures, and geometric constraints during generation.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.11134)

> **Core Innovation**
> Many generative models often fail at perspective and geometric structures (e.g., distorted chairs or incorrect reflections). **GGBench** is the first benchmark focused on **Geometric Reasoning**. It requires models to perform tasks such as "generate a 90-degree rotated view of an object," "generate a mirror image," or "combine two objects with specific geometric relations." GGBench reveals that while models can generate realistic textures, they suffer significant deficits in maintaining rigid body geometry and spatial consistency.

<details>
    <summary>Abstract</summary>
    Geometric consistency is the cornerstone of high-quality multimodal generation. GGBench presents a geometric generative reasoning benchmark designed to evaluate unified multimodal models' mastery of spatial structures and geometric transformations. The benchmark covers tasks like 2D geometric transformations, 3D view synthesis, and spatial relationship reasoning. We use precise geometric metrics (e.g., keypoint matching error, pose estimation error) to evaluate results. Experiments show that even top-tier diffusion models often struggle to maintain structural integrity in tasks requiring precise geometric control.
</details>

<details>
    <summary>Key points</summary>
    * **Geometric Rigidity:** Tests if objects deform unnaturally during generation.
    * **Spatial Transformations:** Examines accuracy of rotation, scaling, and mirroring.
    * **Multimodal Alignment:** Verifies if text-described spatial relations are correctly rendered.
</details>
</details>

---

<details>
<summary><b>TempViz: Temporal Knowledge in T2I</b></summary>

* **Authors:** Research Team
* **arXiv ID:** 2601.14951
* **One-liner:** Explores and evaluates the implicit "Temporal Knowledge" in static Text-to-Image (T2I) models, such as understanding historical eras, seasonal changes, motion blur, and the passage of time.
* **Published in:** arXiv 2026
* **Links:** [[Paper]](https://arxiv.org/abs/2601.14951)

> **Core Innovation**
> While images are static, they contain rich temporal information (e.g., "Victorian clothing" or "blur of a speeding car"). **TempViz** is a tool specifically designed to evaluate the **Temporal Knowledge** of T2I models. It tests if models can accurately generate scenes from specific historical periods (Chronological Knowledge), express "speed" and "process" through visual elements (Dynamic Implication), and differentiate between "ancient" and "modern." This is a novel study on how static models encode the fourth dimension.

<details>
    <summary>Abstract</summary>
    Although text-to-image models primarily generate static content, they must possess rich temporal knowledge to produce coherent and context-aware images. TempViz is an evaluation framework for temporal knowledge in T2I models. We construct a dataset across three dimensions: chronological accuracy, implied dynamic motion, and temporal causal snapshots (e.g., shattered glass implying a recent action). Evaluations reveal that while models excel at specific historical details, they show significant bias in expressing abstract passage of time and instantaneous dynamics, often resorting to excessive blur or incorrect physical states.
</details>

<details>
    <summary>Key points</summary>
    * **Chronological Eval:** Tests mastery of visual styles across historical eras.
    * **Implied Motion:** Evaluates how models represent "movement" via static pixels.
    * **Temporal Snapshots:** Examines the distinction between "ongoing" and "post-event" states.
</details>
</details>

---