<p align="center">
  <a href="README.md">English</a> | <a href="README_zh.md">中文</a>
</p>

### Embodied Intelligence Systems

Models designed for robotic control and autonomous agents that must integrate perception, spatial reasoning, and temporal prediction for real-world task execution.

**Key Characteristics:**
- Multimodal instruction following
- 3D spatial navigation and manipulation planning
- Predictive modeling of action consequences

#### Representative Works

<details>
<summary><b>RT-2: Vision-Language-Action Models</b></summary>

* **Authors:** Anthony Brohan, Noah Brown, Justice Carbajal, Yevgen Chebotar, Xi Chen, Krzysztof Choromanski, Tianli Ding, Danny Driess, Avinava Dubey, Chelsea Finn, Pete Florence, Chuyuan Fu, Montse Gonzalez Arenas, Keerthana Gopalakrishnan, Kehang Han, Karol Hausman, Alexander Herzog, Jasmine Hsu, Brian Ichter, Alex Irpan, Nikhil Joshi, Ryan Julian, Dmitry Kalashnikov, Yuheng Kuang, Isabel Leal, Lisa Lee, Tsang-Wei Edward Lee, Sergey Levine, Yao Lu, Henryk Michalewski, Igor Mordatch, Karl Pertsch, Kanishka Rao, Krista Reymann, Michael Ryoo, Grecia Salazar, Pannag Sanketi, Pierre Sermanet, Jaspiar Singh, Anikait Singh, Radu Soricut, Huong Tran, Vincent Vanhoucke, Quan Vuong, Ayzaan Wahid, Stefan Welker, Paul Wohlhart, Jialin Wu, Fei Xia, Ted Xiao, Peng Xu, Sichun Xu, Tianhe Yu, Brianna Zitkovich
* **arXiv ID:** 2307.15818
* **One-liner:** Trains a VLM on web-scale internet data + robot trajectories to map text + images directly to robotic actions for general-purpose real-world manipulation.
* **Published in:** CoRL 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2307.15818) | [[PDF]](https://arxiv.org/pdf/2307.15818.pdf) | [[Project Page]](https://robotics-transformer2.github.io/)

> **Core Innovation**  
> Extends large models from “see and talk” to “see, understand, and act,” pioneering the transfer of internet-scale vision-language knowledge to real-world robotic control, endowing robots with open-world reasoning and zero-shot manipulation capabilities.

<details>
    <summary>Abstract</summary>
    We study how vision-language models trained on Internet-scale data can be incorporated directly into end-to-end robotic control to boost generalization and enable emergent semantic reasoning. Our goal is to enable a single end-to-end trained model to both learn to map robot observations to actions and enjoy the benefits of large-scale pretraining on language and vision-language data from the web. To this end, we propose to co-fine-tune state-of-the-art vision-language models on both robotic trajectory data and Internet-scale vision-language tasks, such as visual question answering. In contrast to other approaches, we propose a simple, general recipe to achieve this goal: in order to fit both natural language responses and robotic actions into the same format, we express the actions as text tokens and incorporate them directly into the training set of the model in the same way as natural language tokens. We refer to such category of models as vision-language-action models (VLA) and instantiate an example of such a model, which we call RT-2. Our extensive evaluation (6k evaluation trials) shows that our approach leads to performant robotic policies and enables RT-2 to obtain a range of emergent capabilities from Internet-scale training. This includes significantly improved generalization to novel objects, the ability to interpret commands not present in the robot training data (such as placing an object onto a particular number or icon), and the ability to perform rudimentary reasoning in response to user commands (such as picking up the smallest or largest object, or the one closest to another object). We further show that incorporating chain of thought reasoning allows RT-2 to perform multi-stage semantic reasoning, for example figuring out which object to pick up for use as an improvised hammer (a rock), or which type of drink is best suited for someone who is tired (an energy drink).
</details>

<details>
    <summary>Key points</summary>
    * Extends LLM/VLM foundation modeling to robot control
    * Trained on *internet vision-language data + robot action data*
    * Outputs robotic action tokens
    * Strong zero-shot generalization to new objects, tasks, environment changes
</details>
</details>

---

<details>
<summary><b>GAIA-1: A Generative World Model for Autonomous Driving</b></summary>

* **Authors:** Anthony Hu, Lloyd Russell, Hudson Yeo, Zak Murez, George Fedoseev, Alex Kendall, Jamie Shotton, Gianluca Corrado
* **arXiv ID:** 2311.07541
* **One-liner:** A large-scale generative world model that simulates diverse driving scenarios and predicts future multi-agent behavior for closed-loop autonomous driving.
* **Published in:** arXiv 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2309.17080) | [[PDF]](https://arxiv.org/pdf/2309.17080.pdf)

> **Core Innovation**  
> Beyond trajectory forecasting, it learns “world evolution” itself—simultaneously generating multi-agent dynamics, realistic traffic behaviors, and authentic sensor signals for closed-loop simulation and synthesis of rare safety-critical scenarios.

<details>
    <summary>Abstract</summary>
    Autonomous driving promises transformative improvements to transportation, but building systems capable of safely navigating the unstructured complexity of real-world scenarios remains challenging. A critical problem lies in effectively predicting the various potential outcomes that may emerge in response to the vehicle's actions as the world evolves.
    To address this challenge, we introduce GAIA-1 ('Generative AI for Autonomy'), a generative world model that leverages video, text, and action inputs to generate realistic driving scenarios while offering fine-grained control over ego-vehicle behavior and scene features. Our approach casts world modeling as an unsupervised sequence modeling problem by mapping the inputs to discrete tokens, and predicting the next token in the sequence. Emerging properties from our model include learning high-level structures and scene dynamics, contextual awareness, generalization, and understanding of geometry. The power of GAIA-1's learned representation that captures expectations of future events, combined with its ability to generate realistic samples, provides new possibilities for innovation in the field of autonomy, enabling enhanced and accelerated training of autonomous driving technology.
</details>

<details>
    <summary>Key points</summary>
    * Generative world model for driving — not just trajectory prediction
    * Generates future agent motion, scene geometry, and sensor data
    * Closed-loop simulation for AD evaluation + training
    * Enables rare / edge-case generation for safety
</details>
</details>

---

<details>
<summary><b>PaLM-E: An Embodied Multimodal Language Model</b></summary>

* **Authors:** Danny Driess, Fei Xia, Mehdi S. M. Sajjadi, Corey Lynch, Aakanksha Chowdhery, Brian Ichter, Ayzaan Wahid, Jonathan Tompson, Quan Vuong, Tianhe Yu, Wenlong Huang, Yevgen Chebotar, Pierre Sermanet, Daniel Duckworth, Sergey Levine, Vincent Vanhoucke, Karol Hausman, Marc Toussaint, Klaus Greff, Andy Zeng, Igor Mordatch, Pete Florence
* **arXiv ID:** 2303.03378
* **One-liner:** Multimodal LLM that integrates real-world sensor inputs (vision, robotics state) into PaLM, enabling robotic reasoning and action planning.
* **Published in:** ICLR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2303.03378) | [[PDF]](https://arxiv.org/pdf/2303.03378.pdf) | [[Project Page]](https://palm-e.github.io/)

> **Core Innovation**  
> Treats robot vision and state information as “tokens” fed into an LLM, turning the language model into an embodied-intelligence decision system that can understand the environment, plan actions, and execute tasks.

<details>
    <summary>Abstract</summary>
    Large language models excel at a wide range of complex tasks. However, enabling general inference in the real world, e.g., for robotics problems, raises the challenge of grounding. We propose embodied language models to directly incorporate real-world continuous sensor modalities into language models and thereby establish the link between words and percepts. Input to our embodied language model are multi-modal sentences that interleave visual, continuous state estimation, and textual input encodings. We train these encodings end-to-end, in conjunction with a pre-trained large language model, for multiple embodied tasks including sequential robotic manipulation planning, visual question answering, and captioning. Our evaluations show that PaLM-E, a single large embodied multimodal model, can address a variety of embodied reasoning tasks, from a variety of observation modalities, on multiple embodiments, and further, exhibits positive transfer: the model benefits from diverse joint training across internet-scale language, vision, and visual-language domains. Our largest model, PaLM-E-562B with 562B parameters, in addition to being trained on robotics tasks, is a visual-language generalist with state-of-the-art performance on OK-VQA, and retains generalist language capabilities with increasing scale.
</details>

<details>
    <summary>Key points</summary>
    * Embodied LLM combining robot sensor tokens + language
    * Joint vision-robot-language pretraining improves generalization
    * Handles long-horizon task reasoning and grounding
    * Builds toward unified *robotics-LLM world models*
</details>
</details>

---

<details>
<summary><b>Genie 3: General-Purpose World Model</b></summary>

* **Authors:** Google DeepMind Team
* **arXiv ID:** 2508.xxxxx (August 2025 Release)
* **One-liner:** A general-purpose world model achieving real-time 720p/24fps generation with infinite exploration and complex text-to-environment interaction.
* **Published in:** Google DeepMind Research / arXiv 2025
* **Links:** [[Blog]](https://deepmind.google/models/genie-3) | [[Paper]](https://arxiv.org/abs/2508.xxxxx)

> **Core Innovation**
> Compared to the original Genie (2024), which was limited to low-res 2D platformers, **Genie 3** is a massive leap. It generates **photorealistic** 3D-style environments. The core breakthrough lies in its optimized **auto-regressive architecture**, enabling **24fps** generation at **720p** resolution. Crucially, it features **Persistent Memory**—objects and layouts remain consistent even after the camera looks away and returns. It also introduces **Promptable World Events**, allowing users to modify the simulation on the fly via natural language (e.g., "start a thunderstorm").

<details>
    <summary>Abstract (Reconstructed)</summary>
    We present Genie 3, a general-purpose world model capable of generating dynamic, interactive environments from simple text descriptions. Unlike its predecessors, Genie 3 achieves real-time generation at 720p resolution and 24fps, while maintaining temporal consistency over minutes. The model exhibits emergent object permanence and allows for real-time modification of environmental states via natural language. Genie 3 serves as an infinite simulation ground for training embodied agents without manual asset creation.
</details>

<details>
    <summary>Key points</summary>
    * **Real-Time Interaction:** The first HD world model to achieve playable frame rates (24fps).
    * **Object Permanence:** Solves the common issue of objects vanishing or morphing in video generation.
    * **Agent Training Ground:** Designed as a training environment for generalist agents like SIMA.
</details>
</details>

---

<details>
<summary><b>Matrix-Game 2.0: Open-Source Interactive World Model</b></summary>

* **Authors:** Skywork AI Team
* **arXiv ID:** 2508.13009
* **One-liner:** The first open-source world model to support real-time streaming interaction, generating minute-long high-quality videos at 25 FPS, breaking the monopoly of closed-source models.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2508.13009) | [[GitHub]](https://github.com/SkyworkAI/Matrix-Game)

> **Core Innovation**
> Addressing the issues of slow inference and closed nature of existing world models, Skywork AI released **Matrix-Game 2.0**. It proposes an efficient **Streaming Inference Architecture** capable of translating user inputs into video feedback with minimal latency. Similar to Genie 3, it achieves a smooth **25 FPS**, but its key differentiator is being **Fully Open Source** (Open Weights). The model excels in diverse game scenarios and physical simulations, proving that high-performance real-time interactive world models can be trained without Google-scale resources.

<details>
    <summary>Abstract</summary>
    We introduce Matrix-Game 2.0, an open-source real-time and streaming interactive world model. Addressing bottlenecks in long-sequence consistency and inference speed, we design a novel streaming architecture. Matrix-Game 2.0 generates high-quality, minute-level videos at 25 FPS on consumer hardware, responding instantly to user keypress inputs. We release the model weights and code to foster research in the interactive world model community.
</details>

<details>
    <summary>Key points</summary>
    * **Streaming Interaction:** Ultra-low input-output latency, suitable for real-time game simulation.
    * **Open Source SOTA:** Provides reproducible code and weights, becoming a primary base for academic research.
    * **Efficient Inference:** Optimized attention mechanisms allow long-sequence generation on limited VRAM.
</details>
</details>

---

<details>
<summary><b>HunyuanWorld 1.0: 3D World Generation</b></summary>

* **Authors:** Tencent Hunyuan Team
* **arXiv ID:** 2507.21809
* **One-liner:** Tencent's 3D world generation model, capable of generating free-roaming, immersive 360° 3D scenes directly from single images or text via "Panoramic Proxy" technology.
* **Published in:** arXiv 2025 / GitHub
* **Links:** [[Paper]](https://arxiv.org/abs/2507.21809) | [[Project]](https://github.com/Tencent-Hunyuan/HunyuanWorld-1.0)

> **Core Innovation**
> Unlike "World Models" that generate video, **HunyuanWorld 1.0** focuses on generating **true 3D spaces**. While traditional 3D generation is limited to single objects, HunyuanWorld targets **Scene-scale** generation. It introduces **Panoramic World Proxies**, first generating highly consistent panoramas, then converting them into exportable Meshes or Gaussian Splats via hierarchical 3D reconstruction. This allows users to input a sentence and get a 3D world they can walk into (VR-ready), at a very low cost (~$0.30/gen).

<details>
    <summary>Abstract</summary>
    We present HunyuanWorld 1.0, a novel framework for generating immersive, explorable, and interactive 3D scenes from text and image conditions. Our approach leverages panoramic proxy generation and semantic layered reconstruction to achieve high-quality scene-scale 360° 3D world generation. The model supports mesh export, seamless compatibility with existing CG pipelines, offering an efficient tool for game development and metaverse content creation.
</details>

<details>
    <summary>Key points</summary>
    * **Scene-Scale Generation:** Breaks the limit of single-object generation to build complete environments.
    * **Panoramic Proxy:** Uses the power of 2D diffusion models to guide 3D structure construction.
    * **Explorability:** The output is not a static image but a navigable 3D asset supporting free viewing angles.
</details>
</details>

---

<details>
<summary><b>Cosmos: World Foundation Model Platform for Physical AI</b></summary>

* **Authors:** NVIDIA Research (Niket Agarwal, et al.)
* **arXiv ID:** 2501.03575
* **One-liner:** NVIDIA's foundation platform specifically for "Physical AI," comprising Cosmos Predict, Transfer, and Reason; the cornerstone for digital twins in robotics and autonomous driving.
* **Published in:** arXiv 2025 / CES 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2501.03575) | [[Website]](https://www.nvidia.com/en-us/ai/cosmos/)

> **Core Innovation**
> **Cosmos** is not just a model, but a **World Foundation Model Platform**. NVIDIA posits that Physical AI (robots, AVs) must be trained in digital twins first. Cosmos provides high-quality pretrained models: **Cosmos Predict** forecasts future physical states (video generation); **Cosmos Reason** understands complex physics and causality. It utilizes a hybrid tokenizer/transformer architecture, emphasizing strict adherence to **physical laws** (gravity, collision, friction) over mere visual aesthetics.

<details>
    <summary>Abstract</summary>
    Physical AI needs to be trained digitally first. We present the Cosmos World Foundation Model Platform to help developers build customized world models. Cosmos includes a suite of diffusion and autoregressive transformer models trained on millions of hours of video. It serves as a general-purpose world simulator for video prediction, synthetic data generation, and physical reasoning. We open-source the weights and pipelines to address data scarcity and simulation gaps in Physical AI.
</details>

<details>
    <summary>Key points</summary>
    * **Physical Consistency:** Prioritizes accurate physics over visuals (unlike Sora), designed for robot training.
    * **Modular Design:** Divided into Predict, Transfer, and Reason modules.
    * **Open Ecosystem:** NVIDIA open-sourced weights, making it the standard for industrial Sim-to-Real systems.
</details>
</details>

---

<details>
<summary><b>UniAD: Planning-oriented Autonomous Driving</b></summary>

* **Authors:** Yihan Hu, et al. (OpenDriveLab / SenseTime)
* **arXiv ID:** 2212.10156
* **One-liner:** CVPR 2023 Best Paper; the first End-to-End autonomous driving model integrating perception, prediction, and planning into a unified Transformer, pioneering the "World Model" approach in AD.
* **Published in:** CVPR 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2212.10156) | [[Project]](https://github.com/OpenDriveLab/UniAD)

> **Core Innovation**
> Before **UniAD**, autonomous driving was typically modular (Perception -> Prediction -> Planning), suffering from information loss and lack of joint optimization. UniAD proposed a **Planning-oriented** unified architecture. It connects detection, tracking, mapping, prediction, and planning via a **Query** mechanism, where queries from one stage feed into the next. Effectively, this builds a **predictive world model** of the driving scene; the model doesn't just "see" the road, but predicts the future trajectories of all surrounding agents and their impact on the ego-vehicle, enabling more human-like decision-making.

<details>
    <summary>Abstract</summary>
    Modern autonomous driving systems are characterized as modular tasks in sequential order. We introduce UniAD, a comprehensive framework incorporating full-stack driving tasks in one network. UniAD leverages unified query interfaces to facilitate communication between tasks towards planning. Evaluated on the nuScenes benchmark, UniAD substantially outperforms previous SOTAs in all aspects, proving that this planning-oriented philosophy enhances not just perception but significantly improves planning safety and human-likeness.
</details>

<details>
    <summary>Key points</summary>
    * **Unified Query Interface:** Solves feature misalignment between different modules.
    * **End-to-End Optimization:** The entire network is jointly trained with losses focused on prediction and final planning.
    * **Interactive Prediction:** Implicitly learns the game-theoretic interactions between the ego-vehicle and others.
</details>
</details>

---

<details>
<summary><b>V-JEPA: Non-Generative World Model</b></summary>

* **Authors:** Meta FAIR (Yann LeCun, et al.)
* **arXiv ID:** 2404.08471
* **One-liner:** The embodiment of LeCun's "World Model" vision—understanding the world by predicting abstract features rather than generating pixels, achieving high efficiency and strong representation.
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2404.08471) | [[Blog]](https://ai.meta.com/blog/v-jepa-yann-lecun-ai-model-video-joint-embedding-predictive-architecture/)

> **Core Innovation**
> Unlike "generative" world models like Sora or Hunyuan, **V-JEPA** represents LeCun's **Joint Embedding Predictive Architecture (JEPA)** path. It posits that generating every pixel is wasteful and unnecessary (as the world is full of stochastic details). V-JEPA predicts in **Latent Space**: it masks spatiotemporal regions of a video and trains the model to predict the abstract features of those regions. This forces the model to ignore irrelevant visual details (like random leaf movement) and focus on high-level semantics of motion and physics, offering training efficiency orders of magnitude higher than generative models.

<details>
    <summary>Abstract</summary>
    We propose V-JEPA, a method for self-supervised video representation learning. V-JEPA is based on the Joint Embedding Predictive Architecture, learning by predicting missing parts of a video in latent space. Unlike generative methods, V-JEPA does not reconstruct pixels but predicts abstract embeddings. We train V-JEPA on large-scale video datasets, demonstrating superior performance on downstream image and video tasks (e.g., action recognition) with significantly higher training efficiency than pixel-generation models.
</details>

<details>
    <summary>Key points</summary>
    * **Non-Generative:** Predicts features, not pixels, avoiding hallucinations and computational waste.
    * **Semantic Focus:** Forces the model to learn high-level semantics over low-level textures.
    * **Efficient Scaling:** High computational efficiency allows scaling to massive model sizes.
</details>
</details>

---

<details>
<summary><b>DreamerV3: General RL World Model</b></summary>

* **Authors:** Danijar Hafner, et al. (DeepMind / UofT)
* **arXiv ID:** 2301.04104
* **One-liner:** A milestone in RL; the first algorithm to achieve SOTA across diverse domains (Minecraft, Atari, Robotics) with a single set of fixed hyperparameters using a World Model.
* **Published in:** ICLR 2024 / arXiv 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2301.04104) | [[Project]](https://danijar.com/project/dreamerv3/)

> **Core Innovation**
> **DreamerV3** solves the brittleness of Model-Based Reinforcement Learning (MBRL). Previous models required extensive tuning for different tasks. DreamerV3 introduces **Symlog transformation** to handle rewards of vastly different magnitudes and robust normalization techniques. This allows it to learn to **collect diamonds in Minecraft** from scratch (previously only possible with imitation learning) without changing a single line of code or hyperparameter, while also beating specialized algorithms on Atari and control tasks.

<details>
    <summary>Abstract</summary>
    General intelligence requires algorithms that master diverse domains. We introduce DreamerV3, a scalable algorithm based on world models that outperforms previous approaches across a wide range of domains with fixed hyperparameters. DreamerV3 learns a discrete world model and trains an actor-critic policy in imagination. Using Symlog predictions and robust normalization, DreamerV3 becomes the first algorithm to collect diamonds in Minecraft without human data, mastering hundreds of other tasks.
</details>

<details>
    <summary>Key points</summary>
    * **Generality:** One set of parameters for all tasks, solving RL's hyperparameter sensitivity.
    * **Symlog Prediction:** Elegantly handles numerical scales from tiny to massive.
    * **Minecraft Breakthrough:** Proves that pure exploration and world models can solve complex, long-horizon tasks.
</details>
</details>

---

<details>
<summary><b>WorldVLA: Unified Action-World Model</b></summary>

* **Authors:** DAMO Academy, Alibaba Group (Jun Cen, et al.)
* **arXiv ID:** 2506.21539
* **One-liner:** A unified framework from Alibaba breaking the boundary between "World Models" and "Action Models," proving that action generation and video prediction mutually enhance each other.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2506.21539)

> **Core Innovation**
> Existing embodied AI models typically separate VLA (Vision-Language-Action) from World Models. **WorldVLA** proposes an **Autoregressive Action World Model**. It performs two tasks simultaneously within a single Transformer: 1) The **World Model** predicts future images using actions (learning physics); 2) The **Action Model** generates actions based on observations. The study reveals a significant **Mutual Enhancement**: a model that understands physics generates better actions, and a model that knows how to act predicts better videos.

<details>
    <summary>Abstract</summary>
    Existing VLA models lack deep understanding of the relation between actions and environmental dynamics. We present WorldVLA, a world model that unifies action and image generation. WorldVLA predicts future frames by leveraging action and image understanding to learn underlying physics, while simultaneously generating subsequent actions based on observations. Experiments show WorldVLA outperforms standalone models in both tasks, highlighting the synergistic enhancement between World Models and VLA.
</details>

<details>
    <summary>Key points</summary>
    * **Unified Architecture:** Treats Video Generation and Action Prediction as a unified sequence modeling problem.
    * **Mutual Enhancement:** Proves "predicting the future" aids "current decision making" and vice-versa.
    * **Physical Consistency:** Generates actions more compliant with physical constraints compared to pure VLAs.
</details>
</details>

---

<details>
<summary><b>LingBot-World: Open-Source Interactive Simulator</b></summary>

* **Authors:** Robbyant Team (Ka Leong Cheng, et al.)
* **arXiv ID:** 2601.20540 (Jan 2026)
* **One-liner:** A 2026 open-source milestone achieving **minute-level** long-term memory and **real-time** interaction, bridging the gap between open-source and proprietary (e.g., Google Genie 3) models.
* **Published in:** arXiv 2026
* **Links:** [[Paper]](https://arxiv.org/abs/2601.20540) | [[Code]](https://github.com/Robbyant/LingBot-World)

> **Core Innovation**
> Addressing the common issues of "short-term memory" (scenes collapsing after seconds) and "high latency" in world models, **LingBot-World** offers a novel solution. As the core of Robbyant's LingBot series, it supports **High-Fidelity** dynamics and achieves **Minute-Level Temporal Consistency**. Crucially, it is optimized for inference speed, achieving **<1s latency** on consumer hardware. This makes it the first truly usable open-source real-time world simulator for gaming, content creation, and robot training.

<details>
    <summary>Abstract</summary>
    We present LingBot-World, an open-sourced world simulator stemming from video generation. Positioned as a top-tier world model, LingBot-World offers three core features: (1) It maintains high fidelity and robust dynamics across diverse environments (realism, scientific, cartoon); (2) It enables a minute-level horizon while preserving contextual consistency (long-term memory); (3) It supports real-time interactivity, achieving a latency of under 1 second at 16fps. We release the code and model to narrow the divide between open and closed-source technologies.
</details>

<details>
    <summary>Key points</summary>
    * **Minute-Level Consistency:** Breaks the bottleneck where existing models fail after a few seconds.
    * **Real-Time Low Latency:** Optimized inference pipeline allowing for real-time human interaction.
    * **Fully Open Source:** Provides full training/inference code, a key asset for the community in early 2026.
</details>
</details>

---

<details>
<summary><b>3D-VLA: 3D Generative World Model</b></summary>

* **Authors:** Chuang Gan, et al. (UMass Amherst / MIT-IBM Watson)
* **arXiv ID:** 2403.09631
* **One-liner:** Introduces "Generative World Models" to 3D Embodied AI; capable of **imagining** future point clouds and depth changes to plan precise robotic actions.
* **Published in:** ICML 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2403.09631) | [[Project]](https://vis-www.cs.umass.edu/3d-vla/)

> **Core Innovation**
> Traditional VLA models (like RT-2) rely on 2D images, lacking spatial depth, which limits performance in complex 3D manipulation. **3D-VLA** introduces a **3D LLM** architecture, injecting 3D positional information into interaction tokens. Its key innovation is a **Generative World Model** that generates **future 3D Point Clouds and Depth Maps** instead of just pixels. This allows the robot to simulate the 3D state of objects after manipulation in its "mind" before acting, significantly improving planning success rates.

<details>
    <summary>Abstract</summary>
    Recent VLA models rely on 2D inputs, lacking integration with the 3D physical world. We propose 3D-VLA, linking 3D perception, reasoning, and action through a generative world model. Built on top of a 3D-LLM, it introduces interaction tokens. Trained on a large-scale 3D embodied instruction dataset, 3D-VLA demonstrates superior capabilities in 3D reasoning, multimodal goal generation (images, depth, point clouds), and action planning. The generative world model allows the robot to predict the 3D effects of its actions.
</details>

<details>
    <summary>Key points</summary>
    * **3D Imagination:** Generates future 3D geometry (point clouds), not just 2D pixels.
    * **Spatial Reasoning:** Overcomes the inherent spatial limitations of 2D VLMs.
    * **Data Pipeline:** Proposes a pipeline to extract 3D information from existing robotics datasets.
</details>
</details>

---

<details>
<summary><b>DriveVLM: VLM for Autonomous Driving</b></summary>

* **Authors:** Tsinghua University / Li Auto
* **arXiv ID:** 2402.12289
* **One-liner:** Explores the potential of VLMs in autonomous driving, utilizing **Chain-of-Thought (CoT)** reasoning to handle long-tail scenarios and complex interactions, accompanied by the SUP-AD dataset.
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2402.12289) | [[Project]](https://tsinghua-mars-lab.github.io/DriveVLM/)

> **Core Innovation**
> Traditional AD systems are often "black boxes" or rule-based, struggling with corner cases (e.g., strange animals or complex gestures). **DriveVLM** leverages the commonsense reasoning of Large Vision-Language Models. Instead of directly outputting control, it performs **Scene Description**, then **Scene Analysis**, and finally **Hierarchical Planning**. This human-like **Chain-of-Thought (CoT)** makes decisions transparent and robust. To address latency, it introduces **DriveVLM-Dual**, combining slow VLM reasoning with a fast traditional AD pipeline.

<details>
    <summary>Abstract</summary>
    Autonomous driving requires not just perception but understanding and reasoning about complex scenes. We propose DriveVLM, an AD system leveraging VLMs for scene understanding and planning. We design a Chain-of-Thought (CoT) mechanism to mimic human decision-making via description, analysis, and planning. Furthermore, we propose DriveVLM-Dual, a hybrid system synergizing traditional planners with VLMs to ensure real-time performance. We also release the SUP-AD dataset to facilitate research.
</details>

<details>
    <summary>Key points</summary>
    * **CoT Driving:** Decomposes driving into logical reasoning steps, improving interpretability.
    * **Dual System:** Solves the engineering challenge of high latency in large models.
    * **Long-tail Handling:** Uses VLM world knowledge to effectively handle rare and complex traffic scenarios.
</details>
</details>

---