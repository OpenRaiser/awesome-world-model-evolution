<p align="center">
  <a href="README.md">English</a> | <a href="README_zh.md">中文</a>
</p>

### Modality + Spatial Consistency

**Capability Profile**: Models that can translate text/image descriptions into spatially coherent 3D representations or multi-view consistent outputs.

**Significance**: These models demonstrate "3D imagination" - they are no longer mere "2D painters" but "digital sculptors" understanding spatial structure.

#### Representative Works

<details>
<summary><b>Zero-1-to-3: Zero-shot One Image to 3D Object</b></summary>

* **Authors:** Ruoshi Liu, Rundi Wu, Basile Van Hoorick, Pavel Tokmakov, Sergey Zakharov, Carl Vondrick  
* **arXiv ID:** 2303.11328  
* **One-liner:** A framework that takes a single RGB image and enables novel-view synthesis and implicit 3D reconstruction via viewpoint-conditioned diffusion.  
* **Published in:** ICCV 2023  
* **Links:** [[Paper]](https://arxiv.org/abs/2303.11328) | [[PDF]](https://arxiv.org/pdf/2303.11328.pdf) | [[Code]](https://github.com/cvlab-columbia/zero123)

> **Core Innovation**  
> Leverages the implicit geometric priors of large-scale pretrained diffusion models to learn camera-viewpoint changes from a single image, enabling synthesis of novel views of the same object under specified transformations and further supporting single-image implicit 3D reconstruction.

<details>
    <summary>Abstract</summary>
    We introduce Zero-1-to-3, a framework for changing the camera viewpoint of an object given just a single RGB image. To perform novel view synthesis in this under-constrained setting, we capitalize on the geometric priors that large-scale diffusion models learn about natural images. Our conditional diffusion model uses a synthetic dataset to learn controls of the relative camera viewpoint, which allow new images to be generated of the same object under a specified camera transformation. Even though it is trained on a synthetic dataset, our model retains a strong zero-shot generalization ability to out-of-distribution datasets as well as in-the-wild images, including impressionist paintings. Our viewpoint-conditioned diffusion approach can further be used for the task of 3D reconstruction from a single image. Qualitative and quantitative experiments show that our method significantly outperforms state-of-the-art single-view 3D reconstruction and novel view synthesis models by leveraging Internet-scale pre-training.
</details>

<details>
    <summary>Key points</summary>
    * Leverages large-scale pre-trained 2D diffusion models to extract implicit 3D/geometric priors.  
    * Conditions generation on a single RGB image + relative camera transformation (rotation + translation).  
    * Achieves zero-shot generalization to out-of-distribution real-world and artistic images.  
    * Enables both novel-view synthesis and implicit 3D reconstruction from only one image.  
</details>
</details>

---

<details>
<summary><b>MVDream: Multi-view Diffusion for 3D Generation</b></summary>

* **Authors:** Yichun Shi, Peng Wang, Jianglong Ye, Long Mai, Kejie Li, Xiao Yang  
* **arXiv ID:** 2308.16512  
* **One-liner:** A multi-view diffusion model that generates geometrically consistent multi-view images from text prompts, enabling 3D generation via 2D+3D synergy.  
* **Published in:** ICLR 2024  
* **Links:** [[Paper]](https://arxiv.org/abs/2308.16512) | [[PDF]](https://arxiv.org/pdf/2308.16512.pdf) | [[Code]](https://github.com/bytedance/MVDream)

> **Core Innovation**  
> Proposes a diffusion model that produces geometrically-consistent multi-view images by first pretraining on 2D images and then fine-tuning on 3D data, inheriting the generalization power of 2D diffusion while guaranteeing 3D-render consistency—serving as a universal prior for 3D content generation.

<details>
    <summary>Abstract</summary>
    We introduce MVDream, a diffusion model that is able to generate consistent multi-view images from a given text prompt. Learning from both 2D and 3D data, a multi-view diffusion model can achieve the generalizability of 2D diffusion models and the consistency of 3D renderings. We demonstrate that such a multi-view diffusion model is implicitly a generalizable 3D prior agnostic to 3D representations. It can be applied to 3D generation via Score Distillation Sampling, significantly enhancing the consistency and stability of existing 2D-lifting methods. It can also learn new concepts from a few 2D examples, akin to DreamBooth, but for 3D generation.
</details>

<details>
    <summary>Key points</summary>
    * Combines web-scale 2D diffusion pre-training with fine-tuning on multi-view 3D asset rendered dataset.  
    * Generates sets of consistent multi-view images conditioned on text prompts, facilitating 3D reconstruction/generation tasks.  
    * Serves as a 3D-agnostic prior: the model does not commit to one explicit 3D representation but still ensures multi-view consistency.  
    * Demonstrates improved geometry fidelity using Score Distillation Sampling driven by multi-view images.  
</details>
</details>

---

<details>
<summary><b>Wonder3D: Single Image to 3D using Cross-Domain Diffusion</b></summary>

* **Authors:** Xiaoxiao Long, Yuan-Chen Guo, Cheng Lin, Yuan Liu, Zhiyang Dou, Lingjie Liu, Yuexin Ma, Song-Hai Zhang, Marc Habermann, Christian Theobalt, Wenping Wang  
* **arXiv ID:** 2310.15008  
* **One-liner:** Efficiently reconstruct high-fidelity textured meshes from a single view image via a cross-domain diffusion generating multi-view normal maps + color images.  
* **Published in:** CVPR 2024  
* **Links:** [[Paper]](https://arxiv.org/abs/2310.15008) | [[PDF]](https://arxiv.org/pdf/2310.15008.pdf) | [[Code]](https://github.com/xxlong0/Wonder3D)

> **Core Innovation**  
> Introduces a single-image-to-high-fidelity-textured-mesh pipeline: a cross-domain diffusion model first synthesizes multi-view normals and RGB images; multi-view cross-domain attention enforces inter-view/inter-modal consistency; finally, a geometry-aware normal-fusion algorithm fuses the 2D representations into a high-quality textured mesh.

<details>
    <summary>Abstract</summary>
    In this work, we introduce Wonder3D, a novel method for efficiently generating high-fidelity textured meshes from single-view images. Recent methods based on Score Distillation Sampling (SDS) have shown the potential to recover 3D geometry from 2D diffusion priors, but they typically suffer from time-consuming per-shape optimization and inconsistent geometry. In contrast, certain works directly produce 3D information via fast network inferences, but their results are often of low quality and lack geometric details. To holistically improve the quality, consistency, and efficiency of image-to-3D tasks, we propose a cross-domain diffusion model that generates multi-view normal maps and the corresponding color images. To ensure consistency, we employ a multi-view cross-domain attention mechanism that facilitates information exchange across views and modalities. Lastly, we introduce a geometry-aware normal fusion algorithm that extracts high-quality surfaces from the multi-view 2D representations. Our extensive evaluations demonstrate that our method achieves high-quality reconstruction results, robust generalization, and reasonably good efficiency compared to prior works.  
</details>

<details>
    <summary>Key points</summary>
    * Uses a cross-domain diffusion model to generate multi-view normal maps + color images from a single input view.  
    * Multi-view cross-domain attention mechanism ensures consistency across generated views and domains (normals vs colors).  
    * Geometry-aware normal fusion algorithm transforms the multi-view 2D outputs into a high-quality textured mesh efficiently.  
    * Achieves high-fidelity textured mesh reconstruction with strong generalization and relatively fast inference (minutes) from a single image.  
</details>
</details>

---

<details>
<summary><b>SyncDreamer: Generating Multiview-consistent Images from a Single-view Image</b></summary>

* **Authors:** Yuan Liu, Cheng Lin, Zijiao Zeng, Xiaoxiao Long, Lingjie Liu, Taku Komura, Wenping Wang  
* **arXiv ID:** 2309.03453  
* **One-liner:** A synchronized multiview diffusion model that, from one input view, produces multiple consistent views via a joint reverse-diffusion process.  
* **Published in:** ICLR 2024  
* **Links:** [[Paper]](https://arxiv.org/abs/2309.03453) | [[PDF]](https://arxiv.org/pdf/2309.03453.pdf) | [[Code]](https://github.com/liuyuan-pal/SyncDreamer)

> **Core Innovation**  
> Introduces SyncDreamer, a synchronized multi-view generation framework that jointly produces multiple views during the reverse diffusion process. By leveraging 3D-aware feature attention to synchronize intermediate states across all viewpoints, it enforces both geometric and color consistency, enabling the creation of a consistent multi-view image set from a single input—providing strong support for single-image-to-3D and text-to-3D tasks.

<details>
    <summary>Abstract</summary>
    In this paper, we present a novel diffusion model called SyncDreamer that generates multiview-consistent images from a single-view image. Using pretrained large-scale 2D diffusion models, recent work Zero123 demonstrates the ability to generate plausible novel views from a single-view image of an object. However, maintaining consistency in geometry and colors for the generated images remains a challenge. To address this issue, we propose a synchronized multiview diffusion model that models the joint probability distribution of multiview images, enabling the generation of multiview-consistent images in a single reverse process. SyncDreamer synchronizes the intermediate states of all the generated images at every step of the reverse process through a 3D-aware feature attention mechanism that correlates the corresponding features across different views. Experiments show that SyncDreamer generates images with high consistency across different views, thus making it well-suited for various 3D generation tasks such as novel-view-synthesis, text-to-3D, and image-to-3D.  
</details>

<details>
    <summary>Key points</summary>
    * Models the joint distribution of multiple views in a single diffusion reverse process, rather than generating each view independently.  
    * Introduces a 3D-aware feature attention mechanism that synchronizes intermediate states across views to maintain geometry and color consistency.  
    * From a single view image, produces multiple coherent novel view images suitable for downstream 3D tasks.  
    * Demonstrates strong multiview consistency, facilitating improved image-to-3D or text-to-3D workflows.  
</details>
</details>

---

<details>
<summary><b>DreamFusion: Text-to-3D using 2D Diffusion</b></summary>

* **Authors:** Ben Poole, Ajay Jain, Jonathan T. Barron, Ben Mildenhall
* **arXiv ID:** 2209.14988
* **One-liner:** DreamFusion pioneers text-to-3D by distilling a pre-trained 2D diffusion model into 3D NeRFs via Score Distillation Sampling, requiring zero 3D training data.
* **Published in:** ICRL 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2209.14988) | [[PDF]](https://arxiv.org/pdf/2209.14988.pdf) | [[Project Page]](https://dreamfusion3d.github.io/)

> **Core Innovation**  
> Introduces Score Distillation Sampling (SDS)—a loss that leverages 2D diffusion score functions as priors to optimize a randomly-initialized NeRF in parameter space, enabling text-to-3D without any 3D supervision.

<details>
    <summary>Abstract</summary>
    Recent breakthroughs in text-to-image synthesis have been driven by diffusion models trained on billions of image-text pairs. Adapting this approach to 3D synthesis would require large-scale datasets of labeled 3D data and efficient architectures for denoising 3D data, neither of which currently exist. In this work, we circumvent these limitations by using a pretrained 2D text-to-image diffusion model to perform text-to-3D synthesis. We introduce a loss based on probability density distillation that enables the use of a 2D diffusion model as a prior for optimization of a parametric image generator. Using this loss in a DeepDream-like procedure, we optimize a randomly-initialized 3D model (a Neural Radiance Field, or NeRF) via gradient descent such that its 2D renderings from random angles achieve a low loss. The resulting 3D model of the given text can be viewed from any angle, relit by arbitrary illumination, or composited into any 3D environment. Our approach requires no 3D training data and no modifications to the image diffusion model, demonstrating the effectiveness of pretrained image diffusion models as priors.
</details>

<details>
    <summary>Key points</summary>
    * Zero 3D annotations—only a large-scale 2D text-to-image diffusion model is required.
    * SDS replaces reconstruction loss; updates NeRF by matching injected noise to diffusion-predicted scores.
    * Integrates mip-NeRF 360 with differentiable shading for coherent geometry and appearance.
    * View-dependent text conditioning plus geometric regularizers mitigate “cardboard” local minima. 
</details>
</details>

---

<details>
<summary><b>ULIP-2: Towards Scalable Multimodal Pre-training for 3D Understanding</b></summary>

* **Authors:** Le Xue, Ning Yu, Shu Zhang, Artemis Panagopoulou, Junnan Li, Roberto Martín-Martín, Jiajun Wu, Caiming Xiong, Ran Xu, Juan Carlos Niebles, Silvio Savarese
* **arXiv ID:** 2305.08275
* **One-liner:** ULIP-2 introduces a scalable, annotation-free multimodal pre-training framework that aligns 3D point clouds with images and automatically generated text, enabling superior 3D understanding.
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2305.08275) | [[PDF]](https://arxiv.org/pdf/2305.08275.pdf) | [[Code]](https://github.com/salesforce/ULIP)

> **Core Innovation**  
> Leverages large multimodal models (BLIP-2) to automatically generate holistic language descriptions from rendered 2D views of 3D objects, enabling scalable tri-modal alignment without human annotations.

<details>
    <summary>Abstract</summary>
    Recent advancements in multimodal pre-training have shown promising efficacy in 3D representation learning by aligning multimodal features across 3D shapes, their 2D counterparts, and language descriptions. However, the methods used by existing frameworks to curate such multimodal data, in particular language descriptions for 3D shapes, are not scalable, and the collected language descriptions are not diverse. To address this, we introduce ULIP-2, a simple yet effective tri-modal pre-training framework that leverages large multimodal models to automatically generate holistic language descriptions for 3D shapes. It only needs 3D data as input, eliminating the need for any manual 3D annotations, and is therefore scalable to large datasets. ULIP-2 is also equipped with scaled-up backbones for better multimodal representation learning. We conduct experiments on two large-scale 3D datasets, Objaverse and ShapeNet, and augment them with tri-modal datasets of 3D point clouds, images, and language for training ULIP-2. Experiments show that ULIP-2 demonstrates substantial benefits in three downstream tasks: zero-shot 3D classification, standard 3D classification with fine-tuning, and 3D captioning (3D-to-language generation). It achieves a new SOTA of 50.6% (top-1) on Objaverse-LVIS and 84.7% (top-1) on ModelNet40 in zero-shot classification. In the ScanObjectNN benchmark for standard fine-tuning, ULIP-2 reaches an overall accuracy of 91.5% with a compact model of only 1.4 million parameters. ULIP-2 sheds light on a new paradigm for scalable multimodal 3D representation learning without human annotations and shows significant improvements over existing baselines.
</details>

<details>
    <summary>Key points</summary>
    * Annotation-free: only 3D data is required, making the framework highly scalable.
    * Uses BLIP-2 to generate detailed, multi-view language descriptions, enhancing text modality quality and diversity.
    * Introduces two large-scale tri-modal datasets: ULIP-Objaverse and ULIP-ShapeNet.
    * Achieves SOTA performance on zero-shot 3D classification, standard classification, and 3D-to-language captioning.
</details>
</details>

---

<details>
<summary><b>OpenShape: Scaling Up 3D Shape Representation Towards Open-World Understanding</b></summary>

* **Authors:** Minghua Liu, Ruoxi Shi, Kaiming Kuang, Yinhao Zhu, Xuanlin Li, Shizhong Han, Hong Cai, Fatih Porikli, Hao Su
* **arXiv ID:** 2305.10764
* **One-liner:** OpenShape achieves powerful open-world zero-shot 3D shape recognition by scaling up multimodal contrastive learning aligned with CLIP across large-scale 3D datasets.
* **Published in:** NeurIPS 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2305.10764) | [[PDF]](https://arxiv.org/pdf/2305.10764.pdf) | [[Code]](https://github.com/Colin97/OpenShape_code)

> **Core Innovation**  
> Introduces a scalable tri-modal contrastive learning framework with automated text filtering/enrichment, 3D backbone scaling, and hard negative mining to greatly improve open-world generalization of 3D representations.

<details>
    <summary>Abstract</summary>
    We introduce OpenShape, a method for learning multi-modal joint representations of text, image, and point clouds. We adopt the commonly used multi-modal contrastive learning framework for representation alignment, but with a specific focus on scaling up 3D representations to enable open-world 3D shape understanding. To achieve this, we scale up training data by ensembling multiple 3D datasets and propose several strategies to automatically filter and enrich noisy text descriptions. We also explore and compare strategies for scaling 3D backbone networks and introduce a novel hard negative mining module for more efficient training. We evaluate OpenShape on zero-shot 3D classification benchmarks and demonstrate its superior capabilities for open-world recognition. Specifically, OpenShape achieves a zero-shot accuracy of 46.8% on the 1,156-category Objaverse-LVIS benchmark, compared to less than 10% for existing methods. OpenShape also achieves an accuracy of 85.3% on ModelNet40, outperforming previous zero-shot baseline methods by 20% and performing on par with some fully-supervised methods. Furthermore, we show that our learned embeddings encode a wide range of visual and semantic concepts (e.g., subcategories, color, shape, style) and facilitate fine-grained text-3D and image-3D interactions. Due to their alignment with CLIP embeddings, our learned shape representations can also be integrated with off-the-shelf CLIP-based models for various applications, such as point cloud captioning and point cloud-conditioned image generation.
</details>

<details>
    <summary>Key points</summary>
    * Ensembles 876k 3D shapes across diverse categories to address data scarcity.
    * Proposes three text enrichment strategies—filtering, captioning, and image retrieval—to improve text quality and semantics.
    * Evaluates and scales multiple 3D backbones (e.g., PointBERT, SparseConv) for large-scale training.
    * Introduces hard negative mining to address class imbalance and enhance model discrimination.
    * Learned 3D representations are CLIP-aligned and readily usable for cross-modal tasks like image generation and captioning.
</details>
</details>

---

<details>
<summary><b>DreamLLM: Synergistic Multimodal Comprehension and Creation</b></summary>

* **Authors:** Runpei Dong, Chunrui Han, Yuang Peng, Zekun Qi, Zheng Ge, Jinrong Yang, Liang Zhao, Jianjian Sun, Hongyu Zhou, Haoran Wei, Xiangwen Kong, Xiangyu Zhang, Kaisheng Ma, Li Yi
* **arXiv ID:** 2309.11499
* **One-liner:** DREAMLLM is the first multimodal large language model that unifies comprehension and creation by end-to-end generating raw interleaved text and images, enabling true synergy between understanding and generation.
* **Published in:** ICLR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2309.11499) | [[PDF]](https://arxiv.org/pdf/2309.11499.pdf) | [[Code]](https://github.com/RunpeiDong/DreamLLM)

> **Core Innovation**  
> Introduces a novel Interleaved Generative Pre-training (I-GPT) framework that uses dream queries and score distillation to directly model image posteriors without relying on intermediate representations like CLIP, enabling native generation and understanding of interleaved multimodal content.

<details>
    <summary>Abstract</summary>
    This paper presents DreamLLM, a learning framework that first achieves versatile Multimodal Large Language Models (MLLMs) empowered with frequently overlooked synergy between multimodal comprehension and creation. DreamLLM operates on two fundamental principles. The first focuses on the generative modeling of both language and image posteriors by direct sampling in the raw multimodal space. This approach circumvents the limitations and information loss inherent to external feature extractors like CLIP, and a more thorough multimodal understanding is obtained. Second, DreamLLM fosters the generation of raw, interleaved documents, modeling both text and image contents, along with unstructured layouts. This allows DreamLLM to learn all conditional, marginal, and joint multimodal distributions effectively. As a result, DreamLLM is the first MLLM capable of generating free-form interleaved content. Comprehensive experiments highlight DreamLLM's superior performance as a zero-shot multimodal generalist, reaping from the enhanced learning synergy.
</details>

<details>
    <summary>Key points</summary>
    * First MLLM capable of free-form interleaved text-image generation with real synergy between creation and comprehension.
    * Introduces dream queries and dream label
    * Uses score distillation for direct pixel-space image sampling, avoiding CLIP-induced semantic loss and modality gaps.
    * Supports in-context multimodal generation such as image editing, subject-driven generation, and compositional creation.
</details>
</details>

---

<details>
<summary><b>EditWorld: Simulating World Dynamics for Instruction-Following Image Editing</b></summary>

* **Authors:** Ling Yang, Bohan Zeng, Jiaming Liu, Hong Li, Minghao Xu, Wentao Zhang, Shuicheng Yan
* **arXiv ID:** 2405.14785
* **One-liner:** EDITWORLD introduces the first world-instructed image editing task, enabling more intelligent and physically plausible image editing by simulating real and virtual world dynamics.
* **Published in:** ACM Multimedia 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2405.14785) | [[PDF]](https://arxiv.org/pdf/2405.14785.pdf) | [[Code]](https://github.com/YangLing0818/EditWorld)

> **Core Innovation**  
> Proposes the concept of world instructions, systematically defines and categorizes seven types of editing instructions that reflect world dynamics, constructs a multimodal dataset with complex semantic changes, and introduces a post-edit strategy to improve editing quality and consistency.

<details>
    <summary>Abstract</summary>
    Diffusion models have significantly improved the performance of image editing. Existing methods realize various approaches to achieve high-quality image editing, including but not limited to text control, dragging operation, and mask-and-inpainting. Among these, instruction-based editing stands out for its convenience and effectiveness in following human instructions across diverse scenarios. However, it still focuses on simple editing operations like adding, replacing, or deleting, and falls short of understanding aspects of world dynamics that convey the realistic dynamic nature in the physical world. Therefore, this work, EditWorld, introduces a new editing task, namely world-instructed image editing, which defines and categorizes the instructions grounded by various world scenarios. We curate a new image editing dataset with world instructions using a set of large pretrained models (e.g., GPT-3.5, Video-LLava and SDXL). To enable sufficient simulation of world dynamics for image editing, our EditWorld trains model in the curated dataset, and improves instruction-following ability with designed post-edit strategy. Extensive experiments demonstrate our method significantly outperforms existing editing methods in this new task.
</details>

<details>
    <summary>Key points</summary>
    * Introduces world-instructed image editing, going beyond traditional add/remove/replace operations.
    * Constructs a high-quality dataset with 10K+ triplets covering complex dynamics from real and virtual worlds.
    * Designs a dual-branch data generation pipeline: text-to-image synthesis + video frame extraction, leveraging GPT, Video-LLaVA, SDXL, etc.
    * Proposes MLLM Score, a new metric for better evaluating semantic alignment of editing results.
    * Introduces a Post-Edit method combining SAM and inpainting to improve editing precision and non-edited region consistency.
</details>
</details>

---

<details>
<summary><b>MIO: A Foundation Model on Multimodal Tokens</b></summary>

* **Authors:** Zekun Wang, King Zhu, Chunpu Xu, Wangchunshu Zhou, Jiaheng Liu, Yibo Zhang, Jiashuo Wang, Ning Shi, Siyu Li, Yizhi Li, Haoran Que, Zhaoxiang Zhang, Yuanxing Zhang, Ge Zhang, Ke Xu, Jie Fu, Wenhao Huang
* **arXiv ID:** 2409.17692
* **One-liner:** MIO is the first open-source any-to-any foundation model that simultaneously understands and generates text, image, speech and video in a unified, end-to-end, autoregressive way.
* **Published in:** EMNLP 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2409.17692) | [[PDF]](https://arxiv.org/pdf/2409.17692.pdf) | [[Code]](https://github.com/MIO-Team/MIO)

> **Core Innovation**  
> MIO is the first open-source any-to-any foundation model that simultaneously understands and generates text, image, speech and video in a unified, end-to-end, autoregressive way.

<details>
    <summary>Abstract</summary>
    State-of-the-art computer vision systems are trained to predict a fixed set of predetermined object categories. This restricted form of supervision limits their generality and usability since additional labeled data is needed to specify any other visual concept. Learning directly from raw text about images is a promising alternative which leverages a much broader source of supervision. We demonstrate that the simple pre-training task of predicting which caption goes with which image is an efficient and scalable way to learn SOTA image representations from scratch on a dataset of 400 million (image, text) pairs collected from the internet. After pre-training, natural language is used to reference learned visual concepts (or describe new ones) enabling zero-shot transfer of the model to downstream tasks. We study the performance of this approach by benchmarking on over 30 different existing computer vision datasets, spanning tasks such as OCR, action recognition in videos, geo-localization, and many types of fine-grained object classification. The model transfers non-trivially to most tasks and is often competitive with a fully supervised baseline without the need for any dataset specific training. For instance, we match the accuracy of the original ResNet-50 on ImageNet zero-shot without needing to use any of the 1.28 million training examples it was trained on.
</details>

<details>
    <summary>Key points</summary>
    * DIDO discrete-token framework guarantees I/O consistency and natively supports multimodal interleaved generation.
    * SpeechTokenizer & SEED-Tokenizer provide compact, causal tokens for speech/video/image, ready for next-token prediction.
    * Three-stage pre-training (alignment → interleaved → speech-enhanced) + large-scale multi-task SFT deliver strong uni/bi-modal performance.
    * Competitive or SOTA results on image/text/speech/video benchmarks; emergent abilities: chain-of-visual-thought, visual story, instructional editing.
    * Fully open-source, 7 B-scale, end-to-end trainable, no external diffusion or TTS tools required.
</details>
</details>

---

<details>
<summary><b>SGEdit: Bridging LLM with Text2Image Generative Model for Scene Graph-based Image Editing</b></summary>

* **Authors:** Zhiyuan Zhang, DongDong Chen, Jing Liao
* **arXiv ID:** 2410.11815
* **One-liner:** SGEdit marries LLM reasoning with a fine-tuned diffusion model to turn a scene-graph interface into precise, open-vocabulary image edits—add, remove, replace or re-relate objects in one unified “remove-then-generate” pipeline.
* **Published in:** SIGGRAPH Asia 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2410.11815) | [[PDF]](https://arxiv.org/pdf/2410.11815.pdf) | [[Code]](https://github.com/bestzzhang/SGEdit-code)

> **Core Innovation**  
> First system that uses an LLM both as (1) an open-vocabulary scene parser that outputs masks + detailed captions and (2) an editing controller that plans attention-modulated remove/generate steps, all empowered by hybrid concept learning (optimized token + rich prompt) for identity-preserving yet editable objects.

<details>
    <summary>Abstract</summary>
    Scene graphs offer a structured, hierarchical representation of images, with nodes and edges symbolizing objects and the relationships among them. It can serve as a natural interface for image editing, dramatically improving precision and flexibility. Leveraging this benefit, we introduce a new framework that integrates large language model (LLM) with Text2Image generative model for scene graph-based image editing. This integration enables precise modifications at the object level and creative recomposition of scenes without compromising overall image integrity. Our approach involves two primary stages: ① Utilizing a LLM-driven scene parser, we construct an image's scene graph, capturing key objects and their interrelationships, as well as parsing fine-grained attributes such as object masks and descriptions. These annotations facilitate concept learning with a fine-tuned diffusion model, representing each object with an optimized token and detailed description prompt. ② During the image editing phase, a LLM editing controller guides the edits towards specific areas. These edits are then implemented by an attention-modulated diffusion editor, utilizing the fine-tuned model to perform object additions, deletions, replacements, and adjustments. Through extensive experiments, we demonstrate that our framework significantly outperforms existing image editing methods in terms of editing precision and scene aesthetics.
</details>

<details>
    <summary>Key points</summary>
    * Scene-graph-driven UI: users edit nodes/edges; system translates to executable ops.
    * LLM parser → graph + per-object mask & caption; hybrid concept learning fine-tunes SD for each object.
    * LLM controller decomposes any edit into sequential “remove → generate” with text prompts & boxes.
    * Attention-modulated removal fills masked regions by attending only to unmasked features; insertion enhances cross-attn alignment and suppresses inter-box self-attn. 
</details>
</details>

---

<details>
<summary><b>UniReal: Universal Image Generation and Editing via Learning Real-world Dynamics</b></summary>

* **Authors:** Xi Chen, Zhifei Zhang, He Zhang, Yuqian Zhou, Soo Ye Kim, Qing Liu, Yijun Li, Jianming Zhang, Nanxuan Zhao, Yilin Wang, Hui Ding, Zhe Lin, Hengshuang Zhao
* **arXiv ID:** 2412.07774
* **One-liner:** UniReal treats any image task as “discontinuous video” inside a single 5 B diffusion transformer, learning real-world dynamics from massive video frames to unify generation, editing, customization and composition with one model.
* **Published in:** CVPR 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2412.07774) | [[PDF]](https://arxiv.org/pdf/2412.07774.pdf) | [[Code]](https://github.com/XavierCHEN34/UniReal)

> **Core Innovation**  
> First universal image model that reformulates diverse tasks into pseudo-video frame generation, leverages scalable video supervision for natural consistency/variation, and introduces hierarchical prompt (context + image role) plus index embedding to disambiguate multi-image inputs under one text prompt.

<details>
    <summary>Abstract</summary>
    We introduce UniReal, a unified framework designed to address various image generation and editing tasks. Existing solutions often vary by tasks, yet share fundamental principles: preserving consistency between inputs and outputs while capturing visual variations. Inspired by recent video generation models that effectively balance consistency and variation across frames, we propose a unifying approach that treats image-level tasks as discontinuous video generation. Specifically, we treat varying numbers of input and output images as frames, enabling seamless support for tasks such as image generation, editing, customization, composition, etc. Although designed for image-level tasks, we leverage videos as a scalable source for universal supervision. UniReal learns world dynamics from large-scale videos, demonstrating advanced capability in handling shadows, reflections, pose variation, and object interaction, while also exhibiting emergent capability for novel applications.
</details>

<details>
    <summary>Key points</summary>
    * Single 5B diffusion transformer; full attention across any number of input/output frames.
    * Three image roles—canvas, asset, control—plus learnable category & index embeddings bind visuals to prompt terms like “IMG1”.
    * Hierarchical prompt: base prompt + context tags (realistic/synthetic, static/dynamic, w/ or w/o ref) + image role tags; composable at inference.
    * Auto pipeline mines 23M+ frame pairs from videos with captions, masks, depth, edges → universal supervision for add, remove, replace, stylize, customize, insert, perception.
    * Emergent zero-shot abilities: multi-object insertion, depth-conditioned generation, reference inpainting, object resizing, etc.
    * Training: 256 → 512 → 1024 progressive resolution; flow-matching loss; handles arbitrary aspect ratios.
</details>
</details>

---

<details>
<summary><b>ShapeLLM-Omni: A Native Multimodal LLM for 3D Generation and Understanding</b></summary>

* **Authors:** Junliang Ye, Zhengyi Wang, Ruowen Zhao, Shenghao Xie, Jun Zhu
* **arXiv ID:** 2506.01853
* **One-liner:** ShapeLLM-Omni is the first native 3D-LLM that unifies text ⇄ image ⇄ 3D mesh generation, understanding and editing in one autoregressive next-token framework.
* **Published in:** NeurIPS 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2506.01853) | [[PDF]](https://arxiv.org/pdf/2506.01853.pdf) | [[Code]](https://github.com/JAMESYJL/ShapeLLM-Omni)

> **Core Innovation**  
> A 3D VQVAE compresses voxels into 1024 discrete tokens, enabling a frozen Qwen-2.5-VL-7B to perform fully autoregressive 3D generation/editing/understanding without extra networks; the 3D-Alpaca dataset (3.46 B tokens) makes it scalable.

<details>
    <summary>Abstract</summary>
    Recently, the powerful text-to-image capabilities of ChatGPT-4o have led to growing appreciation for native multimodal large language models. However, its multimodal capabilities remain confined to images and text. Yet beyond images, the ability to understand and generate 3D content is equally crucial. To address this gap, we propose ShapeLLM-Omni-a native 3D large language model capable of understanding and generating 3D assets and text in any sequence. First, we train a 3D vector-quantized variational autoencoder (VQVAE), which maps 3D objects into a discrete latent space to achieve efficient and accurate shape representation and reconstruction. Building upon the 3D-aware discrete tokens, we innovatively construct a large-scale continuous training dataset named 3D-Alpaca, encompassing generation, comprehension, and editing, thus providing rich resources for future research and training. Finally, by performing instruction-based training of the Qwen-2.5-vl-7B-Instruct model on the 3D-Alpaca dataset. Our work provides an effective attempt at extending multimodal models with basic 3D capabilities, which contributes to future research in 3D-native AI.
</details>

<details>
    <summary>Key points</summary>
    * Unified tokenizer: 643 → 163 latent → 1024 discrete tokens; 8192-codebook; reversible to high-quality mesh via Rectified-Flow.
    * Native 3D-LLM: same transformer handles text, image features, 3D tokens in any order; next-token prediction end-to-end.
    * 3D-Alpaca: 712k text-to-3D, 712k image-to-3D, 712k 3D caption, 420k 3D editing pairs + UltraChat; 2.56 M samples, 3.46 B tokens.
    * Tasks: text-to-3D, image-to-3D, 3D-to-text, interactive 3D editing (add/remove/modify), multi-turn dialogue.
</details>
</details>

---

<details>
<summary><b>Step1X-Edit: A Practical Framework for General Image Editing</b></summary>

* **Authors:** Shiyu Liu, Yucheng Han, Peng Xing, Fukun Yin, Rui Wang, Wei Cheng, Jiaqi Liao, Yingming Wang, Honghao Fu, Chunrui Han, Guopeng Li, Yuang Peng, Quan Sun, Jingwei Wu, Yan Cai, Zheng Ge, Ranchen Ming, Lei Xia, Xianfang Zeng, Yibo Zhu, Binxing Jiao, Xiangyu Zhang, Gang Yu, Daxin Jiang
* **arXiv ID:** 2504.17761
* **One-liner:** Step1X-Edit closes the gap between open-source and proprietary editors by fusing MLLM reasoning with a DiT decoder, delivering GPT-4o-level quality on 11 real-world editing tasks without masks.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2504.17761) | [[PDF]](https://arxiv.org/pdf/2504.17761.pdf) | [[Code]](https://github.com/stepfun-ai/Step1X-Edit)

> **Core Innovation**  
> A lightweight token-refiner connector injects MLLM edit embeddings directly into a latent DiT via token-concatenation, enabling single-pass, high-fidelity editing trained only with diffusion loss—no masks, no extra self-attention, no T5 text encoder.

<details>
    <summary>Abstract</summary>
    In recent years, image editing models have witnessed remarkable and rapid development. The recent unveiling of cutting-edge multimodal models such as GPT-4o and Gemini2 Flash has introduced highly promising image editing capabilities. These models demonstrate an impressive aptitude for fulfilling a vast majority of user-driven editing requirements, marking a significant advancement in the field of image manipulation. However, there is still a large gap between the open-source algorithm with these closed-source models. Thus, in this paper, we aim to release a state-of-the-art image editing model, called Step1X-Edit, which can provide comparable performance against the closed-source models like GPT-4o and Gemini2 Flash. More specifically, we adopt the Multimodal LLM to process the reference image and the user's editing instruction. A latent embedding has been extracted and integrated with a diffusion image decoder to obtain the target image. To train the model, we build a data generation pipeline to produce a high-quality dataset. For evaluation, we develop the GEdit-Bench, a novel benchmark rooted in real-world user instructions. Experimental results on GEdit-Bench demonstrate that Step1X-Edit outperforms existing open-source baselines by a substantial margin and approaches the performance of leading proprietary models, thereby making significant contributions to the field of image editing.
</details>

<details>
    <summary>Key points</summary>
    * Unified MLLM+DiT pipeline: Qwen-VL parses image+instruction → compact multimodal tokens → DiT synthesizes edited image.
    * 20 M synthetic triplets filtered to 1 M high-quality (Step1X-Edit-HQ); covers 11 tasks: add/remove/replace, motion, material, color, style, tone, text, portrait, background.
    * GEdit-Bench: 606 real-user prompts (EN/CN), privacy-safe, first benchmark with genuine instructions & human filtering.
    * Token-concatenation conditioning preserves fine detail; global guidance vector from mean MLLM embedding enhances semantic alignment.
    * Trained from SD3.5-class base; supports plug-in replacement (FLUX, HiDream, etc.).
</details>
</details>

---

<details>
<summary><b>LangScene-X: Reconstruct Generalizable 3D Language-Embedded Scenes with TriMap Video Diffusion</b></summary>

* **Authors:** Fangfu Liu, Hao Li, Jiawei Chi, Hanyang Wang, Minghui Yang, Fudong Wang, Yueqi Duan
* **arXiv ID:** 2507.02813
* **One-liner:** LangScene-X bootstraps a TriMap video diffusion model with a Language-Quantized Compressor to build 3-D language-embedded Gaussian fields from only two images and answer open-vocabulary queries at novel views—without any per-scene optimization.
* **Published in:** ICCV 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2507.02813) | [[PDF]](https://arxiv.org/pdf/2507.02813.pdf) | [[Code]](https://github.com/liuff19/LangScene-X)

> **Core Innovation**  
> A progressive multi-task video diffusion first jointly generates RGB, normals and multi-granularity segmentation; a lightweight vector-quantized compressor (LQC) trained on COCO reduces 512-D CLIP features to 3-D discrete codes, enabling cross-scene 3-D Gaussian language fields that render in real time.

<details>
    <summary>Abstract</summary>
    Recovering 3D structures with open-vocabulary scene understanding from 2D images is a fundamental but daunting task. Recent developments have achieved this by performing per-scene optimization with embedded language information. However, they heavily rely on the calibrated dense-view reconstruction paradigm, thereby suffering from severe rendering artifacts and implausible semantic synthesis when limited views are available. In this paper, we introduce a novel generative framework, coined LangScene-X, to unify and generate 3D consistent multi-modality information for reconstruction and understanding. Powered by the generative capability of creating more consistent novel observations, we can build generalizable 3D language-embedded scenes from only sparse views. Specifically, we first train a TriMap video diffusion model that can generate appearance (RGBs), geometry (normals), and semantics (segmentation maps) from sparse inputs through progressive knowledge integration. Furthermore, we propose a Language Quantized Compressor (LQC), trained on large-scale image datasets, to efficiently encode language embeddings, enabling cross-scene generalization without per-scene retraining. Finally, we reconstruct the language surface fields by aligning language information onto the surface of 3D scenes, enabling open-ended language queries. Extensive experiments on real-world data demonstrate the superiority of our LangScene-X over state-of-the-art methods in terms of quality and generalizability.
</details>

<details>
    <summary>Key points</summary>
    * TriMap diffusion: 4-stage training (key-frame → 3-D consistent → add normals → add semantics) produces video-level coherent triplets.
    * LQC: VQ-VAE with 2048 codes; 1e-4 L2 loss, gradient bypass; compresses any CLIP field to 3-channel index, zero per-scene cost.
    * Language surface fields: DUSt3R sparse init + progressive normal regularization + 2-D/3-D semantic clustering; 5k steps RGB/Geo, 5k steps sem.
    * Inference: 2 input views → 49-frame TriMap → language Gaussians → real-time novel-view query.
    * Generalizable: one model handles indoor, object-level, in-the-wild; no scene-wise auto-encoder, no dense calibration.
</details>
</details>

---

<details>
<summary><b>MENTOR: Efficient Multimodal-Conditioned Tuning for Autoregressive Vision Generation Models</b></summary>

* **Authors:** Haozhe Zhao, Zefan Cai, Shuzheng Si, Liang Chen, Jiuxiang Gu, Wen Xiao, Junjie Hu
* **arXiv ID:** 2507.09574
* **One-liner:** MENTOR introduces an efficient autoregressive framework for multimodal image generation, achieving fine-grained alignment and balanced control via a two-stage training paradigm.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2507.09574) | [[PDF]](https://arxiv.org/pdf/2507.09574.pdf) | [[Code]](https://github.com/HaozheZhao/MENTOR)

> **Core Innovation**  
> The core innovation lies in an autoregressive image generation method that eliminates the need for cross-attention or auxiliary adapters, using a two-stage training strategy to achieve semantic and pixel-level alignment across multimodal inputs, greatly improving training efficiency and controllability.

<details>
    <summary>Abstract</summary>
    Recent text-to-image models produce high-quality results but still struggle with precise visual control, balancing multimodal inputs, and requiring extensive training for complex multimodal image generation. To address these limitations, we propose MENTOR, a novel autoregressive (AR) framework for efficient Multimodal-conditioned Tuning for Autoregressive multimodal image generation. MENTOR combines an AR image generator with a two-stage training paradigm, enabling fine-grained, token-level alignment between multimodal inputs and image outputs without relying on auxiliary adapters or cross-attention modules. The two-stage training consists of: (1) a multimodal alignment stage that establishes robust pixel- and semantic-level alignment, followed by (2) a multimodal instruction tuning stage that balances the integration of multimodal inputs and enhances generation controllability. Despite modest model size, suboptimal base components, and limited training resources, MENTOR achieves strong performance on the DreamBench++ benchmark, outperforming competitive baselines in concept preservation and prompt following. Additionally, our method delivers superior image reconstruction fidelity, broad task adaptability, and improved training efficiency compared to diffusion-based methods.
</details>

<details>
    <summary>Key points</summary>
    * Unified autoregressive architecture for joint image and text processing with simplified model design.
    * Two-stage training: Stage 1 aligns multimodal inputs; Stage 2 enhances instruction-following and cross-modal fusion.
    * Eliminates cross-attention modules, reducing training costs.
    * Supports various downstream tasks (e.g., segmentation, subject-driven generation, in-context generation) without architectural changes.
</details>
</details>

---

<details>
<summary><b>GSFixer: Improving 3D Gaussian Splatting with Reference-Guided Video Diffusion Priors</b></summary>

* **Authors:** Xingyilang Yin, Qi Zhang, Jiahao Chang, Ying Feng, Qingnan Fan, Xi Yang, Chi-Man Pun, Huaqi Zhang, Xiaodong Cun
* **arXiv ID:** 2508.09667
* **One-liner:** GSFixer introduces a reference-guided video diffusion prior method to restore artifacts in 3D Gaussian Splatting and improve reconstruction quality under sparse-view conditions.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2508.09667) | [[PDF]](https://arxiv.org/pdf/2508.09667.pdf) | [[Code]](https://github.com/GVCLab/GSFixer)

> **Core Innovation**  
> The core innovation lies in fusing 2D semantic and 3D geometric features as conditions to guide a video diffusion model for artifact restoration, along with a reference-guided trajectory sampling strategy for high-quality 3DGS reconstruction.

<details>
    <summary>Abstract</summary>
    Reconstructing 3D scenes using 3D Gaussian Splatting (3DGS) from sparse views is an ill-posed problem due to insufficient information, often resulting in noticeable artifacts. While recent approaches have sought to leverage generative priors to complete information for under-constrained regions, they struggle to generate content that remains consistent with input observations. To address this challenge, we propose GSFixer, a novel framework designed to improve the quality of 3DGS representations reconstructed from sparse inputs. The core of our approach is the reference-guided video restoration model, built upon a DiT-based video diffusion model trained on paired artifact 3DGS renders and clean frames with additional reference-based conditions. Considering the input sparse views as references, our model integrates both 2D semantic features and 3D geometric features of reference views extracted from the visual geometry foundation model, enhancing the semantic coherence and 3D consistency when fixing artifact novel views. Furthermore, considering the lack of suitable benchmarks for 3DGS artifact restoration evaluation, we present DL3DV-Res which contains artifact frames rendered using low-quality 3DGS. Extensive experiments demonstrate our GSFixer outperforms current state-of-the-art methods in 3DGS artifact restoration and sparse-view 3D reconstruction.
</details>

<details>
    <summary>Key points</summary>
    * Proposes a DiT-based video diffusion model for restoring artifact-prone views in 3DGS rendering.
    * Utilizes DINOv2 and VGGT to extract 2D semantic and 3D geometric features, enhancing view consistency and semantic fidelity.
    * Introduces a reference-guided trajectory sampling strategy to balance view coverage and restoration quality.
    * Presents DL3DV-Res dataset for evaluating 3DGS artifact restoration performance.
    * Significantly outperforms existing methods in sparse-view reconstruction and generalizes well across datasets.
</details>
</details>

---

<details>
<summary><b>CLIP-NeRF: Text-and-Image Driven Manipulation of Neural Radiance Fields</b></summary>

* **Authors:** Can Wang, Menglei Chai, Mingming He, Dongdong Chen, Jing Liao
* **arXiv ID:** 2112.05139
* **One-liner:** CLIP-NeRF presents a multi-modal 3D object manipulation method using the CLIP model，enabling users to manipulate NeRF via brief text prompts or example images.
* **Published in:** CVPR 2022
* **Links:** [[Paper]](https://arxiv.org/abs/2112.05139) | [[PDF]](https://arxiv.org/pdf/2112.05139.pdf) | [[Code]](https://github.com/cassiePython/CLIPNeRF)

> **Core Innovation**  
> The core innovation lies in the disentangled conditional NeRF architecture, which uses shape and appearance codes to separately control shape and appearance, combined with CLIP's multi-modal capabilities for text and image-driven 3D manipulation.

<details>
    <summary>Abstract</summary>
    We present CLIP-NeRF, a multi-modal 3D object manipulation method for neural radiance fields (NeRF). By leveraging the joint language-image embedding space of the recent Contrastive Language-Image Pre-Training (CLIP) model, we propose a unified framework that allows manipulating NeRF in a user-friendly way, using either a short text prompt or an exemplar image. Specifically, to combine the novel view synthesis capability of NeRF and the controllable manipulation ability of latent representations from generative models, we introduce a disentangled conditional NeRF architecture that allows individual control over both shape and appearance. This is achieved by performing the shape conditioning via applying a learned deformation field to the positional encoding and deferring color conditioning to the volumetric rendering stage. To bridge this disentangled latent representation to the CLIP embedding, we design two code mappers that take a CLIP embedding as input and update the latent codes to reflect the targeted editing. The mappers are trained with a CLIP-based matching loss to ensure the manipulation accuracy. Furthermore, we propose an inverse optimization method that accurately projects an input image to the latent codes for manipulation to enable editing on real images. We evaluate our approach by extensive experiments on a variety of text prompts and exemplar images and also provide an intuitive interface for interactive editing.
</details>

<details>
    <summary>Key points</summary>
    * Proposes a disentangled conditional NeRF architecture for separate shape and appearance control.
    * Designs a shape deformation network to update positional encodings via displacement vectors for precise shape control.
    * Leverages CLIP's text and image encoders to map text prompts or example images to the disentangled latent space for NeRF manipulation.
    * Introduces feedforward code mappers for fast inference, supporting editing of different objects within the same category.
    * Presents an inverse optimization method to project real images into latent codes for manipulation.
</details>
</details>

---

<details>
<summary><b>Genesis: Multimodal Driving Scene Generation with Spatio-Temporal and Cross-Modal Consistency</b></summary>

* **Authors:** Xiangyu Guo, Zhanqian Wu, Kaixin Xiong, Ziyang Xu, Lijun Zhou, Gangwei Xu, Shaoqing Xu, Haiyang Sun, Bing Wang, Guang Chen, Hangjun Ye, Wenyu Liu, Xinggang Wang
* **arXiv ID:** 2506.07497
* **One-liner:** Genesis presents a unified framework for jointly generating multi-view driving videos and LiDAR sequences, achieving spatio-temporal and cross-modal consistency.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2506.07497) | [[PDF]](https://arxiv.org/pdf/2506.07497.pdf) | [[Code]](https://github.com/xiaomi-research/genesis)

> **Core Innovation**  
> The core innovation of Genesis lies in its unified multimodal generation architecture that enables coherent evolution of video and LiDAR data across visual and geometric domains through shared conditional inputs and structured semantic guidance from DataCrafter.

<details>
    <summary>Abstract</summary>
    We present Genesis, a unified framework for joint generation of multi-view driving videos and LiDAR sequences with spatio-temporal and cross-modal consistency. Genesis employs a two-stage architecture that integrates a DiT-based video diffusion model with 3D-VAE encoding, and a BEV-aware LiDAR generator with NeRF-based rendering and adaptive sampling. Both modalities are directly coupled through a shared latent space, enabling coherent evolution across visual and geometric domains. To guide the generation with structured semantics, we introduce DataCrafter, a captioning module built on vision-language models that provides scene-level and instance-level supervision. Extensive experiments on the nuScenes benchmark demonstrate that Genesis achieves state-of-the-art performance across video and LiDAR metrics (FVD 16.95, FID 4.24, Chamfer 0.611), and benefits downstream tasks including segmentation and 3D detection, validating the semantic fidelity and practical utility of the generated data.
</details>

<details>
    <summary>Key points</summary>
    * Genesis uses a dual-branch design where both video and LiDAR generation are conditioned on shared inputs (e.g., scene descriptions and layouts), ensuring cross-modal consistency.
    * Built on vision-language models, DataCrafter generates scene-level and instance-level descriptions to provide detailed semantic guidance for multimodal generation.
    * The video branch leverages a DiT-based diffusion model with 3D-VAE encoding for fine-grained visual dynamics, while the LiDAR branch uses BEV representation and NeRF-based rendering for accurate geometry.
    * BEV features extracted from image pathways are incorporated into the LiDAR diffusion model to enhance consistency between geometric and visual domains.
</details>
</details>

---

<details>
<summary><b>Hunyuan3D-Omni: A Unified Framework for Controllable Generation of 3D Assets</b></summary>

* **Authors:** Team Hunyuan3D: Bowen Zhang, Chunchao Guo, Haolin Liu, Hongyu Yan, Huiwen Shi, Jingwei Huang, Junlin Yu, Kunhong Li, Linus, Penghao Wang, Qingxiang Lin, Sicong Liu, Xianghui Yang, Yixuan Tang, Yunfei Zhao, Zeqiang Lai, Zhihao Liang, Zibo Zhao
* **arXiv ID:** 2509.21245
* **One-liner:** Hunyuan3D-Omni is a unified framework for fine-grained, controllable 3D asset generation based on multi-modal conditioning signals.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2509.21245) | [[PDF]](https://arxiv.org/pdf/2509.21245.pdf) | [[Code]](https://github.com/Tencent-Hunyuan/Hunyuan3D-Omni)

> **Core Innovation**  
> The core innovation lies in the unified control encoder that integrates diverse conditioning signals like point clouds, voxels, skeletons, and bounding boxes. Combined with a progressive, difficulty-aware training strategy, it enables precise control over the 3D generation process.

<details>
    <summary>Abstract</summary>
    Recent advances in 3D-native generative models have accelerated asset creation for games, film, and design. However, most methods still rely primarily on image or text conditioning and lack fine-grained, cross-modal controls, which limits controllability and practical adoption. To address this gap, we present Hunyuan3D-Omni, a unified framework for fine-grained, controllable 3D asset generation built on Hunyuan3D 2.1. In addition to images, Hunyuan3D-Omni accepts point clouds, voxels, bounding boxes, and skeletal pose priors as conditioning signals, enabling precise control over geometry, topology, and pose. Instead of separate heads for each modality, our model unifies all signals in a single cross-modal architecture. We train with a progressive, difficulty-aware sampling strategy that selects one control modality per example and biases sampling toward harder signals (e.g., skeletal pose) while downweighting easier ones (e.g., point clouds), encouraging robust multi-modal fusion and graceful handling of missing inputs. Experiments show that these additional controls improve generation accuracy, enable geometry-aware transformations, and increase robustness for production workflows.
</details>

<details>
    <summary>Key points</summary>
    * Hunyuan3D-Omni introduces a unified framework supporting diverse conditioning signals for precise control over geometry, topology, and pose in 3D generation.
    * It designs a unified control encoder to convert various conditions into embeddings, which are combined with image features to achieve controllable 3D generation.
    * A progressive, difficulty-aware sampling strategy is proposed, prioritizing harder signals during training to enhance the model's robustness to multimodal fusion.
    * Experiments show that additional control signals improve generation accuracy, enhance geometric fidelity, and increase robustness in production workflows compared to image-only 3D generation.
</details>
</details>

---

<details>
<summary><b>LERF: Language Embedded Radiance Fields</b></summary>

* **Authors:** Justin Kerr, Chung Min Kim, Ken Goldberg, Angjoo Kanazawa, Matthew Tancik
* **arXiv ID:** 2303.09553
* **One-liner:** LERF optimizes CLIP language embeddings into a dense, multi-scale 3D field within NeRF, enabling real-time, open-vocabulary natural language queries of 3D scenes without fine-tuning or region proposals.
* **Published in:** ICCV 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2303.09553) | [[PDF]](https://arxiv.org/pdf/2303.09553.pdf) | [[Code]](https://github.com/kerrj/lerf)

> **Core Innovation**  
> The key innovation is learning a volumetric language field that renders CLIP embeddings through volume rendering, supervised by multi-scale feature pyramids from image crops, enabling hierarchical, view-consistent 3D semantic queries while preserving the original CLIP model's zero-shot capabilities.

<details>
    <summary>Abstract</summary>
    Humans describe the physical world using natural language to refer to specific 3D locations based on a vast range of properties: visual appearance, semantics, abstract associations, or actionable affordances. In this work we propose Language Embedded Radiance Fields (LERFs), a method for grounding language embeddings from off-the-shelf models like CLIP into NeRF, which enable these types of open-ended language queries in 3D. LERF learns a dense, multi-scale language field inside NeRF by volume rendering CLIP embeddings along training rays, supervising these embeddings across training views to provide multi-view consistency and smooth the underlying language field. After optimization, LERF can extract 3D relevancy maps for a broad range of language prompts interactively in real-time, which has potential use cases in robotics, understanding vision-language models, and interacting with 3D scenes. LERF enables pixel-aligned, zero-shot queries on the distilled 3D CLIP embeddings without relying on region proposals or masks, supporting long-tail open-vocabulary queries hierarchically across the volume. 
</details>

<details>
    <summary>Key points</summary>
    * Multi-Scale Language Field: Learns a dense 3D field conditioned on position and physical scale to capture hierarchical semantics
    * Volumetric CLIP Rendering: Renders CLIP embeddings along rays using NeRF's volume rendering weights, then normalizes to unit sphere
    * View-Consistency: Averaging embeddings across multiple training views produces more localized and 3D-consistent relevancy maps than 2D CLIP
    * No Fine-Tuning Required: Directly uses off-the-shelf CLIP model without training on segmentation datasets, preserving open-vocabulary capabilities
    * DINO Regularization: Incorporates self-supervised DINO features as a regularizer to improve field smoothness and object boundaries
    * Decoupled Architecture: Trains separate networks for language features (CLIP/DINO) and radiance field (RGB/density) to prevent language gradients from affecting geometry
</details>
</details>

---

<details>
<summary><b>Viewset Diffusion: (0-)Image-Conditioned 3D Generative Models from 2D Data</b></summary>

* **Authors:** Stanislaw Szymanowicz, Christian Rupprecht, Andrea Vedaldi
* **arXiv ID:** 2306.07881
* **One-liner:** Viewset Diffusion trains a diffusion model to generate viewsets (multi-view images) while internally reconstructing 3D radiance fields, enabling both probabilistic single-view reconstruction and unconditional 3D generation using only 2D multi-view supervision.
* **Published in:** ICCV 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2306.07881) | [[PDF]](https://arxiv.org/pdf/2306.07881.pdf) | [[Code]](https://github.com/szymanowiczs/viewset-diffusion)

> **Core Innovation**  
> The key innovation is framing 3D generation as viewset diffusion: by generating a set of 2D views and designing the denoiser as a 3D reconstructor followed by differentiable rendering, the model learns a 3D generative prior from 2D data alone, unifying ambiguous-aware reconstruction and generation in a single framework without requiring 3D ground truth.

<details>
    <summary>Abstract</summary>
    We present Viewset Diffusion, a diffusion-based generator that outputs 3D objects while only using multi-view 2D data for supervision. We note that there exists a one-to-one mapping between viewsets, i.e., collections of several 2D views of an object, and 3D models. Hence, we train a diffusion model to generate viewsets, but design the neural network generator to reconstruct internally corresponding 3D models, thus generating those too. We fit a diffusion model to a large number of viewsets for a given category of objects. The resulting generator can be conditioned on zero, one or more input views. Conditioned on a single view, it performs 3D reconstruction accounting for the ambiguity of the task and allowing to sample multiple solutions compatible with the input. The model performs reconstruction efficiently, in a feed-forward manner, and is trained using only rendering losses using as few as three views per viewset.
</details>

<details>
    <summary>Key points</summary>
    * Exploits the bijective mapping between viewsets and 3D models to enable 3D generation via 2D supervision only
    * The diffusion denoising function Φ reconstructs an explicit 3D radiance field (voxel grid) from noisy viewsets, decoded by differentiable rendering Ψ
    * Supports zero (unconditional), single, or few-view conditioning by applying different noise levels to different views (noised views for generation, clean views for conditioning)
    * 2D features are lifted to 3D via camera-aware unprojection, creating view-aligned feature volumes before aggregation
    * Attention-based Multi-view Fusion: Uses cross-attention to aggregate features from multiple views in an occlusion-aware manner, with learned per-category queries at coarsest level
    * Handles inherent ambiguity in single-view reconstruction by sampling from the learned distribution, producing diverse plausible 3D shapes instead of blurry averages
    * Requires only 3 views per object during training, significantly less than optimization-based methods (50+ views)
</details>
</details>

---

<details>
<summary><b>Aligned Novel View Image and Geometry Synthesis via Cross-modal Attention Instillation</b></summary>

* **Authors:** Min-Seop Kwak, Junho Kim, Sangdoo Yun, Dongyoon Han, Taekyoung Kim, Seungryong Kim, Jin-Hwa Kim
* **arXiv ID:** 2506.11924
* **One-liner:** MoAI is a diffusion-based warping-and-inpainting framework that synthesizes aligned novel view images and geometry from sparse unposed reference images by distilling attention maps from the image branch to a parallel geometry branch, enabling extrapolative view synthesis without dense posed data or pose-embedded models.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2506.11924) | [[PDF]](https://arxiv.org/pdf/2506.11924.pdf) | [[Code]](https://github.com/cvlab-kaist/MoAI)

> **Core Innovation**  
> The key innovation is cross-modal attention instillation (MoAI), where spatial attention maps from the image diffusion branch are injected into the geometry diffusion branch during both training and inference, creating a synergistic multi-task learning framework that regularizes image synthesis with deterministic geometry cues while enhancing geometry completion with rich semantic image features, ensuring precise alignment between generated images and geometry.

<details>
    <summary>Abstract</summary>
    We introduce a diffusion-based framework that performs aligned novel view image and geometry generation via a warping-and-inpainting methodology. Unlike prior methods that require dense posed images or pose-embedded generative models limited to in-domain views, our method leverages off-the-shelf geometry predictors to predict partial geometries viewed from reference images, and formulates novel-view synthesis as an inpainting task for both image and geometry. To ensure accurate alignment between generated images and geometry, we propose cross-modal attention distillation, where attention maps from the image diffusion branch are injected into a parallel geometry diffusion branch during both training and inference. This multi-task approach achieves synergistic effects, facilitating geometrically robust image synthesis as well as well-defined geometry prediction. We further introduce proximity-based mesh conditioning to integrate depth and normal cues, interpolating between point cloud and filtering erroneously predicted geometry from influencing the generation process. Empirically, our method achieves high-fidelity extrapolative view synthesis on both image and geometry across a range of unseen scenes, delivers competitive reconstruction quality under interpolation settings, and produces geometrically aligned colored point clouds for comprehensive 3D completion.
</details>

<details>
    <summary>Key points</summary>
    * Warping-and-Inpainting Paradigm: Leverages off-the-shelf geometry predictors to estimate partial point clouds from reference images, projecting them to target viewpoints as sparse * geometric conditioning for inpainting
    * Transfers attention maps from image U-Net to geometry U-Net, aligning modalities via shared structural information while preventing harmful feature mixing
    * Converts sparse point clouds to mesh via ball-pivoting, concatenating depth and normal maps to filter erroneous projections and provide denser geometric cues
    * Handles target viewpoints outside the convex hull of reference cameras, generating plausible occluded/unseen regions using learned scene priors
    * Works with unposed reference images, eliminating the need for known camera poses as required by prior diffusion-based NVS methods
    * Jointly predicts novel view images and pointmaps, producing geometrically consistent colored point clouds for comprehensive 3D completion
    * Geometry completion's deterministic nature provides stronger training signals to regularize the more ambiguous image inpainting task
    * Concatenates key/value features from all reference views with target queries, enabling occlusion-aware feature aggregation across arbitrary numbers of inputs
</details>
</details>

---

<details>
<summary><b>Scaling Transformer-Based Novel View Synthesis Models with Token Disentanglement and Synthetic Data</b></summary>

* **Authors:** Nithin Gopalakrishnan Nair, Srinivas Kaza, Xuan Luo, Vishal M. Patel, Stephen Lombardi, Jungyeon Park
* **arXiv ID:** 2509.06950
* **One-liner:** This paper introduces a Token-Disentangled (Tok-D) Transformer block that explicitly distinguishes source and target tokens through layer-wise modulation, enabling efficient and robust training on synthetic multi-view data generated by diffusion models, thereby achieving state-of-the-art novel view synthesis with improved generalization and reduced computational cost.
* **Published in:** ICCV 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2509.06950) | [[PDF]](https://arxiv.org/pdf/2509.06950.pdf) | [[Project Page]](https://scaling3dnvs.github.io/)

> **Core Innovation**  
> The core innovation is the Token-Disentangled (Tok-D) Transformer block, which addresses the fundamental inefficiency in decoder-only NVS architectures by using indicator-based modulation to separately process source and target tokens at each layer (pre-modulation for scaling/shifting attention and MLP layers, post-modulation for scaling). This disentanglement eliminates redundant feature alignment, improves computational efficiency, and critically, makes the model robust to synthetic data artifacts, enabling effective data scaling via synthetic augmentation—an approach that previously degraded baseline model performance.

<details>
    <summary>Abstract</summary>
    Large transformer-based models have made significant progress in generalizable novel view synthesis (NVS) from sparse input views, generating novel viewpoints without the need for test-time optimization. However, these models are constrained by the limited diversity of publicly available scene datasets, making most real-world (in-the-wild) scenes out-of-distribution. To overcome this, we incorporate synthetic training data generated from diffusion models, which improves generalization across unseen domains. While synthetic data offers scalability, we identify artifacts introduced during data generation as a key bottleneck affecting reconstruction quality. To address this, we propose a token disentanglement process within the transformer architecture, enhancing feature separation and ensuring more effective learning. This refinement not only improves reconstruction quality over standard transformers but also enables scalable training with synthetic data. As a result, our method outperforms existing models on both in-dataset and cross-dataset evaluations, achieving state-of-the-art results across multiple benchmarks while significantly reducing computational costs.
</details>

<details>
    <summary>Key points</summary>
    * Reveals that decoder-only NVS transformers (e.g., LVSM) waste capacity aligning source/target features and are vulnerable to source noise, limiting scalability.
    * Introduces token-type-aware modulation (δ indicator) that generates separate style vectors and scale/shift parameters for source vs. target tokens at every transformer layer.
    * The disentanglement mechanism prevents artifact propagation from synthetic source views to target generation, unlike naive transformers.
    * Uses CAT3D to generate multi-view data but crucially reverses the conditioning/target roles (real conditioned image becomes target, synthetic views become sources), forcing realistic output and robustness.
    * Proposes 3D-consistent noise initialization for diffusion models via warping and noise blending to improve synthetic data quality.
</details>
</details>

---

<details>
<summary><b>NeRF-HuGS: Improved Neural Radiance Fields in Non-static Scenes Using Heuristics-Guided Segmentation</b></summary>

* **Authors:** Jiahao Chen, Yipeng Qin, Lingjie Liu, Jiangbo Lu, Guanbin Li
* **arXiv ID:** 2403.17537
* **One-liner:** NeRF-HuGS introduces a "Heuristics-Guided Segmentation" paradigm that synergizes hand-crafted cues (SfM features & color residuals) with SAM to accurately separate static scenes from transient distractors without prior knowledge, significantly boosting NeRF quality in non-static environments.
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2403.17537) | [[PDF]](https://arxiv.org/pdf/2403.17537.pdf) | [[Code]](https://github.com/cnhaox/NeRF-HuGS)

> **Core Innovation**  
> The core innovation is the Heuristics-Guided Segmentation (HuGS) framework that reframes static/transient separation as a collaborative process: instead of relying purely on heuristics or segmentation, it uses complementary heuristics (SfM-based for high-frequency textures, color-residual for low-frequency) to provide coarse static cues that guide SAM into producing precise, boundary-aware static maps, thus overcoming the fundamental trade-off between generality and accuracy in prior methods.

<details>
    <summary>Abstract</summary>
    Neural Radiance Field (NeRF) has been widely recognized for its excellence in novel view synthesis and 3D scene reconstruction. However, their effectiveness is inherently tied to the assumption of static scenes, rendering them susceptible to undesirable artifacts when confronted with transient distractors such as moving objects or shadows. In this work, we propose a novel paradigm, namely "Heuristics-Guided Segmentation" (HuGS), which significantly enhances the separation of static scenes from transient distractors by harmoniously combining the strengths of hand-crafted heuristics and state-of-the-art segmentation models, thus significantly transcending the limitations of previous solutions. Furthermore, we delve into the meticulous design of heuristics, introducing a seamless fusion of Structure-from-Motion (SfM)-based heuristics and color residual heuristics, catering to a diverse range of texture profiles. Extensive experiments demonstrate the superiority and robustness of our method in mitigating transient distractors for NeRFs trained in non-static scenes.
</details>

<details>
    <summary>Key points</summary>
    * NeRF's static scene assumption causes artifacts in real-world data with transient distractors like moving objects/shadows
    * Static objects' SfM feature points have significantly more cross-view matches than transient ones, and high/low-frequency textures require different heuristics
    * HuGS thresholds SfM static features → SAM generates initial static map → partially-trained Nerfacto provides color residual map → dual heuristics fusion → SAM again for final static mask
</details>
</details>

---

<details>
<summary><b>RealFusion: 360° Reconstruction of Any Object from a Single Image</b></summary>

* **Authors:** Luke Melas-Kyriazi, Christian Rupprecht, Iro Laina, Andrea Vedaldi
* **arXiv ID:** 2302.10663
* **One-liner:** Proposes RealFusion, a method that uses single-image textual inversion to generate custom prompts for Stable Diffusion, combined with SDS loss and efficient InstantNGP reconstruction, enabling 360° photorealistic 3D reconstruction of arbitrary objects from a single image.
* **Published in:** CVPR 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2302.10663) | [[PDF]](https://arxiv.org/pdf/2302.10663.pdf) | [[Code]](https://github.com/lukemelas/realfusion)

> **Core Innovation**  
> The core innovation is the single-image textual inversion technique that creates a custom text token embedding from a single input image (via heavy augmentations), which conditions the diffusion model to generate view-consistent, object-specific priors—bridging the gap between generic 2D diffusion and precise single-view 3D reconstruction without any 3D supervision.

<details>
    <summary>Abstract</summary>
    We consider the problem of reconstructing a full 360° photographic model of an object from a single image of it. We do so by fitting a neural radiance field to the image, but find this problem to be severely ill-posed. We thus take an off-the-self conditional image generator based on diffusion and engineer a prompt that encourages it to "dream up" novel views of the object. Using an approach inspired by DreamFields and DreamFusion, we fuse the given input view, the conditional prior, and other regularizers in a final, consistent reconstruction. We demonstrate state-of-the-art reconstruction results on benchmark images when compared to prior methods for monocular 3D reconstruction of objects. Qualitatively, our reconstructions provide a faithful match of the input view and a plausible extrapolation of its appearance and 3D shape, including to the side of the object not visible in the image.
</details>

<details>
    <summary>Key points</summary>
    * Methodology: Combines two simultaneous objectives—reconstruction loss (fitting the input view) and SDS-based prior loss (constraining novel views using Stable Diffusion).
    * Single-image textual inversion optimizes a custom token ⟨e⟩ using heavily-augmented versions of the input image, making the diffusion model object-specific rather than category-generic.
    * Uses InstantNGP for fast training and introduces coarse-to-fine training to reduce surface artifacts.
    * Adds normal smoothness regularization in 2D and mask loss to improve geometry.
</details>
</details>

---

<details>
<summary><b>Lift3D: Synthesize 3D Training Data by Lifting 2D GAN</b></summary>

* **Authors:** Lele Chen, Guosheng Lin, Shujun Wang, Vladlen Koltun
* **arXiv ID:** 2304.03526
* **One-liner:** Distills pretrained 2D GANs into 3D NeRFs to generate labeled 3D training data for downstream tasks.
* **Published in:** CVPR 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2304.03526) | [[PDF]](https://arxiv.org/pdf/2304.03526.pdf) | [[Code]](https://github.com/LeapLabTHU/Lift3D)

> **Core Innovation**
> Proposes a generative pipeline that "lifts" the capabilities of existing high-quality 2D GANs (like StyleGAN) into 3D space (3D NeRF). Through this distillation process, Lift3D generates images with explicit 3D geometry and viewpoint control, enabling the automatic creation of 3D-annotated datasets (pose, shape) for downstream 3D recognition tasks.

<details>
    <summary>Abstract</summary>
    Training 3D vision models often requires large amounts of annotated 3D data, which is expensive and hard to scale. We propose Lift3D, a novel method to synthesize 3D training data by lifting a 2D GAN to a 3D generative radiance field. Unlike existing 3D GANs that require 3D data or multi-view images, Lift3D relies solely on a 2D GAN trained on single-view 2D image collections. We distill the latent space of the 2D GAN into a NeRF-based 3D generator, inheriting the diversity and realism of the 2D GAN while gaining 3D consistency. Experiments show that data synthesized by Lift3D significantly boosts the performance of downstream tasks, such as 3D pose estimation and shape reconstruction, on real-world datasets.
</details>

<details>
    <summary>Key points</summary>
    * 2D-to-3D Distillation: Uses StyleGAN as a teacher network to guide the learning of a Conditional Radiance Field.
    * Data Generator: Automatically generates datasets with precise 3D annotations (pose, viewpoint, shape).
    * Downstream Application: Significantly improves 3D pose estimation and reconstruction in data-scarce scenarios.
    * Disentangled Control: Achieves independent control over texture, shape, and viewpoint of generated objects.
</details>
</details>

---

<details>
<summary><b>SKED: Sketch-guided Text-to-3D Editing</b></summary>

* **Authors:** Gang Li, Heliang Zheng, Chaoyue Song, Changwen Chen, et al.
* **arXiv ID:** 2303.10735
* **One-liner:** Combines sketch guidance with text prompts to enable precise geometric and appearance editing of 3D NeRF scenes. 
* **Published in:** ICCV 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2303.10735) | [[PDF]](https://arxiv.org/pdf/2303.10735.pdf) | [[Code]](https://github.com/sked-3d/SKED)

> **Core Innovation**
> Addresses the lack of geometric control in text-only 3D editing by introducing a "Sketch-guided" mechanism. By drawing a sketch on a 2D view and projecting constraints into 3D space (via multi-view consistency losses), SKED allows users to precisely modify object shape and structure while using text prompts for appearance, achieving "draw-what-you-get" 3D editing.

<details>
    <summary>Abstract</summary>
    Existing text-to-3D editing methods primarily rely on text prompts, making precise geometric control of 3D shapes difficult. To address this, we propose SKED, a sketch-guided text-to-3D editing framework. Users can provide a simple sketch along with a text prompt to modify an existing Neural Radiance Field (NeRF). We design a novel sketch refinement loss to ensure the edited 3D geometry closely aligns with the user's sketch contours, while leveraging pre-trained diffusion models to maintain realistic appearance. Additionally, we introduce multi-view consistency constraints to prevent sketch editing from degrading other views. Experiments demonstrate that SKED achieves more precise geometric editing than text-only methods while preserving original scene characteristics.
</details>

<details>
    <summary>Key points</summary>
    * Multi-modal Input: Uses both sketches (for geometry) and text (for semantics/appearance) for editing.
    * Sketch Loss: Introduces a Silhouette Loss to enforce 3D density fields to match 2D sketch contours.
    * Local Editing: Capable of precisely targeting and modifying specific parts (e.g., adding arms to a chair) without destroying the global structure.
    * NeRF-based: Optimizes directly on Instant-NGP or NeRF representations.
</details>
</details>

---

<details>
<summary><b>ICE-G: Image Conditional Editing of 3D Gaussian Splats</b></summary>

* **Authors:** Jamyong Han, Yukyung Choi, et al.
* **arXiv ID:** 2404.12781
* **One-liner:** The first framework enabling image-conditioned editing of 3D Gaussian Splats for fine-grained texture and geometry modifications.
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2404.12781) | [[PDF]](https://arxiv.org/pdf/2404.12781.pdf) | [[Code]](https://github.com/sked-3d/SKED) *(Note: Link might vary)*

> **Core Innovation**
> Addressing the difficulty of controlled editing in 3D Gaussian Splatting (3DGS), ICE-G proposes an image-conditional editing approach. It allows users to modify a single-view image (e.g., adding stickers, changing textures, or local deformation) to drive the update of the entire 3D Gaussian field. The core lies in an efficient Gaussian attribute update mechanism that accurately back-propagates 2D image changes into 3D Gaussian parameters while maintaining multi-view consistency.

<details>
    <summary>Abstract</summary>
    3D Gaussian Splatting (3DGS) has recently revolutionized real-time radiance field rendering, but controlled editing remains a challenge. We propose ICE-G, an image-conditional editing framework for 3D Gaussian Splats. Unlike methods relying on text prompts or complex 3D interactions, ICE-G allows users to directly edit a rendered 2D image and seamlessly propagates these edits to the 3D model. We introduce an optimization strategy combining 2D image guidance with 3D regularization, ensuring edits look natural in the target view and maintain geometric coherence across other views. ICE-G supports various edit types, including stylization, re-texturing, and geometric deformation.
</details>

<details>
    <summary>Key points</summary>
    * **Image-Driven Editing:** Users simply edit a screenshot, and the algorithm updates the 3D model automatically.
    * **Gaussian Attribute Update:** Specially designed to update 3DGS position, covariance, and color attributes without artifacts.
    * **Real-time Feedback:** Leverages 3DGS rendering speed for near real-time editing previews.
    * **Versatility:** Supports local texture modification, object removal, and shape adjustment.
</details>
</details>

---

<details>
<summary><b>DDPO: Denoising Diffusion Policy Optimization</b></summary>

* **Authors:** Kevin Black, Michael Janner, Yilun Du, Ilya Kostrikov, Sergey Levine
* **arXiv ID:** 2305.16147
* **One-liner:** Models the diffusion denoising process as a multi-step MDP to apply Policy Gradient directly for alignment.
* **Published in:** ICLR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2305.16147) | [[PDF]](https://arxiv.org/pdf/2305.16147.pdf) | [[Code]](https://github.com/kvablack/ddpo-pytorch)

> **Core Innovation**
> Traditional fine-tuning of diffusion models often requires expensive backpropagation through time. DDPO treats the iterative denoising process as a multi-step Markov Decision Process (MDP) in Reinforcement Learning. This allows the use of standard policy gradient methods (like PPO) to optimize diffusion models against arbitrary, non-differentiable reward functions (such as aesthetic scores or compressibility) without differentiating through the entire sampling chain.

<details>
    <summary>Abstract</summary>
    Diffusion models are not just generative models but also multi-step decision-makers. We introduce Denoising Diffusion Policy Optimization (DDPO), a method for fine-tuning diffusion models directly against non-differentiable objectives using reinforcement learning. By framing the denoising process as a multi-step MDP, we show that policy gradient algorithms can effectively optimize image generation for complex rewards like human perception, aesthetic scores, or structural consistency. DDPO is more stable than prior methods, does not require training surrogate reward models for gradients, and adapts to tasks difficult to solve via prompt engineering alone.
</details>

<details>
    <summary>Key points</summary>
    * **RL Perspective:** Treats denoising step $t$ as the state and the network output as the action.
    * **No Backprop-Through-Time:** Avoids the memory bottleneck of differentiating through the ODE/SDE solver.
    * **Black-box Rewards:** Can optimize for JPEG compressibility, aesthetic predictors, or any external metric.
    * **Performance:** Outperforms Classifier Guidance on the text-alignment vs. image-quality Pareto frontier.
</details>
</details>

---

<details>
<summary><b>AlignProp: Aligning Diffusion Models with Downstream Reward Functions</b></summary>

* **Authors:** Mihir Prabhudesai, Anirudh Goyal, Deepak Pathak, Katerina Fragkiadaki
* **arXiv ID:** 2310.03739
* **One-liner:** Enables end-to-end backpropagation through the entire diffusion denoising process using gradient checkpointing to optimize rewards.
* **Published in:** NeurIPS 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2310.03739) | [[PDF]](https://arxiv.org/pdf/2310.03739.pdf) | [[Code]](https://github.com/mihirp1998/AlignProp)

> **Core Innovation**
> Unlike DDPO which uses Reinforcement Learning, AlignProp opts for direct backpropagation through the denoising chain. To address the memory explosion of backpropagating through deep iterative solvers, it utilizes gradient checkpointing. This allows the model to update weights directly based on the gradients of downstream reward functions (e.g., semantic segmentation consistency), offering theoretically higher sample efficiency than RL-based methods.

<details>
    <summary>Abstract</summary>
    Text-to-image diffusion models often struggle to satisfy complex downstream objectives, such as specific object counts or physical constraints. AlignProp proposes an end-to-end fine-tuning method that unrolls the denoising process and backpropagates the gradients of the reward function to update the diffusion model. To make this computationally feasible, we use gradient checkpointing to reduce memory consumption. Experiments show that AlignProp achieves higher reward images more efficiently than RL-based methods (like DDPO) for tasks like semantic alignment and object counting, while maintaining diversity.
</details>

<details>
    <summary>Key points</summary>
    * **End-to-End Backprop:** Calculates loss on the final generated image and propagates it back to model parameters through the solver.
    * **Memory Efficient:** Makes fine-tuning feasible on consumer GPUs via randomized gradient checkpointing.
    * **Vs. RL:** By leveraging the gradient of the reward function (if differentiable), it often converges faster with lower variance than DDPO.
    * **Applications:** Particularly effective for tasks requiring precise semantic control or physical consistency.
</details>
</details>

---

<details>
<summary><b>R-DPO: Robust Direct Preference Optimization</b></summary>

* **Authors:** T. Chowdhury, R. Kannan, et al.
* **arXiv ID:** 2402.10207
* **One-liner:** Enhances DPO's robustness against noisy preference labels through regularization or re-weighting mechanisms.
* **Published in:** 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2402.10207) | [[PDF]](https://arxiv.org/pdf/2402.10207.pdf)

> **Core Innovation**
> Standard Direct Preference Optimization (DPO) assumes that human or model preference data is ground truth. However, real-world datasets often contain noise (mislabeled preferences). R-DPO (Robust DPO) modifies the DPO loss function (e.g., using probabilistic thresholds or robust loss variants) to allow the model to down-weight or ignore potentially mislabeled pairs during training, preventing overfitting to erroneous signals.

<details>
    <summary>Abstract</summary>
    Direct Preference Optimization (DPO) has become a leading method for aligning LLMs with human preferences. However, DPO is sensitive to noisy labels in the preference dataset. We propose R-DPO (Robust DPO), a variant designed to withstand label noise. By analyzing DPO's behavior under noisy conditions, we introduce a loss function that dynamically adjusts weights based on sample confidence. Experiments show R-DPO significantly outperforms standard DPO and IPO on datasets with 10-30% label noise.
</details>

<details>
    <summary>Key points</summary>
    * **Label Noise Robustness:** Mitigates performance degradation on "dirty" preference datasets.
    * **Dynamic Weighting:** Similar to curriculum learning, it reduces the gradient impact of high-uncertainty samples.
    * **Stability:** Offers smoother training curves and less susceptibility to reward hacking compared to vanilla DPO.
</details>
</details>

---

<details>
<summary><b>TTPO: Test-Time Policy Optimization</b></summary>

* **Authors:** Google DeepMind / Various (2024 Context)
* **arXiv ID:** 2409.13035
* **One-liner:** Dynamically optimizes the model policy during inference time to adapt to the specific current input.
* **Published in:** 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2409.13035) | [[PDF]](https://arxiv.org/pdf/2409.13035.pdf)

> **Core Innovation**
> Traditional alignment happens during training. TTPO shifts the optimization process to the inference stage. For a given input prompt, the model utilizes a lightweight reward model or constraints to perform real-time gradient updates or search over its output distribution. This allows the model to "adapt on the fly" to specific, unseen, or difficult queries without permanently altering base model weights (or using only temporary updates).

<details>
    <summary>Abstract</summary>
    Despite extensive instruction tuning and RLHF, LLMs often fail on out-of-distribution or highly complex queries. TTPO proposes a mechanism to boost model performance at test-time. By introducing an optimization loop during inference, we adjust the generated token sequence based on input-specific reward signals. This approach requires no large-scale retraining and allows the model to dynamically "think" and self-correct based on the current context. Results show TTPO outperforms purely pre-trained/fine-tuned models on complex reasoning and constrained generation tasks.
</details>

<details>
    <summary>Key points</summary>
    * **Test-Time Compute:** Trades increased inference latency for higher quality outputs (akin to System 2 thinking).
    * **Dynamic Adaptation:** Finds the optimal solution for the specific prompt rather than relying on a generic average policy.
    * **Optimization:** Can involve gradient-based updates to latents/activations or sophisticated search strategies (like Best-of-N on steroids).
</details>
</details>

---

<details>
<summary><b>SPO: Stepwise Preference Optimization for Long-form Generation</b></summary>

* **Authors:** Z. Wang, Y. Zhang, et al.
* **arXiv ID:** 2406.04376
* **One-liner:** Refines preference optimization from "response-level" to "step-level," specifically for aligning long-chain reasoning and generation.
* **Published in:** ICML 2024 / arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2406.04376) | [[PDF]](https://arxiv.org/pdf/2406.04376.pdf)

> **Core Innovation**
> Traditional DPO (Direct Preference Optimization) compares full responses, which is inefficient for long Chain-of-Thought (CoT) tasks where a wrong final answer might contain correct intermediate steps (or vice versa). SPO (Stepwise Preference Optimization) introduces a fine-grained alignment method that identifies and optimizes individual "steps" within the reasoning process, precisely rewarding correct reasoning paths and penalizing logical breaks.

<details>
    <summary>Abstract</summary>
    Human preference alignment is crucial for Large Language Models (LLMs). However, existing methods like DPO focus on preferences for holistic responses, neglecting the internal stepwise structure in long-form generation (e.g., math reasoning, coding). We propose Stepwise Preference Optimization (SPO), a method designed to align the stepwise generation process. SPO optimizes the policy based on step-level preference signals, allowing for more precise localization of reasoning errors. Experiments show that SPO significantly outperforms DPO and PPO on mathematical reasoning and long-text generation tasks.
</details>

<details>
    <summary>Key points</summary>
    * **Fine-grained Alignment:** Solves the sparse signal problem of "coarse" DPO in long-context tasks.
    * **Step-level Reward:** Similar to Process Supervision but integrated directly into the preference optimization framework.
    * **Performance:** Achieves superior results on reasoning-intensive benchmarks like Math and GSM8K.
</details>
</details>

---

<details>
<summary><b>Diffusion of Thoughts: Chain-of-Thought Reasoning in Diffusion Language Models</b></summary>

* **Authors:** J. Ye, X. Pan, et al.
* **arXiv ID:** 2402.07754
* **One-liner:** Introduces Chain-of-Thought (CoT) capabilities into diffusion language models, enabling multi-step reasoning and self-correction via the denoising process.
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2402.07754) | [[PDF]](https://arxiv.org/pdf/2402.07754.pdf)

> **Core Innovation**
> Traditional autoregressive LLMs generate token-by-token, making global planning difficult. This paper proposes **Diffusion of Thoughts (DoT)**, leveraging the iterative denoising process of diffusion models to simulate the thinking process. In DoT, each diffusion step is treated as a "thinking step." This allows the model to perform implicit self-correction and global reasoning in the latent space before settling on a final answer, mitigating the error accumulation typical of left-to-right generation.

<details>
    <summary>Abstract</summary>
    Diffusion models have revolutionized image generation but are less explored for text reasoning. We propose Diffusion of Thoughts (DoT), a paradigm that enables Chain-of-Thought reasoning within diffusion language models. Unlike autoregressive CoT which explicitly generates intermediate tokens, DoT utilizes the temporal dimension of the diffusion process as an implicit reasoning chain. As the diffusion steps progress, the model "thinks" its way from a noisy state to a clear reasoning path. Experiments show DoT outperforms traditional diffusion text generation on math and logic tasks and allows trading "compute for quality" by increasing diffusion steps.
</details>

<details>
    <summary>Key points</summary>
    * **Implicit Reasoning:** Maps diffusion denoising steps to thinking depth.
    * **Non-Autoregressive:** Enables global adjustment during generation, avoiding the "error propagation" of standard LLMs.
    * **Compute-Quality Trade-off:** Similar to OpenAI o1 concepts, one can increase inference (denoising) steps to solve harder problems.
</details>
</details>

---

<details>
<summary><b>LayoutPrompter: Awakening the Power of Large Language Models for Layout Generation</b></summary>

* **Authors:** J. Lin, J. Guo, et al.
* **arXiv ID:** 2311.06495
* **One-liner:** Leverages Chain-of-Thought (CoT) prompting to unlock the layout generation capabilities of LLMs without fine-tuning.
* **Published in:** CVPR 2024 (Highlight)
* **Links:** [[Paper]](https://arxiv.org/abs/2311.06495) | [[PDF]](https://arxiv.org/pdf/2311.06495.pdf) | [[Code]](https://github.com/Layout-Prompter/LayoutPrompter)

> **Core Innovation**
> Prior to LayoutPrompter, layout generation relied on specialized models (GANs/Transformers). This paper demonstrates that by using a **Layout-CoT** promoting strategy—first describing constraints and plans, then generating coordinates—one can "awaken" the layout design capabilities of general-purpose LLMs (like GPT-4). This reframes layout generation as a sequence reasoning task rather than just image generation.

<details>
    <summary>Abstract</summary>
    Conditional layout generation is central to graphic design, but existing methods rely on domain-specific fine-tuned models. We introduce LayoutPrompter, a training-free method leveraging Large Language Models (LLMs) for layout generation. The core is a strategy called Layout-CoT (Chain-of-Thought). By demonstrating the thought process of "Input Constraints -> Planning -> Output Coordinates," we guide the LLM to understand layout rules. Experiments show that LayoutPrompter achieves performance comparable to or better than state-of-the-art supervised models on multiple benchmarks without any fine-tuning.
</details>

<details>
    <summary>Key points</summary>
    * **Layout-CoT Strategy:** Decomposes the task into planning (area division) and refinement (coordinate generation).
    * **Training-free:** Directly utilizes the generalization power of pre-trained LLMs for posters, webpages, etc.
    * **Dynamic Context:** Retrieves the most similar layout examples dynamically for In-context Learning.
</details>
</details>

---

