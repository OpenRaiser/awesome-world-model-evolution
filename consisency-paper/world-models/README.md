<p align="center">
  <a href="README.md">English</a> | <a href="README_zh.md">中文</a>
</p>

### Text-to-World Generators

Models that generate dynamic, spatially consistent virtual environments from language descriptions.

**Key Characteristics:**
- ✅ Modality: Natural language understanding and pixel-space generation
- ✅ Spatial: 3D-aware scene composition with object permanence
- ✅ Temporal: Physically plausible dynamics and motion

#### Representative Works

<details>
<summary><b>OpenAI Sora</b></summary>

* **Authors:** OpenAI Research Team
* **Model:** Sora (2024)
* **One-liner:** A large-scale space-time generative model that treats videos as sequences of visual patches, enabling high-fidelity text-to-video, image-to-video, and video editing.
* **Published in:** 2024 (open release)
* **Links:** [[Model Page]](https://openai.com/sora) | [[Technical Overview]](https://openai.com/index/video-generation-models-as-world-simulators/)

> **Core Innovation**  
> Sora introduces a large-scale universal generative model that treats visual data (e.g., videos) as “patches,” supporting multiple input modalities (text, images, videos) and outputting new videos with flexible durations, resolutions, and aspect ratios.

<details>
    <summary>Abstract</summary>
    Sora is a general visual generation model capable of synthesizing videos and images across diverse durations, resolutions, and aspect ratios. It leverages a spatiotemporal representation of visual data and trains on patches, similar to token-based language models. Sora supports flexible conditioning (text, image, video) and demonstrates strong temporal coherence, physical realism, and camera motion control, pointing toward scalable video models as world simulators.
</details>

<details>
    <summary>Key points</summary>
    * Treats video as patch-based latent sequences (analogous to tokenization in LLMs)  
    * Unified model for video & image generation across resolutions and durations  
    * Strong physical consistency and camera control  
    * Supports text → video, image → video, video editing, and stylization  
</details>
</details>

---

<details>
<summary><b>Open-Sora: Democratizing Efficient Video Production for All</b></summary>

* **Authors:** HPC-AI Tech Team (Colossal-AI)
* **arXiv ID:** 2412.20404 (v1.2/v2 Report)
* **One-liner:** An open-source initiative to replicate Sora, drastically reducing training costs via ST-DiT architecture and efficient strategies like dynamic resolution loading.
* **Published in:** arXiv 2024 / GitHub
* **Links:** [[Paper]](https://arxiv.org/abs/2412.20404) | [[Project]](https://github.com/hpcaitech/Open-Sora)

> **Core Innovation**
> Since OpenAI kept Sora closed, **Open-Sora** aims to fill the gap. It focuses not just on replication but on **Training Efficiency** and **Democratization**. It employs **ST-DiT (Spatiotemporal DiT)**, decoupling spatial and temporal attention to reduce complexity. Open-Sora introduces Dynamic Resolution Loading and a multi-stage training strategy (image pretraining to video finetuning), successfully training coherent video models at a fraction of the cost (e.g., $200k range). The latest versions optimize 3D VAEs and Flow Matching strategies further.

<details>
    <summary>Abstract</summary>
    To facilitate the development of visual intelligence, we present Open-Sora, an open-source initiative dedicated to efficiently producing high-quality video. We propose an architecture based on ST-DiT and implement various system optimizations to support dynamic resolutions and long-sequence training. By open-sourcing weights, code, and data pipelines, we demonstrate that training top-tier video models is accessible, significantly lowering the barrier to entry.
</details>

<details>
    <summary>Key points</summary>
    * **ST-DiT Architecture:** Serializes spatial and temporal attention, saving memory compared to full 3D attention.
    * **Cost-Efficiency:** Proves high-performance models can be trained on a budget via data curation and multi-stage training.
    * **Full-Stack Open Source:** Provides the complete pipeline from data cleaning and VAE training to DiT training.
</details>
</details>

---

<details>
<summary><b>Runway Gen-3 Alpha</b></summary>

* **Authors:** Runway Research Team
* **Model:** Gen-3 Alpha (2024)
* **One-liner:** Next-generation multimodal video foundation model with improved motion realism, fidelity, and controllability over Gen-2.
* **Published in:** 2024 (Alpha)
* **Links:** [[Model Page]](https://runwayml.com/research/introducing-gen-3-alpha)

> **Core Innovation**  
> Gen-3 Alpha is built on a brand-new, large-scale multimodal training infrastructure that accepts text, image, and video inputs, delivering superior motion fidelity, structural consistency, and controllability.

<details>
    <summary>Abstract</summary>
    Gen-3 Alpha is a new multimodal video generation model built on a scalable training stack designed for high-fidelity, controllable visual synthesis. It supports text-to-video, image-to-video, and hybrid creative workflows with strong temporal stability, realistic motion, and cinematic quality. The system introduces new control tools such as Motion Brush and camera path control for creator-centric video production.
</details>

<details>
    <summary>Key points</summary>
    * Text-to-video, image-to-video, and mixed creative inputs  
    * Enhanced motion, consistency, and cinematic realism vs. Gen-2  
    * New control tools (Motion Brush, camera path control)  
    * Designed for professional film & creator workflows  
</details>
</details>

---

<details>
<summary><b>Pika 1.0</b></summary>

* **Authors:** Pika Labs Team
* **Model:** Pika 1.0 (2023)
* **One-liner:** A user-friendly generative video platform supporting text-to-video, image-to-video, and video editing with multiple artistic and cinematic styles.
* **Published in:** 2023 (November)
* **Links:** [[Product Page]](https://pika.art/) | [[Launch Blog]](https://pika.art/blog)

> **Core Innovation**  
> Pika 1.0 democratizes video generation and editing: accessible via Web and Discord, it lets users create videos from text or images and edit existing footage in a wide range of visual styles.

<details>
    <summary>Abstract</summary>
    Pika 1.0 introduces a generative video model embedded in a web-based creation platform. It supports multi-style video synthesis (3D animation, anime, cinematic, cartoon) and allows users to animate images, edit video clips, and generate scenes through natural prompts. With an emphasis on accessibility and fast iteration, Pika aims to democratize AI-powered video creation for everyday creative workflows.
</details>

<details>
    <summary>Key points</summary>
    * Text-to-video, image-to-video, and video editing  
    * Multiple stylistic modes (3D, anime, cinematic, cartoon)  
    * Web UI + Discord integration for accessible creation  
    * Consumer-focused, fast iteration and community-driven growth  
</details>
</details>

---

<details>
<summary><b>CogVideoX: Text-to-Video Diffusion Models with An Expert Transformer</b></summary>

* **Authors:** Zhipu AI (THUDM)
* **arXiv ID:** 2408.06072
* **One-liner:** Proposes an efficient architecture based on "3D Causal VAE" and "Expert Transformer," achieving compact and highly aligned video generation with reduced latent dimensions.
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2408.06072) | [[Project]](https://github.com/THUDM/CogVideo)

> **Core Innovation**
> Many video models struggle with massive memory costs. **CogVideoX** breaks through with its highly efficient **3D Causal VAE**. It compresses video aggressively across both spatial and temporal dimensions (e.g., 4x4x4), significantly reducing the token count for the DiT. Furthermore, to address text-video alignment, it introduces an **Expert Transformer** with **Expert Adaptive LayerNorm**, specifically designed to fuse the two modalities. This allows CogVideoX to generate videos with high prompt adherence and fluid motion even with smaller parameter counts (e.g., 2B/5B).

<details>
    <summary>Abstract</summary>
    We introduce CogVideoX, a large-scale text-to-video generation model. To efficiently model video data, we leverage a 3D Variational Autoencoder (VAE) to compress videos along spatial and temporal dimensions. To improve text-video alignment, we propose an expert transformer with expert adaptive LayerNorm to facilitate deep fusion between modalities. Employing progressive training techniques, CogVideoX excels at producing coherent, long-duration videos with significant motion, demonstrating state-of-the-art performance on multiple benchmarks.
</details>

<details>
    <summary>Key points</summary>
    * **3D Causal VAE:** The key component for efficient spatiotemporal compression, reducing sequence length.
    * **Expert Transformer:** Enhances prompt understanding via adaptive normalization layers.
    * **3D RoPE:** Uses 3D Rotary Positional Encoding to better capture spatiotemporal relationships.
</details>
</details>

---

<details>
<summary><b>Wan 2.2 (Wan-Video): Mixture-of-Experts for Video Generation</b></summary>

* **Authors:** Alibaba Group (Tongyi Wanxiang Team)
* **arXiv ID:** 25xx.xxxxx (Referencing the Wan 2.1/2.2 Technical Report)
* **One-liner:** The first SOTA open-source model to integrate **Mixture-of-Experts (MoE)** into video diffusion, massively scaling capacity (27B params) without sacrificing inference speed, surpassing Sora/Gen-3 in complex motion.
* **Published in:** arXiv 2025
* **Links:** [[Project]](https://github.com/Wan-Video/Wan2.1)

> **Core Innovation**
> While Wan 2.1 was powerful, **Wan 2.2** introduces a fundamental architectural shift: **Mixture-of-Experts (MoE)**. Traditional video DiTs slow down as parameters grow. Wan 2.2 uses an MoE architecture with 27B total parameters but only ~14B active during inference. This scales model capacity significantly without increasing computational cost. Combined with its robust **Wan-VAE** (supporting 1080P infinite length encoding) and massive data scale (80% more video data than its predecessor), Wan 2.2 solves the common issues of "small motion" and "physics collapse," generating cinematic, large-motion sequences.

<details>
    <summary>Abstract (Reconstructed)</summary>
    We present Wan 2.2, the latest iteration of the Wan video generation suite. Wan 2.2 incorporates a Mixture-of-Experts (MoE) architecture, distributing the denoising process across specialized experts to enlarge model capacity while maintaining computational efficiency. Trained on a massive dataset of aesthetics and motion, Wan 2.2 demonstrates superior performance in generating complex motions, cinematic lighting, and long-term consistency. Our models outperform existing closed-source models (e.g., Gen-3, Sora) on multiple benchmarks.
</details>

<details>
    <summary>Key points</summary>
    * **Video MoE Architecture:** First large-scale application of MoE in video generation, balancing massive parameters with speed.
    * **Wan-VAE:** Exceptionally strong 3D compression supporting arbitrary aspect ratios and durations.
    * **Data Scale:** Near doubling of training data compared to v2.1, significantly boosting generalization.
</details>
</details>

---

<details>
<summary><b>HailuoAI (MiniMax Video-01)</b></summary>

* **Authors:** MiniMax Team
* **arXiv ID:** N/A (Proprietary Service)
* **One-liner:** A "Sora-level" video generation service from Chinese unicorn MiniMax, known for exceptional prompt adherence, native sound generation, and long-duration coherence.
* **Published in:** Product Release (Sep 2024)
* **Links:** [[Website]](https://hailuoai.com/video) | [[Tech Blog]](https://www.minimaxi.com/)

> **Core Innovation**
> Emerging as a dark horse alongside Runway and Luma AI, **HailuoAI (MiniMax)** utilizes a massive **DiT (Diffusion Transformer)** architecture. Its key differentiator is its superior **Instruction Following** capability (e.g., precise lighting changes, object morphing) and **Motion Fluidity**. It significantly mitigates common "collapse" and "flickering" issues found in earlier models. Being one of the first to support **native high frame rates** and **text-to-sound effects**, it is widely regarded as the strongest closed-source video model in the Chinese market.

<details>
    <summary>Abstract (Product Description)</summary>
    HailuoAI is a revolutionary video generation tool launched by MiniMax. Powered by our proprietary Video-01 model, it transforms text prompts into high-definition, high-frame-rate cinematic videos in seconds. The model achieves major breakthroughs in semantic understanding, motion coherence, and visual detail, supporting styles from photorealism to anime. It aims to provide creators with a virtual production experience without the need for expensive equipment.
</details>

<details>
    <summary>Key points</summary>
    * **Superior Semantic Alignment:** Accurately understands complex prompts, including cinematic language and physical interactions.
    * **High Dynamic Range:** Generates videos with large, fluid motions, avoiding the "slideshow effect."
    * **Ecosystem Integration:** Leverages MiniMax's strong audio tech for integrated video dubbing and sound effects.
</details>
</details>

---

<details>
<summary><b>HunyuanVideo: Open-Source SOTA Video Generation</b></summary>

* **Authors:** Tencent Hunyuan Team
* **arXiv ID:** 2412.03603
* **One-liner:** The reigning champion of open-source video generation, featuring a unified DiT architecture and 3D VAE, supporting 720p/129-frame generation, beating Gen-3 and Kling in benchmarks.
* **Published in:** arXiv 2024 / GitHub
* **Links:** [[Paper]](https://arxiv.org/abs/2412.03603) | [[Project]](https://github.com/Tencent/HunyuanVideo)

> **Core Innovation**
> **HunyuanVideo** marks the entry of open-source video generation into the DiT era. Departing from the UNet path of VideoCrafter, it builds a novel **Dual-Stream DiT**. Key contributions include: 1) **Unified Image-Video Training**, using images for spatial detail and videos for dynamics; 2) **MLLM Re-captioning**, using Multimodal LLMs to generate extremely detailed descriptions for training data, boosting text control; 3) **Causal 3D VAE**, achieving high compression with lossless quality. Its full open-source release has made it the primary base model for community fine-tuning.

<details>
    <summary>Abstract</summary>
    We present HunyuanVideo, an open-source large-scale video generation model. To achieve high-quality generation, we design a systematic framework covering data processing, model architecture, and training strategies. We propose a unified DiT architecture capable of learning from both image and video data simultaneously. By combining detailed captions from MLLMs with an efficient 3D VAE, HunyuanVideo achieves state-of-the-art performance in subject consistency, motion smoothness, and visual quality, surpassing proprietary commercial models on several metrics.
</details>

<details>
    <summary>Key points</summary>
    * **Dual-Stream DiT:** Processes content and text information separately, similar to Stable Diffusion 3.
    * **Data Engineering:** Highlights the decisive role of detailed MLLM captioning in video quality.
    * **Open Source Foundation:** Provides full inference code and weights, supporting LoRA fine-tuning with a thriving ecosystem.
</details>
</details>

---

<details>
<summary><b>VideoCrafter2: Overcoming Data Limitations</b></summary>

* **Authors:** Haoxin Chen, et al. (Tencent AI Lab)
* **arXiv ID:** 2401.09047
* **One-liner:** The classic open-source UNet video baseline, proving that high-quality generation can be achieved even with low-quality training data by decoupling motion and appearance.
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2401.09047) | [[Project]](https://github.com/AILab-CVC/VideoCrafter)

> **Core Innovation**
> Before the DiT explosion, **VideoCrafter2** was one of the strongest open-source UNet video models. The core challenge it addressed was the scarcity of high-quality video data (like 4K clips) versus the abundance of low-quality web videos. VideoCrafter2 proposed a strategy: train on massive low-quality videos first to learn **Generic Motion Concepts**, then fine-tune to shift the model to a high-quality visual distribution. It demonstrated that motion patterns and visual quality can be **disentangled**, making it a crucial baseline for researchers (and the AnimateDiff community).

<details>
    <summary>Abstract</summary>
    Training high-quality video models is hindered by the scarcity of high-quality video data. We propose VideoCrafter2 to overcome this. We observe that low-quality videos, while visually poor, contain rich motion patterns. Thus, we propose disentangling motion learning from appearance learning. We first train on large-scale low-quality datasets to learn motion, then fine-tune with high-quality images and videos to upgrade visual quality. Results show VideoCrafter2 significantly outperforms VideoCrafter1 and contemporaries in generic video generation.
</details>

<details>
    <summary>Key points</summary>
    * **Decoupled Training:** Proves "learn motion from bad videos, learn quality from good images" works.
    * **Peak UNet Architecture:** Represents the mature form of traditional 2D/3D UNet in video generation.
    * **Broad Compatibility:** Due to its standard architecture, it supports numerous ControlNet and LoRA plugins.
</details>
</details>

---

<details>
<summary><b>LTX-Video: High-Resolution Video Generation with Latent Flow Matching</b></summary>

* **Authors:** Lightricks R&D (Creators of Facetune/Videoleap)
* **arXiv ID:** 2501.00103
* **One-liner:** The first open-source DiT video model prioritizing **Real-time Speed** and **Efficiency**, using Latent Flow Matching to achieve faster generation than Hunyuan on consumer GPUs.
* **Published in:** arXiv 2025 / GitHub
* **Links:** [[Paper]](https://arxiv.org/abs/2501.00103) | [[Project]](https://github.com/Lightricks/LTX-Video)

> **Core Innovation**
> While most DiT models (like Sora, Hunyuan) chase extreme quality at the cost of speed, Lightricks' **LTX-Video** takes a different path: **Efficiency**. Although based on DiT, it utilizes **Latent Flow Matching** technology and optimizes the Transformer structure significantly. LTX-Video achieves near real-time inference latency while maintaining high fluidity (24fps). Its relatively low VRAM footprint makes fine-tuning and inference accessible on consumer GPUs (e.g., RTX 3090/4090), representing the "lightweight" class of video generation.

<details>
    <summary>Abstract</summary>
    Large-scale video generation models are typically computationally expensive and slow. We present LTX-Video, an efficient DiT-based video generation model. By combining Latent Flow Matching with a novel spatiotemporal compression scheme, we drastically reduce computational overhead without significantly sacrificing visual quality. LTX-Video generates high-resolution videos faster than real-time and demonstrates superior motion consistency and text alignment in human evaluations. It is the first DiT video model truly optimized for consumer hardware.
</details>

<details>
    <summary>Key points</summary>
    * **Flow Matching:** Replaces traditional diffusion with straighter sampling paths, requiring fewer steps.
    * **Consumer-Friendly:** Optimized VRAM usage and speed, lowering the barrier for DiT video generation.
    * **High Frame Rate:** Focuses on generating native high frame rates (24fps+), avoiding interpolation artifacts.
</details>
</details>

---