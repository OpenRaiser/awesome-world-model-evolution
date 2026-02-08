<p align="center">
  <a href="README.md">English</a> | <a href="README_zh.md">中文</a>
</p>

### Spatial + Temporal Consistency

Capability Profile: Models that maintain 3D spatial structure while simulating temporal dynamics, but may have limited language understanding or controllability.

Significance: These models represent crucial technical achievements in understanding "how the 3D world moves," forming the physics engine component of world models.

#### Representative Works

<details>
<summary><b>DUSt3R: Geometric 3D Vision Made Easy</b></summary>

* **Authors:** Shuzhe Wang, Vincent Leroy, Yohann Cabon, Boris Chidlovskii, Jérôme Revaud  
* **arXiv ID:** 2312.14132  
* **One-liner:** Dense, unconstrained stereo 3D reconstruction from arbitrary image collections with no calibration/preset pose required  
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2312.14132) | [[PDF]](https://arxiv.org/pdf/2312.14132.pdf)

> **Core Innovation**  
> Introduces a paradigm-shifting pipeline that replaces traditional multi-view stereo (MVS): it directly regresses dense point-maps without ever estimating camera intrinsics or extrinsics. By unifying single- and multi-view depth estimation, camera pose recovery, and reconstruction into one network, the approach excels even in casual, “in-the-wild” capture scenarios.

<details>
    <summary>Abstract</summary>
    Multi-view stereo reconstruction (MVS) in the wild requires to first estimate the camera parameters e.g. intrinsic and extrinsic parameters. These are usually tedious and cumbersome to obtain, yet they are mandatory to triangulate corresponding pixels in 3D space, which is the core of all best performing MVS algorithms. In this work, we take an opposite stance and introduce DUSt3R, a radically novel paradigm for Dense and Unconstrained Stereo 3D Reconstruction of arbitrary image collections, i.e. operating without prior information about camera calibration nor viewpoint poses. We cast the pairwise reconstruction problem as a regression of pointmaps, relaxing the hard constraints of usual projective camera models. We show that this formulation smoothly unifies the monocular and binocular reconstruction cases. In the case where more than two images are provided, we further propose a simple yet effective global alignment strategy that expresses all pairwise pointmaps in a common reference frame. We base our network architecture on standard Transformer encoders and decoders, allowing us to leverage powerful pretrained models. Our formulation directly provides a 3D model of the scene as well as depth information, but interestingly, we can seamlessly recover from it, pixel matches, relative and absolute camera. Exhaustive experiments on all these tasks showcase that the proposed DUSt3R can unify various 3D vision tasks and set new SoTAs on monocular/multi-view depth estimation as well as relative pose estimation. In summary, DUSt3R makes many geometric 3D vision tasks easy.
</details>

<details>
    <summary>Key points</summary>
    * Reformulates multi-view stereo as point-map regression, removing need for camera intrinsics/extrinsics.  
    * Unified framework that handles monocular and multi-view reconstruction seamlessly.  
    * Uses Transformer-based architecture to directly predict dense 3D geometry from images.  
    * Achieves state-of-the-art on depth, pose, and reconstruction benchmarks under unconstrained settings.  
</details>
</details>

---

<details>
<summary><b>4D Gaussian Splatting for Real-Time Dynamic Scene Rendering</b></summary>

* **Authors:** Guanjun Wu, Taoran Yi, Jiemin Fang, Lingxi Xie, Xiaopeng Zhang, Wei Wei, Wenyu Liu, Qi Tian, Xinggang Wang  
* **arXiv ID:** 2310.08528  
* **One-liner:** A holistic 4D Gaussian splatting representation for dynamic scenes enabling real-time rendering of space-time geometry and appearance  
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2310.08528) | [[PDF]](https://arxiv.org/pdf/2310.08528.pdf) | [[Code]](https://github.com/hustvl/4DGaussians)

> **Core Innovation**  
> Proposes 4D Gaussian Splatting (4D-GS) that models space and time jointly: each Gaussian primitive carries spatio-temporal extent, dramatically boosting both training speed and real-time rendering performance on dynamic scenes.

<details>
    <summary>Abstract</summary>
    Representing and rendering dynamic scenes has been an important but challenging task. Especially, to accurately model complex motions, high efficiency is usually hard to guarantee. To achieve real-time dynamic scene rendering while also enjoying high training and storage efficiency, we propose 4D Gaussian Splatting (4D-GS) as a holistic representation for dynamic scenes rather than applying 3D-GS for each individual frame. In 4D-GS, a novel explicit representation containing both 3D Gaussians and 4D neural voxels is proposed. A decomposed neural voxel encoding algorithm inspired by HexPlane is proposed to efficiently build Gaussian features from 4D neural voxels and then a lightweight MLP is applied to predict Gaussian deformations at novel timestamps. Our 4D-GS method achieves real-time rendering under high resolutions, 82 FPS at an 800800 resolution on an RTX 3090 GPU while maintaining comparable or better quality than previous state-of-the-art methods.
</details>

<details>
    <summary>Key points</summary>
    * Introduces 4D Gaussian primitives that model space + time jointly (rather than separate per-frame 3D models).  
    * Enables real-time rendering (30+ fps) for dynamic scenes with high resolution.  
    * Efficient deformation field network and splatting renderer designed for dynamic geometry + appearance.  
    * Training and storage efficiency improved relative to prior dynamic scene representations.  
</details>
</details>

---

<details>
<summary><b>Neural Scene Flow Fields for Space-Time View Synthesis of Dynamic Scenes</b></summary>

* **Authors:** Zhengqi Li, Simon Niklaus, Noah Snavely, Oliver Wang  
* **arXiv ID:** 2011.13084  
* **One-liner:** A continuous time-varying function representation capturing appearance, geometry and motion (scene flow) to perform novel view & time synthesis from monocular video  
* **Published in:** CVPR 2021  
* **Links:** [[Paper]](https://arxiv.org/abs/2011.13084) | [[PDF]](https://arxiv.org/pdf/2011.13084.pdf) | [[Code]](https://github.com/zhengqili/Neural-Scene-Flow-Fields)

> **Core Innovation**  
> Proposes Neural Scene Flow Fields (NSFF): a time-varying continuous representation that jointly encodes geometry, appearance, and 3D scene flow for dynamic scenes. Trained on monocular videos with known camera trajectories, NSFF enables simultaneous novel-view and temporal interpolation.

<details>
    <summary>Abstract</summary>
    We present a method to perform novel view and time synthesis of dynamic scenes, requiring only a monocular video with known camera poses as input. To do this, we introduce Neural Scene Flow Fields, a new representation that models the dynamic scene as a time-variant continuous function of appearance, geometry, and 3D scene motion. Our representation is optimized through a neural network to fit the observed input views. We show that our representation can be used for complex dynamic scenes, including thin structures, view-dependent effects, and natural degrees of motion. We conduct a number of experiments that demonstrate our approach significantly outperforms recent monocular view synthesis methods, and show qualitative results of space-time view synthesis on a variety of real-world videos.
</details>

<details>
    <summary>Key points</summary>
    * Represents dynamic scenes by a continuous 5D/6D function (space + time + view) capturing geometry, appearance & scene-flow.  
    * Optimized from input monocular video + known camera poses (no multi-view capture required).  
    * Supports novel view and novel time synthesis (i.e., view + motion interpolation).  
    * Handles challenging dynamic phenomena such as thin structures, specularities and complex motion.  
</details>
</details>

---

<details>
<summary><b>CoTracker: It is Better to Track Together</b></summary>

* **Authors:** Nikita Karaev, Ignacio Rocco, Benjamin Graham, Natalia Neverova, Andrea Vedaldi, Christian Rupprecht 
* **arXiv ID:** 2307.07635  
* **One-liner:** A transformer-based model that jointly tracks tens of thousands of 2D points across video frames rather than treating them independently  
* **Published in:** ECCV 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2307.07635) | [[PDF]](https://arxiv.org/pdf/2307.07635.pdf) | [[Code]](https://github.com/facebookresearch/co-tracker)

> **Core Innovation**  
> Introduces CoTracker: a Transformer-based architecture that jointly tracks thousands of 2D point trajectories, explicitly modeling inter-point dependencies to boost tracking accuracy for occluded or out-of-view points.

<details>
    <summary>Abstract</summary>
    We introduce CoTracker, a transformer-based model that tracks a large number of 2D points in long video sequences. Differently from most existing approaches that track points independently, CoTracker tracks them jointly, accounting for their dependencies. We show that joint tracking significantly improves tracking accuracy and robustness, and allows CoTracker to track occluded points and points outside of the camera view. We also introduce several innovations for this class of trackers, including using token proxies that significantly improve memory efficiency and allow CoTracker to track 70k points jointly and simultaneously at inference on a single GPU. CoTracker is an online algorithm that operates causally on short windows. However, it is trained utilizing unrolled windows as a recurrent network, maintaining tracks for long periods of time even when points are occluded or leave the field of view. Quantitatively, CoTracker substantially outperforms prior trackers on standard point-tracking benchmarks.
</details>

<details>
    <summary>Key points</summary>
    * Joint point-tracking: tracks many points together, modeling correlations rather than independent tracking.  
    * Uses transformer architecture with token proxies to manage memory and scale to tens of thousands of points.  
    * Works online in causal short windows but is trained as an unrolled long-window recurrent to handle long sequences and occlusion.  
    * Significant improvements in robustness and accuracy over traditional independent point tracking methods, especially under occlusion and out-of-view.  
</details>
</details>

---

<details>
<summary><b>GEN3C: 3D-Informed World-Consistent Video Generation with Precise Camera Control</b></summary>

* **Authors:** Xuanchi Ren, Tianchang Shen, Jiahui Huang, Huan Ling, Yifan Lu, Merlin Nimier-David, Thomas Müller, Alexander Keller, Sanja Fidler, Jun Gao
* **arXiv ID:** 2503.03751
*   **One-liner:** Image (first frame/seed frame) → Video.3D caching + precise camera control, emphasizing world-consistent video generation
*   **Published in:** CVPR 2025
*   **Links:** [[Paper]](https://arxiv.org/abs/2503.03751) | [[PDF]](https://arxiv.org/pdf/2503.03751) | [[Code]](https://github.com/nv-tlabs/GEN3C)
   
> **Core Innovation**  
> Turns camera poses into directly-renderable conditions via a 3D cache, leaving the model to fill only the dis-occluded regions for the new viewpoint—eliminating both imprecise camera control and temporal inconsistency in one shot.

<details>
    <summary>Abstract</summary>
    We present GEN3C, a generative video model with precise Camera Control and temporal 3D Consistency. Prior video models already generate realistic videos, but they tend to leverage little 3D information, leading to inconsistencies, such as objects popping in and out of existence. Camera control, if implemented at all, is imprecise, because camera parameters are mere inputs to the neural network which must then infer how the video depends on the camera. In contrast, GEN3C is guided by a 3D cache: point clouds obtained by predicting the pixel-wise depth of seed images or previously generated frames. When generating the next frames, GEN3C is conditioned on the 2D renderings of the 3D cache with the new camera trajectory provided by the user. Crucially, this means that GEN3C neither has to remember what it previously generated nor does it have to infer the image structure from the camera pose. The model, instead, can focus all its generative power on previously unobserved regions, as well as advancing the scene state to the next frame. Our results demonstrate more precise camera control than prior work, as well as state-of-the-art results in sparse-view novel view synthesis, even in challenging settings such as driving scenes and monocular dynamic video. Results are best viewed in videos.
</details>
<details>
    <summary>Key points</summary>
   Depth Anything v2 (metric version) is used to predict metric depth for a single reference image, and the pixels are back-projected into camera space to form a stable 3D representation (point cloud). Then, it is registered/scaled with the point cloud obtained by COLMAP triangulation of each training video, thereby unifying the camera trajectory from relative scale to metric scale. During inference, the camera trajectory preview is drawn and rendered in this interactive 3D point cloud.
</details>
</details>

---

<details>
<summary><b>NVS-Solver: Video Diffusion Model as Zero-Shot Novel View Synthesizer</b></summary>

* **Authors:** Meng You, Zhiyu Zhu, et al. (City University of Hong Kong)
* **arXiv ID:** 2405.15364
* **One-liner:** Achieves Zero-Shot Novel View Synthesis without training by utilizing pre-trained video diffusion models via score modulation.
* **Published in:** ICLR 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2405.15364) | [[Project]](https://mengyou2.github.io/NVS_Solver/)

> **Core Innovation**
> Existing Novel View Synthesis (NVS) methods often require expensive training or fine-tuning per scene. **NVS-Solver** proposes a **Training-free (Zero-Shot)** paradigm. It leverages the strong 3D consistency priors latent in pre-trained video diffusion models (like SVD). By theoretically modeling NVS as a **controlled diffusion sampling process**, the authors dynamically inject "geometric priors" (via warping) from reference views into the Score Function during denoising. This allows the model to generate smooth, consistent novel view videos from single or multiple images without any additional training.

<details>
    <summary>Abstract</summary>
    Harnessing the potent generative capabilities of pre-trained large video diffusion models, we propose NVS-Solver, a training-free NVS paradigm. The method adaptively modulates the diffusion sampling process with given views to create visually pleasing results. Specifically, building upon our theoretical modeling, we iteratively modulate the score function with scene priors represented by warped input views to control the video diffusion process. Experiments show that NVS-Solver significantly outperforms existing zero-shot methods on both static and dynamic scenes.
</details>

<details>
    <summary>Key points</summary>
    * **Training-free:** Pure inference-time optimization, no weight fine-tuning required.
    * **Score Modulation:** Modifies the diffusion sampling formula to inject geometric constraints.
    * **Zero-Shot Generalization:** Can handle arbitrary unseen scenes or objects directly.
</details>
</details>

---

<details>
<summary><b>ViVid-1-to-3: Novel View Synthesis with Video Diffusion Models</b></summary>

* **Authors:** Jeong-Gi Kwak, et al. (POSTECH / Samsung AI Center)
* **arXiv ID:** 2312.01305
* **One-liner:** Reformulates Novel View Synthesis as "generating a camera orbit video," leveraging video diffusion models for 3D consistent generation.
* **Published in:** CVPR 2024 (Highlight)
* **Links:** [[Paper]](https://arxiv.org/abs/2312.01305) | [[Project]](https://github.com/ubc-vision/vivid123)

> **Core Innovation**
> Traditional Single-view 3D often relies on multi-view image models (like Zero-1-to-3) but struggles with inconsistency across views. **ViVid-1-to-3** is built on the insight that **"Novel View Synthesis" is essentially generating a video of a camera rotating around an object**. It leverages pre-trained **Video Diffusion Models** (e.g., Zeroscope) to generate this "scanning video." Through simple camera trajectory control and denoising guidance, it produces highly coherent object rotation videos, enabling high-quality 3D extraction and overcoming issues like the "Janus problem" (multi-face).

<details>
    <summary>Abstract</summary>
    Generating novel views from a single image requires understanding the underlying 3D structure. While diffusion-based methods have progressed, maintaining consistency among views remains critical. We present a strikingly simple method: leveraging pre-trained video diffusion models. Our key idea is to reformulate novel view synthesis as synthesizing a "scanning video" of a camera orbiting the object. ViVid-1-to-3 combines view-conditioned diffusion with video diffusion to obtain highly consistent novel view synthesis, outperforming state-of-the-art methods.
</details>

<details>
    <summary>Key points</summary>
    * **NVS as Video:** Ingeniously transforms the 3D generation problem into a video generation task.
    * **Video Priors:** Temporal coherence in video models is translated into spatial (geometric) consistency.
    * **Simplicity:** More intuitive and easier to implement compared to complex 3D distillation pipelines.
</details>
</details>

---

<details>
<summary><b>Vivid-ZOO: Multi-View Video Generation with Diffusion Model</b></summary>

* **Authors:** Bing Li, Cheng Zheng, et al. (KAUST / Gen-Verse)
* **arXiv ID:** 2406.08659
* **One-liner:** Tackles "Text-to-4D" data scarcity by decoupling viewpoint and time, reusing layers from existing Image/Video models to generate dynamic 3D videos.
* **Published in:** NeurIPS 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2406.08659) | [[Project]](https://github.com/hi-zhengcheng/vividzoo)

> **Core Innovation**
> Generating dynamic 3D content (4D generation) is limited by the lack of large-scale "multi-view video" data. **Vivid-ZOO** proposes an efficient Text-to-Multi-view-Video (T2MVid) framework. Instead of training a massive 4D model from scratch, it factors the problem into **Viewpoint** and **Time** components. The model reuses layers from pre-trained **Multi-view Image models** (e.g., MVDream) and **Video Diffusion models**, utilizing novel Alignment Modules to bridge the latent gap. The authors also contribute a captioned multi-view video dataset of animals.

<details>
    <summary>Abstract</summary>
    While diffusion models excel in 2D generation, Text-to-Multi-view-Video (T2MVid) remains underexplored due to data scarcity and high dimensionality. We propose Vivid-ZOO, factoring T2MVid into viewpoint-space and time components. This allows us to reuse layers from advanced pre-trained multi-view image and 2D video diffusion models, ensuring both multi-view consistency and temporal coherence while reducing training costs. We introduce alignment modules to address domain gaps. Experiments show high-quality generation with vivid motions and 3D consistency.
</details>

<details>
    <summary>Key points</summary>
    * **Layer Reuse Strategy:** Combines models that "know 3D geometry" with models that "know temporal motion."
    * **Dimensional Decoupling:** Decomposes complex 4D tasks to handle geometry and time separately.
    * **New Dataset:** Contributes a specialized Multi-view Video Dataset for 4D animal research.
</details>
</details>

---

<details>
<summary><b>Diffusion²: Dynamic 3D Content Generation via Score Composition</b></summary>

* **Authors:** Zeyu Yang, et al. (Fudan University)
* **arXiv ID:** 2404.02148
* **One-liner:** Achieves high-quality dynamic 3D (4D) generation via "Score Composition," fusing gradients from Video and Multi-view diffusion models.
* **Published in:** ICLR 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2404.02148) | [[Project]](https://github.com/fudan-zvg/diffusion-square)

> **Core Innovation**
> Generating dynamic 3D content (4D) requires satisfying both "geometric consistency" and "temporal smoothness." **Diffusion² (Diffusion-Square)** avoids training a new 4D model from scratch. Instead, utilizing **Score Distillation Sampling (SDS)**, it proposes a **Score Composition** framework. It runs two off-the-shelf diffusion models in parallel: a **Video Diffusion Model** (for temporal dynamics) and a **Multi-view Diffusion Model** (for spatial geometry). By integrating their scores (gradients), Diffusion² guides the 4D representation to learn realistic motion and accurate 3D structure simultaneously, effectively solving issues like flickering motion or geometric collapse.

<details>
    <summary>Abstract</summary>
    While available video and 3D data are adequate for training video and multi-view diffusion models separately, combining them for dynamic 3D (4D) generation remains challenging. We present Diffusion², a novel framework that reconciles geometric consistency and temporal smoothness via score composition. We directly fuse gradient scores from pre-trained video and multi-view models to optimize dynamic 3D fields. Additionally, we design a joint denoising algorithm for consistent multi-view video sequences. Experiments show Diffusion² generates 4D content with high-fidelity geometry and fluid motion without requiring any 4D training data.
</details>

<details>
    <summary>Key points</summary>
    * **Score Composition:** Mathematical core, proving that summing scores from different models satisfies multiple constraints.
    * **Dual Priors:** Leverages Video Diffusion (Time) + Multi-view Diffusion (Space) simultaneously.
    * **No 4D Data Needed:** Achieves 4D generation relying solely on existing 2D video and static 3D datasets.
</details>
</details>

---

<details>
<summary><b>RealCam-I2V: Real-World Image-to-Video Generation with Interactive Complex Camera Control</b></summary>

* **Authors:** Li et al.
* **arXiv ID:** 2502.10059
* **One-liner:** Introduces "Absolute Scale" training and interactive control to solve camera trajectory alignment issues in real-world image-to-video generation.
* **Published in:** ICCV 2025 / arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2502.10059) | [[Project]](https://zgctroy.github.io/RealCam-I2V/)

> **Core Innovation**
> Previous methods like CameraCtrl used "relative scale" training, making it difficult for users to set correct camera parameters for real-world images (unknown depth ranges), often leading to scale collapse. **RealCam-I2V** focuses on **Absolute Scale**. It uses monocular metric depth estimation to build 3D scenes during preprocessing and trains the model in a unified metric space. Furthermore, it provides an interactive interface for users to draw trajectories directly in 3D space, utilizing **Scene-constrained Noise Shaping** to maintain stability during generation.

<details>
    <summary>Abstract</summary>
    Existing trajectory-based camera control methods struggle with scale inconsistencies and usability when applied to real-world images. To address this, we propose RealCam-I2V. We integrate monocular metric depth estimation to establish 3D scene reconstruction as a preprocessing step. During training, the reconstructed 3D scene enables scaling camera parameters from relative to metric scales, ensuring compatibility. At inference, RealCam-I2V offers an intuitive interface where users can draw trajectories within the 3D scene. Combined with our noise shaping technique, the method achieves significant quality improvements on RealEstate10K and out-of-domain images.
</details>

<details>
    <summary>Key points</summary>
    * **Absolute Scale Training:** Unifies depth standards across images, giving camera parameters physical meaning.
    * **Interactive Interface:** WYSIWYG trajectory control, removing the need for manual parameter tuning.
    * **Noise Shaping:** Constrains noise using scene priors during denoising to reduce jitter.
</details>
</details>

---

<details>
<summary><b>ViewCrafter: Taming Video Diffusion Models for High-fidelity Novel View Synthesis</b></summary>

* **Authors:** Wangbo Yu, et al.
* **arXiv ID:** 2409.02048
* **One-liner:** Combines coarse point clouds with video diffusion models via "point conditioning" to achieve high-fidelity novel view synthesis from single or sparse images.
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2409.02048) | [[Project]](https://drexubery.github.io/ViewCrafter/)

> **Core Innovation**
> Traditional Novel View Synthesis (NVS) relies on dense input views, while existing generative NVS struggles with precise pose control. **ViewCrafter** proposes combining explicit geometry with generative priors. It first constructs a coarse point cloud (using tools like DUSt3R) from single or sparse images, then trains a **Point-conditioned Video Diffusion Model**. This model uses rendered coarse point cloud images as strong guidance, leveraging the video diffusion model to fix geometric defects and complete textures, enabling large-angle, long-distance flythrough generation.

<details>
    <summary>Abstract</summary>
    Despite advancements in neural 3D reconstruction, synthesizing high-fidelity novel views from sparse inputs remains restricted. ViewCrafter leverages video diffusion model priors to synthesize novel views of generic scenes from single or sparse images. We utilize coarse 3D clues offered by point-based representations combined with the powerful generation capabilities of video models. Specifically, we train a video model conditioned on point cloud renders, enabling precise camera control and view consistency. Furthermore, we adopt an iterative view synthesis strategy to progressively update the point cloud for long-range scene exploration.
</details>

<details>
    <summary>Key points</summary>
    * **Point Conditioning:** Uses coarse geometry to guide generation, solving the "hallucination" problem of pure generative models.
    * **Iterative Refinement:** Generate view -> Update Point Cloud -> Generate further view, enabling long-trajectory exploration.
    * **Sparse Input Support:** Initiates high-quality 3D flythroughs from just a single or very few images.
</details>
</details>

---

<details>
<summary><b>EPiC: Efficient Video Camera Control Learning with Precise Anchor-Video Guidance</b></summary>

* **Authors:** Zun Wang, et al. (UNC Chapel Hill)
* **arXiv ID:** 2505.21876
* **One-liner:** Enables efficient camera control learning without pose annotations by using "Anchor Videos" created via first-frame visibility masking.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2505.21876) | [[Project]](https://zunwang1.github.io/Epic)

> **Core Innovation**
> Training camera control models (like CameraCtrl) typically requires expensive datasets with camera trajectory annotations (e.g., RealEstate10K). **EPiC** proposes a label-free, efficient training method. It constructs "Anchor Videos" by masking source videos based on **First-frame Visibility**. This anchor video essentially simulates the occlusion relationships caused by camera motion, serving as a strong guidance signal for a ControlNet. This allows the model to be trained on arbitrary in-the-wild videos with minimal parameters while achieving SOTA-level camera control.

<details>
    <summary>Abstract</summary>
    To address the high cost and data dependency of existing camera control methods, we introduce EPiC, an efficient and precise framework that requires no expensive camera trajectory annotations. Specifically, we automatically construct high-quality "anchor videos" for training by masking source videos based on first-frame visibility. This approach ensures high alignment and is applicable to any video. Combined with a lightweight ControlNet module, EPiC achieves efficient training with minimal parameters and data. Although trained on masked videos, it robustly generalizes to point-cloud-based anchor videos at inference, enabling precise 3D-informed camera control.
</details>

<details>
    <summary>Key points</summary>
    * **Label-Free:** Removes dependency on camera pose Ground Truth, learning motion from the video's own occlusion cues.
    * **Anchor Video:** A clever data construction method using visibility masks to generate training signals automatically.
    * **Efficiency:** Significantly reduces data and compute requirements compared to methods like CameraCtrl.
</details>
</details>

---

<details>
<summary><b>CameraCtrl: Enabling Camera Control for Video Diffusion Models</b></summary>

* **Authors:** Hao He, et al. (Shanghai AI Lab / CUHK)
* **arXiv ID:** 2311.18881
* **One-liner:** Enables precise camera trajectory control for existing video generation models (e.g., AnimateDiff, SVD) using Plücker coordinate embeddings.
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2311.18881) | [[Project]](https://hehao13.github.io/CameraCtrl/)

> **Core Innovation**
> Before **CameraCtrl**, video generation models relied heavily on text prompts for camera motion (e.g., "pan left"), which were vague and inaccurate. CameraCtrl proposes a plug-and-play **Camera Control Module**. It introduces **Plücker Embeddings** to parameterize camera poses, a representation that better encodes geometric information for CNNs. By training a lightweight camera encoder and injecting it into the Temporal Attention layers of pre-trained video diffusion models, CameraCtrl achieves precise control over camera trajectories without compromising the original generation quality.

<details>
    <summary>Abstract</summary>
    Despite advancements in text-to-video (T2V) generation, precise control over camera pose remains a significant challenge. Existing methods largely rely on text prompts, lacking precision. We propose CameraCtrl, a module that provides precise camera control for video diffusion models. We parameterize camera trajectories using Plücker embeddings and train a camera adapter to inject these signals into the model. Extensive experiments on the RealEstate10K dataset demonstrate that our method enables precise control over viewpoint changes in generated videos while maintaining high fidelity and temporal consistency.
</details>

<details>
    <summary>Key points</summary>
    * **Plücker Embeddings:** Uses Plücker coordinates instead of traditional rotation matrices, facilitating better geometric encoding.
    * **Plug-and-Play:** Functions like a ControlNet, adaptable to various base video models (e.g., AnimateDiff, SVD).
    * **Precise Control:** Allows users to define complex camera trajectories beyond simple panning or zooming.
</details>
</details>

---

<details>
<summary><b>World-consistent Video Diffusion with Explicit 3D Modeling</b></summary>

* **Authors:** Songyuan Zhang, et al.
* **arXiv ID:** 2412.01821
* **One-liner:** Proposes WVD, a framework that jointly generates RGB images and XYZ coordinate maps to achieve 3D-consistent video generation within a single model.
* **Published in:** CVPR 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2412.01821) | [[Project]](https://github.com/Hao-Yi-Wu/WVD)

> **Core Innovation**
> While existing video diffusion models generate realistic videos, they often fail to maintain 3D geometric consistency (e.g., objects morphing with view changes). **WVD (World-consistent Video Diffusion)** introduces explicit **3D Supervision (XYZ Images)**. Instead of just learning RGB pixels, it trains the model to learn the joint distribution of RGB frames and corresponding global 3D coordinate maps (XYZ maps). This design enables the model to "understand" the absolute position of every pixel in the world coordinate system, unifying tasks like Single-view-to-3D, Multi-view Stereo (MVS), and camera-controlled video generation via simple inpainting strategies.

<details>
    <summary>Abstract</summary>
    Recent advancements in diffusion models have set new benchmarks in video generation but still struggle with efficiently and explicitly generating 3D-consistent content. To address this, we propose World-consistent Video Diffusion (WVD), a novel framework incorporating explicit 3D supervision. Specifically, we train a Diffusion Transformer to learn the joint distribution of RGB and XYZ frames, where XYZ frames encode global 3D coordinates for each pixel. This approach supports multi-task adaptability via a flexible inpainting strategy. WVD demonstrates competitive performance across multiple benchmarks, providing a scalable solution for 3D-consistent video and image generation.
</details>

<details>
    <summary>Key points</summary>
    * **XYZ Image Supervision:** Directly predicts world coordinates per pixel, enforcing geometric learning.
    * **Joint Distribution Learning:** Generates appearance (RGB) and geometry (XYZ) simultaneously to ensure alignment.
    * **Unified Multi-tasking:** Handles NVS, 3D reconstruction, and video generation with a single model.
</details>
</details>

---

<details>
<summary><b>OmniView: An All-Seeing Diffusion Model for 3D and 4D View Synthesis</b></summary>

* **Authors:** Xiang Fan, et al.
* **arXiv ID:** 25xx.xxxxx (Recent Preprint)
* **One-liner:** A unified diffusion framework that decouples space, time, and view conditions to handle static, dynamic, and multi-view video generation tasks simultaneously.
* **Published in:** arXiv 2025
* **Links:** [Paper Search]

> **Core Innovation**
> Previous approaches to 4D consistency tasks (like NVS, Text-to-Video, Image-to-Video) were handled by disparate specialized models, leading to fragmented training. **OmniView** proposes a unified framework designed to be an "All-Seeing" generator. Its core lies in decoupling condition inputs into **Space**, **Time**, and **View** dimensions. Through flexible combinations, OmniView can synthesize novel views from static images (3D), dynamic videos (4D), and even extrapolate in time. It achieves superior performance across multiple benchmarks (e.g., LLFF, Neural 3D Video) compared to task-specific models.

<details>
    <summary>Abstract</summary>
    Prior approaches injecting camera control into diffusion models have focused on specific subsets of 4D consistency tasks. Therefore, these fragmented approaches are trained on disjoint slices of available data. We introduce OmniView, a unified framework that generalizes across a wide range of 4D consistency tasks. Our method separately represents space, time, and view conditions, enabling flexible combinations of these inputs. For example, OmniView can synthesize novel views from static, dynamic, and multiview inputs, and extrapolate trajectories in time. OmniView is competitive with task-specific models across diverse benchmarks, significantly improving image quality scores.
</details>

<details>
    <summary>Key points</summary>
    * **Unified Framework:** Bridges the gap between 3D NVS and 4D Video Generation.
    * **Condition Decoupling:** Handles arbitrary combinations of Space/Time/View inputs.
    * **Versatile Performance:** Outperforms specialized models on both static multi-view and dynamic video synthesis benchmarks.
</details>
</details>

---

<details>
<summary><b>PostCam: Camera-Controllable Novel-View Video Generation with Query-Shared Cross-Attention</b></summary>

* **Authors:** Yipeng Chen, et al.
* **arXiv ID:** 2511.17185
* **One-liner:** Focuses on "Post-capture" camera trajectory editing, achieving high-precision novel view video reconstruction via Query-Shared Cross-Attention.
* **Published in:** arXiv 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2511.17185)

> **Core Innovation**
> Existing video recapture methods often struggle to precisely control new camera motions while preserving the details of the original video. **PostCam** proposes a framework for **post-shooting camera movement editing**. It introduces a **Query-Shared Cross-Attention** module that integrates 6-DoF camera poses and 2D rendered frames into a unified feature space. This allows the model to extract underlying motion cues, improving camera control precision (by over 20% vs SOTA) and significantly preserving visual fidelity, effectively allowing users to "re-film" a scene after it has been shot.

<details>
    <summary>Abstract</summary>
    We propose PostCam, a framework for novel-view video generation that enables post-capture editing of camera trajectories in dynamic scenes. We find that existing video recapture methods suffer from suboptimal camera motion injection strategies. To achieve more accurate and flexible motion manipulation, PostCam introduces a query-shared cross-attention module. It integrates two distinct forms of control signals: the 6-DoF camera poses and the 2D rendered video frames. By fusing them into a unified representation within a shared feature space, our model can extract underlying motion cues, enhancing both control precision and generation quality.
</details>

<details>
    <summary>Key points</summary>
    * **Post-capture Editing:** Focuses on altering camera trajectories of existing videos rather than generation from scratch.
    * **Query-Shared Attention:** Core technique that effectively fuses geometric pose and visual content.
    * **High Fidelity:** Maximizes the preservation of original texture and dynamics while drastically changing viewpoints.
</details>
</details>

---

<details>
<summary><b>ViewDiff: 3D-Consistent Image Generation with Text-to-Image Models</b></summary>

* **Authors:** Lukas Höllein, et al. (TUM / NVIDIA)
* **arXiv ID:** 2403.01807
* **One-liner:** Integrates volume rendering layers into Text-to-Image diffusion models to generate multi-view consistent images in a single denoising pass.
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2403.01807) | [[Project]](https://lukashoel.github.io/ViewDiff/)

> **Core Innovation**
> Most Text-to-3D methods require time-consuming per-scene optimization (e.g., Score Distillation). **ViewDiff** transforms pre-trained 2D T2I models into **3D-consistent image generators**. It integrates explicit **3D Volume Rendering layers** and **Cross-frame Attention** into every block of the U-Net. By fine-tuning on real-world multi-view data (like CO3D), ViewDiff can generate multiple geometrically consistent images simultaneously in a single denoising process. These images can be directly used to train NeRFs or Gaussian Splatting, yielding high-quality 3D assets in seconds.

<details>
    <summary>Abstract</summary>
    Existing text-to-3D methods often use pre-trained T2I models for optimization, resulting in non-photorealistic objects. We present ViewDiff, a method that leverages pre-trained T2I models as a prior to generate multi-view images from real-world data. Concretely, we integrate 3D volume-rendering and cross-frame-attention layers into each block of the U-Net. Moreover, we design an autoregressive generation scheme that renders more 3D-consistent images at any viewpoint. Results show that our method generates instances with high-quality shapes and textures and outperforms existing methods in consistency.
</details>

<details>
    <summary>Key points</summary>
    * **Architectural Fusion:** Embeds a 3D renderer (NeRF-like) directly within the 2D Diffusion U-Net.
    * **Single Inference:** Outputs a consistent group of images without expensive optimization loops.
    * **Realistic Priors:** Retains the powerful texture generation capabilities of Stable Diffusion, suitable for real-world objects.
</details>
</details>

---

<details>
<summary><b>TC4D: Trajectory-Conditioned Text-to-4D Generation</b></summary>

* **Authors:** Sherwin Bahmani, et al. (University of Toronto / Adobe / NVIDIA)
* **arXiv ID:** 2403.17920
* **One-liner:** Introduces a trajectory-guided 4D generation framework that decomposes motion into global rigid transformations and local deformations to animate scenes along specified paths.
* **Published in:** ECCV 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2403.17920) | [[Project]](https://sherwinbahmani.github.io/tc4d/)

> **Core Innovation**
> Existing Text-to-4D methods often struggle to control the motion path of generated objects or produce only subtle movements. **TC4D** proposes a **Trajectory Conditioning** approach. Instead of generating a complex 4D field directly, it decomposes 4D scene motion into two components: **global rigid transformation** along a user-defined spline, and **local subtle motion** based on deformation fields. By leveraging video diffusion models as supervision, TC4D generates dynamic 3D scenes that are not only realistic but also strictly follow long-distance complex trajectories.

<details>
    <summary>Abstract</summary>
    We present TC4D, a trajectory-conditioned text-to-4D generation method. Existing 4D generation techniques are often limited to static backgrounds or small object motions. To address this, we decompose scene motion into global rigid transformations along a given path and local deformations. We utilize text-to-video models as supervision during optimization, ensuring the generated scenes adhere to text descriptions and maintain geometric consistency across frames. Experiments show that TC4D generates high-quality dynamic scenes moving along complex 3D trajectories, surpassing existing methods in motion magnitude and realism.
</details>

<details>
    <summary>Key points</summary>
    * **Motion Decomposition:** Splits complex 4D motion into "rigid motion along trajectory" + "local non-rigid deformation".
    * **Trajectory Control:** Allows users to draw arbitrary 3D curves to define object movement paths.
    * **Long-range Generation:** Overcomes the limitation of traditional 4D methods that only generate in-place actions or short movements.
</details>
</details>

---

<details>
<summary><b>Diffusion as Shader: 3D-aware Video Diffusion for Versatile Video Generation Control</b></summary>

* **Authors:** Yan Gu, et al. (HKUST / Ant Group)
* **arXiv ID:** 2501.03847
* **One-liner:** Uses 3D tracking videos as control signals, treating the video diffusion model as a "neural renderer" to achieve versatile control like object manipulation and camera movement within a unified architecture.
* **Published in:** SIGGRAPH 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2501.03847) | [[Project]](https://igl-hkust.github.io/das/)

> **Core Innovation**
> Traditional video control methods (like ControlNet) often rely on 2D signals (edges, poses), making complex 3D physical interactions difficult. **Diffusion as Shader (DaS)** proposes a new paradigm: treating video generation as a rendering process for dynamic 3D content. It uses **3D Tracking Videos**—rendered sequences of low-poly geometry—as strong control inputs. By fine-tuning video diffusion models, DaS learns to "shade" these coarse 3D signals into realistic videos. Since the control signal is inherently 3D, DaS can easily handle tasks like camera movement, object replacement, and motion transfer by simply modifying the input 3D proxy, naturally maintaining temporal consistency.

<details>
    <summary>Abstract</summary>
    Existing controlled video generation methods are typically limited to single control types and lack flexibility in handling 3D dynamics. We introduce Diffusion as Shader (DaS), a novel approach supporting multiple video control tasks within a unified architecture. Our key insight is leveraging 3D tracking videos as control inputs, making the video diffusion process inherently 3D-aware. This allows DaS to achieve a wide range of video controls (e.g., camera control, object manipulation, mesh-to-video) by simply manipulating the 3D tracking data. With minimal fine-tuning, DaS demonstrates strong control capabilities and temporal consistency across diverse tasks.
</details>

<details>
    <summary>Key points</summary>
    * **3D Tracking Video:** Uses coarse 3D rendered sequences as conditions instead of 2D edge maps.
    * **Unified Architecture:** A single model handles Camera Control, Motion Transfer, Object Manipulation, etc.
    * **Inherent Consistency:** Generated videos are extremely stable temporally due to the continuity of the 3D signal.
</details>
</details>

---

<details>
<summary><b>3DTrajMaster: Mastering 3D Trajectory for Multi-Entity Motion in Video Generation</b></summary>

* **Authors:** Xiao Fu, et al. (Kling Team / HKUST / Tsinghua)
* **arXiv ID:** 2412.07759
* **One-liner:** Introduces a "3D Motion Injector" and "360-degree Motion Dataset" to enable precise 6-DoF trajectory control for multiple entities in video generation.
* **Published in:** ICLR 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2412.07759) | [[Project]](https://github.com/KlingTeam/3DTrajMaster)

> **Core Innovation**
> Previous video generation controls were often limited to 2D space (e.g., bounding box movement), failing to express complex 3D motions like depth changes or rotation. **3DTrajMaster** focuses on **Multi-Entity 3D Trajectory Control**. It constructs a large-scale **360-Motion Dataset** containing diverse 3D motion data. Architecturally, it introduces a **3D-motion grounded Object Injector** that fuses 6-DoF pose sequences into the video generation model via gated self-attention. This allows users to precisely direct the position and orientation of multiple objects in 3D space, handling complex occlusions and perspective changes.

<details>
    <summary>Abstract</summary>
    This paper aims to manipulate multi-entity 3D motions in video generation. Previous 2D control signals limit the expression of the 3D nature of object motions. To overcome this, we introduce 3DTrajMaster, a robust controller that regulates multi-entity dynamics in 3D space given user-desired 6-DoF pose sequences. At its core is a plug-and-play 3D-motion grounded object injector that fuses entities with trajectories via gated self-attention. Additionally, to address data scarcity, we construct a 360-Motion Dataset using multi-camera capture and GPT-generated trajectories. Experiments show that 3DTrajMaster sets a new state-of-the-art in both accuracy and generalization.
</details>

<details>
    <summary>Key points</summary>
    * **6-DoF Trajectory Control:** Supports full control over object location (x,y,z) and rotation (yaw,pitch,roll).
    * **Multi-Entity Support:** Capable of directing multiple objects performing complex interactive motions simultaneously.
    * **360-Motion Dataset:** A specially constructed high-quality 3D motion-video dataset addressing the training data bottleneck.
</details>
</details>

---

<details>
<summary><b>SV3D: Novel Multi-view Synthesis and 3D Generation from a Single Image using Latent Video Diffusion</b></summary>

* **Authors:** Vikram Voleti, et al. (Stability AI)
* **arXiv ID:** 2403.12008
* **One-liner:** Adapts Stable Video Diffusion to generate coherent orbital videos around 3D objects, significantly improving single-image-to-3D quality.
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2403.12008) | [[Project]](https://sv3d.github.io/)

> **Core Innovation**
> Before SV3D, single-image-to-3D methods often relied on multi-view diffusion models (like Zero123) which frequently lacked consistency across views. **SV3D (Stable Video 3D)** reframes this as a **video generation task**. It leverages the strong temporal consistency priors of Stable Video Diffusion (SVD), fine-tuning the model to generate **Orbital Videos** around an object. SV3D introduces explicit **Camera Pose Conditioning**, enabling the generation of image sequences with deterministic viewpoints. These sequences are then used for high-quality 3D asset generation via improved Score Distillation Sampling (SDS) or direct mesh reconstruction.

<details>
    <summary>Abstract</summary>
    We present Stable Video 3D (SV3D), a latent video diffusion model for high-resolution, image-to-multi-view generation of orbital videos around a 3D object. Recent work on 3D generation adapts 2D models for novel view synthesis (NVS) but suffers from limited views or inconsistency. SV3D adapts image-to-video diffusion models, leveraging their generalization and multi-view consistency, while adding explicit camera control. We also propose improved 3D optimization techniques to utilize SV3D outputs. Extensive results demonstrate SV3D's state-of-the-art performance in both NVS and 3D reconstruction.
</details>

<details>
    <summary>Key points</summary>
    * **Video Prior:** Uses SVD's coherency to solve "Janus" (multi-head) problems common in Zero123.
    * **Explicit Camera Control:** Supports precise control over viewpoint paths via camera elevation and azimuth.
    * **SV3D_u / SV3D_p:** Offers variants for unconditional (orbital only) and pose-conditioned (specific trajectory) generation.
</details>
</details>

---

<details>
<summary><b>4Diffusion: Multi-view Video Diffusion Model for 4D Generation</b></summary>

* **Authors:** Haiyu Zhang, et al. (Beihang University / Shanghai AI Lab)
* **arXiv ID:** 2405.20674
* **One-liner:** Proposes a unified multi-view video diffusion model combined with a 4D-aware SDS loss to generate spatially and temporally consistent 4D content from monocular video.
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2405.20674) | [[Project]](https://github.com/aejion/4Diffusion)

> **Core Innovation**
> Existing 4D generation methods (often based on SDS) frequently suffer from spatiotemporal inconsistency due to independent optimization across views or frames. **4Diffusion** introduces a tailored **Multi-view Video Diffusion Model (4DM)**. It incorporates a learnable motion module into a frozen 3D-aware image diffusion model (like MVDream) to capture multi-view spatiotemporal correlations. Subsequently, the authors propose a **4D-aware SDS Loss**, utilizing this trained 4DM to supervise the optimization of a dynamic NeRF, thereby eliminating multi-face issues and flickering artifacts during generation.

<details>
    <summary>Abstract</summary>
    Current 4D generation methods have achieved efficacy but struggle with consistency. We propose 4Diffusion, a novel pipeline for generating spatially-temporally consistent 4D content from a monocular video. First, we design a unified diffusion model tailored for multi-view video generation by incorporating a learnable motion module into a frozen 3D-aware diffusion model. After training, our model acquires reasonable temporal consistency. Subsequently, we propose a 4D-aware Score Distillation Sampling loss based on our multi-view video diffusion model to optimize 4D representations parameterized by dynamic NeRF. Experiments demonstrate superior performance compared to previous methods.
</details>

<details>
    <summary>Key points</summary>
    * **4DM Model:** A diffusion architecture combining "3D Consistency" (MVDream) with "Temporal Consistency" (Motion Module).
    * **4D-aware SDS:** Uses the video diffusion model as a Score Function to directly supervise 4D field consistency.
    * **Anchor Loss:** Introduces an anchor loss to enhance appearance details and facilitate dynamic NeRF learning.
</details>
</details>

---

<details>
<summary><b>Point-DynRF: Point-Based Dynamic Radiance Fields From a Monocular Video</b></summary>

* **Authors:** Lee, Park, et al.
* **arXiv ID:** [Published in WACV 2024]
* **One-liner:** A Point-NeRF based approach for dynamic radiance fields that distinguishes static/dynamic regions and regresses dynamic fields only on surfaces, enabling high-quality long-term dynamic view synthesis.
* **Published in:** WACV 2024
* **Links:** [[Paper]](https://openaccess.thecvf.com/content/WACV2024/html/Park_Point-DynRF_Point-Based_Dynamic_Radiance_Fields_From_a_Monocular_Video_WACV_2024_paper.html)

> **Core Innovation**
> Traditional dynamic NeRFs (like D-NeRF) typically use MLPs to implicitly encode the entire spatiotemporal field, leading to slow training and difficulties with long videos or large motions. **Point-DynRF** extends the explicit **Point-NeRF** representation to dynamic scenes. It first distinguishes static backgrounds from dynamic objects by analyzing the entire video sequence. For dynamic regions, instead of building a global deformation field, it regresses dynamic radiance fields directly on per-frame **Neural Point Clouds**. This point-based representation accelerates rendering and avoids artifacts in empty space, significantly improving novel view synthesis for long-duration videos.

<details>
    <summary>Abstract</summary>
    Synthesizing novel views of dynamic scenes from monocular video is challenging. Existing deformation-based methods often produce blurry results when dealing with large motions or long sequences. Inspired by Point-NeRF, we propose Point-DynRF, a point-based dynamic radiance field representation. We leverage point clouds to explicitly model scene geometry and encode static and dynamic regions separately. By regressing dynamic features only on inferred surface points, our method avoids computational waste and artifacts in free space. Experimental results show that Point-DynRF outperforms existing SOTA methods in long-term dynamic view synthesis tasks.
</details>

<details>
    <summary>Key points</summary>
    * **Explicit Point Representation:** Extends Point-NeRF to the temporal dimension, using geometric priors for better quality.
    * **Static-Dynamic Split:** Explicitly separates and optimizes static background points and dynamic foreground points.
    * **Long-term Stability:** Handles complex motions in long sequences better than MLP-based deformation field methods.
</details>
</details>

---

<details>
<summary><b>Consistent4D: Consistent 360° Dynamic Object Generation from Monocular Video</b></summary>

* **Authors:** Yanqin Jiang, et al. (Zhejiang University / Ant Group)
* **arXiv ID:** 2311.02848
* **One-liner:** Frames dynamic object generation as a 4D generation problem, utilizing 3D-aware image diffusion models as supervision and solving spatiotemporal inconsistencies via an interpolation-driven consistency loss.
* **Published in:** ICLR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2311.02848) | [[Project]](https://consistent4d.github.io/)

> **Core Innovation**
> Reconstructing 360° dynamic objects from monocular video often suffers from missing views. **Consistent4D** uniquely frames this task as a **4D Generation Problem**, thereby leveraging pre-trained **3D-aware Image Diffusion Models** (like Zero-1-to-3) as strong priors. To address spatiotemporal discontinuities caused by discrete supervision, the authors propose a **Cascade DyNeRF** structure and an **Interpolation-driven Consistency Loss**. The latter uses a video interpolation model to create pseudo-labels, enforcing the DyNeRF to remain smooth and consistent across unseen views and times, effectively mitigating the "Janus" problem.

<details>
    <summary>Abstract</summary>
    We present Consistent4D, a novel approach for generating 4D dynamic objects from uncalibrated monocular videos. Uniquely, we cast the 360-degree dynamic object reconstruction as a 4D generation problem, eliminating the need for tedious multi-view data collection and camera calibration. This is achieved by leveraging object-level 3D-aware image diffusion models as the primary supervision signal for training Dynamic Neural Radiance Fields (DyNeRF). Specifically, we propose a Cascade DyNeRF to facilitate stable convergence and introduce an Interpolation-driven Consistency Loss for spatiotemporal consistency. Experiments show Consistent4D is competitive in generation quality and consistency.
</details>

<details>
    <summary>Key points</summary>
    * **Generative Reconstruction Paradigm:** Uses Generative Priors to fill in missing information from monocular video.
    * **Cascade DyNeRF:** A cascaded structure to stabilize dynamic field optimization.
    * **Interpolation Consistency Loss (ICL):** Uses video interpolation models to constrain temporal continuity and smooth dynamic changes.
</details>
</details>

---

<details>
<summary><b>4Dynamic: Text-to-4D Generation with Hybrid Priors</b></summary>

* **Authors:** Yohan Hong, et al.
* **arXiv ID:** 2407.12684
* **One-liner:** Leverages hybrid priors (Video Diffusion + 3D-aware Models) to directly supervise dynamic amplitude and realism, addressing small or unnatural motions in Text-to-4D generation.
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2407.12684)

> **Core Innovation**
> Many Text-to-4D methods (like MAV3D) often produce motions that are subtle or lack realism, mainly because SDS gradients from Text-to-Video models can be ambiguous. **4Dynamic** proposes a method based on **Hybrid Priors**. It combines **Video Diffusion Models** (to supervise dynamic amplitude and realism) and **3D-aware Image Models** (to ensure geometric consistency). The key lies in using direct video prior supervision alongside SDS to ensure the generated 4D scenes possess significant and plausible motion, bridging the gap between static 3D and dynamic video generation.

<details>
    <summary>Abstract</summary>
    In this paper, we propose 4Dynamic, a novel method for text-to-4D generation that ensures dynamic amplitude and authenticity through direct supervision provided by a video prior. Existing methods often struggle to generate large and natural motions. To address this, we utilize hybrid priors: video diffusion models provide rich motion context, while 3D-aware models ensure geometric structure. Our method balances these priors via carefully designed loss functions, generating high-fidelity 4D content with significant motion magnitude and spatiotemporal consistency.
</details>

<details>
    <summary>Key points</summary>
    * **Hybrid Priors:** Combines the strengths of Video Diffusion (dynamics) and 3D-aware Diffusion (static geometry).
    * **Motion Magnitude Enhancement:** Specifically targets the "zombie" or subtle motion issues common in 4D generation.
    * **Direct Supervision:** Introduces more direct video feature matching compared to pure SDS optimization.
</details>
</details>

---

<details>
<summary><b>DyBluRF: Dynamic Deblurring Neural Radiance Fields for Blurry Monocular Video</b></summary>

* **Authors:** Minhyeok Lee, et al. (KAIST)
* **arXiv ID:** 2312.13528
* **One-liner:** The first dynamic NeRF framework handling blurry monocular video, utilizing DCT trajectories to model motion blur and recover sharp novel view videos.
* **Published in:** arXiv 2023 (Updated 2024)
* **Links:** [[Paper]](https://arxiv.org/abs/2312.13528) | [[Project]](https://kaist-viclab.github.io/dyblurf-site/)

> **Core Innovation**
> Existing dynamic NeRF methods typically assume sharp input videos; their reconstruction quality degrades sharply with **Motion Blur**. **DyBluRF** proposes the first dynamic deblurring NeRF framework for blurry monocular videos. It consists of two stages: **Interleave Ray Refinement (IRR)** and **Motion Decomposition-based Deblurring (MDD)**. The core idea is to physically model the blurring process by aggregating multiple rays over the exposure time (simulating motion via DCT trajectories) to synthesize blurry pixels, thereby inversely learning the sharp 3D scene and precise camera trajectories.

<details>
    <summary>Abstract</summary>
    We propose DyBluRF, a novel dynamic deblurring NeRF framework for blurry monocular video, consisting of an Interleave Ray Refinement (IRR) stage and a Motion Decomposition-based Deblurring (MDD) stage. DyBluRF is the first to address novel view synthesis for blurry monocular video. The IRR stage jointly reconstructs dynamic 3D scenes and refines inaccurate camera poses. In the MDD stage, we introduce a novel Incremental Latent Sharp-rays Prediction (ILSP) approach by decomposing latent sharp rays into global camera motion and local object motion components. Experiments demonstrate that DyBluRF significantly outperforms existing SOTA methods qualitatively and quantitatively.
</details>

<details>
    <summary>Key points</summary>
    * **Physical Blur Modeling:** Simulates motion blur by integrating rays over time to inversely solve for the sharp scene.
    * **DCT Trajectories:** Uses Discrete Cosine Transform to parameterize object and camera motion trajectories for complex non-linear motions.
    * **Two-Stage Optimization:** First coarsely reconstructs and refines poses, then finely decomposes motion for deblurring.
</details>
</details>

---

<details>
<summary><b>DynIBaR: Neural Dynamic Image-Based Rendering</b></summary>

* **Authors:** Zhengqi Li, et al. (Google Research / Cornell)
* **arXiv ID:** 2211.11082
* **One-liner:** Combines Image-Based Rendering (IBR) with spatiotemporal feature aggregation to synthesize high-quality novel views from monocular videos with complex camera motion.
* **Published in:** CVPR 2023 (Best Paper Honorable Mention)
* **Links:** [[Paper]](https://arxiv.org/abs/2211.11082) | [[Project]](https://dynibar.github.io/)

> **Core Innovation**
> Previous dynamic NeRFs (like D-NeRF) struggled with long, in-the-wild videos because they tried to memorize the entire scene's appearance. **DynIBaR** adopts an **Image-Based Rendering (IBR)** approach. Instead of encoding everything in an MLP, it predicts **Motion Trajectories** to dynamically aggregate features from nearby source frames when rendering. This allows the model to utilize raw pixel details from source images, resulting in flicker-free, high-fidelity synthesis even with complex camera motions and dynamic objects.

<details>
    <summary>Abstract</summary>
    We present DynIBaR, a method for synthesizing novel views of complex dynamic scenes from monocular videos. Existing dynamic NeRF methods often suffer from blurriness or artifacts when handling long videos with complex camera movements. To address these limitations, we adopt a volumetric image-based rendering framework. The core idea is to synthesize novel views by aggregating features from nearby source views via predicted per-pixel motion trajectories. This enables our model to overcome the inherent difficulties of dynamic scene representation by referencing source image details. We demonstrate state-of-the-art rendering quality on challenging dynamic video datasets.
</details>

<details>
    <summary>Key points</summary>
    * **Image-Based Rendering (IBR):** Leveraging source pixels directly avoids the blurriness of pure MLP-based memorization.
    * **Motion Trajectory Aggregation:** Aligns features across time steps to enforce temporal consistency.
    * **In-the-wild Capability:** Robustly handles real-world videos with significant camera shake and complex object deformation.
</details>
</details>

---

<details>
<summary><b>4D-fy: Text-to-4D Generation Using Hybrid Score Distillation Sampling</b></summary>

* **Authors:** Sherwin Bahmani, et al. (Snap Inc. / University of Toronto)
* **arXiv ID:** 2311.17984
* **One-liner:** Generates high-fidelity, multi-view consistent 4D dynamic scenes from text using a Hybrid SDS loss that combines 3D and video diffusion models.
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2311.17984) | [[Project]](https://sherwinbahmani.github.io/4d-fy/)

> **Core Innovation**
> Early Text-to-4D methods (like MAV3D) relied mainly on video diffusion models for supervision, resulting in low-quality geometry and texture. **4D-fy** proposes a **Hybrid Score Distillation Sampling (Hybrid SDS)** strategy. It leverages both **3D Diffusion Models** (for high-resolution, multi-view consistent geometry/texture) and **Video Diffusion Models** (for temporal coherence and dynamics). By combining these priors, 4D-fy resolves the "Janus" problem and produces 4D scenes that look like high-quality 3D models with fluid motion.

<details>
    <summary>Abstract</summary>
    Recent progress in text-to-4D generation shows promise but often falls short in spatial resolution and textural detail. We introduce 4D-fy, a method for generating high-quality 4D scenes from text using hybrid Score Distillation Sampling (SDS). We decompose 4D generation into spatial and temporal components, combining the strengths of 3D-aware image diffusion models and video diffusion models. The 3D model ensures high visual fidelity and geometric consistency, while the video model ensures temporal smoothness. This hybrid approach yields 4D scenes significantly superior in quality to methods relying solely on video models.
</details>

<details>
    <summary>Key points</summary>
    * **Hybrid SDS:** Fuses 3D Priors (spatial quality) and Video Priors (temporal dynamics).
    * **Multi-stage Optimization:** Learns static 3D structure first, then dynamic deformation, preventing geometric collapse.
    * **High Fidelity:** Produces sharper textures and more accurate geometry compared to MAV3D.
</details>
</details>

---

<details>
<summary><b>TiNeuVox: Fast Dynamic Radiance Fields with Time-Aware Neural Voxels</b></summary>

* **Authors:** Fangneng Zhan, et al. (MPI Informatics / S-Lab)
* **arXiv ID:** 2205.15285
* **One-liner:** Accelerates dynamic NeRF training from days to minutes using explicit voxel grids combined with lightweight time-deformation MLPs.
* **Published in:** SIGGRAPH Asia 2022
* **Links:** [[Paper]](https://arxiv.org/abs/2205.15285) | [[Project]](https://fnzhan.com/TiNeuVox/)

> **Core Innovation**
> Training dynamic NeRFs is typically excruciatingly slow (e.g., D-NeRF takes days) due to MLPs trying to fit the entire spatiotemporal field. **TiNeuVox** adapts ideas from static NeRF acceleration (like DVGO, TensoR) by proposing **Time-Aware Neural Voxels**. It represents the scene as explicit voxel feature grids augmented with a tiny deformation network to handle temporal changes. This hybrid representation (Explicit Grid + Implicit Deformation) allows for fast feature querying via optimized data structures while retaining the ability to model non-rigid deformations, achieving orders-of-magnitude speedup.

<details>
    <summary>Abstract</summary>
    Neural Radiance Fields (NeRF) have shown great success in novel view synthesis for dynamic scenes but come with high computational costs. We propose TiNeuVox, a framework for fast training of dynamic radiance fields. Our key insight is to decouple the spatiotemporal field into a multi-resolution voxel grid capturing static geometry/appearance and a lightweight deformation network modeling dynamic changes. This combination of explicit and implicit representations enables TiNeuVox to drastically reduce training time (from days to minutes) while maintaining high rendering quality.
</details>

<details>
    <summary>Key points</summary>
    * **Fast Training:** Completes dynamic scene training in minutes on a single GPU.
    * **Time-Aware Voxels:** A data structure that effectively balances memory consumption and representational power.
    * **Multi-resolution Grid:** Uses a coarse-to-fine optimization strategy to capture high-frequency details.
</details>
</details>

---

<details>
<summary><b>SV4D: Dynamic 3D Content Generation with Video Diffusion Models</b></summary>

* **Authors:** U of Toronto / Snap Inc.
* **arXiv ID:** 2403.12008 / 2403.xxxxx
* **One-liner:** Generates high-quality 4D dynamic meshes from a single image by leveraging multi-view consistent videos generated by Stable Video Diffusion (SVD) as supervision.
* **Published in:** CVPR 2024 (Highlight) / arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2403.12008) | [[Project]](https://sv4d.github.io/)

> **Core Innovation**
> Existing Image-to-4D methods often struggle to maintain long-term multi-view consistency, leading to shape collapse during motion. **SV4D** leverages pre-trained **Stable Video Diffusion (SVD)** models. It first converts a single reference image into an **Orbital Video**, then uses SVD to generate **multi-view dynamic videos** of the object across time steps. By using these generated videos as Pseudo-GT, SV4D optimizes an implicit 4D representation (like Dynamic NeRF or Gaussian), achieving a robust Single-Image-to-4D pipeline where the object remains geometrically stable from all angles.

<details>
    <summary>Abstract</summary>
    We present SV4D, a method for generating 4D dynamic content from a single image and motion description. Unlike previous methods that optimize via Score Distillation Sampling (SDS), SV4D adopts a "generation-then-reconstruction" pipeline. We first fine-tune a video diffusion model to generate consistent multi-view video sequences around 3D objects. We then use these generated videos as supervision signals to optimize a 4D representation. This approach effectively utilizes the rich 3D and dynamic priors within video generation models, producing high-resolution and spatiotemporally consistent 4D assets.
</details>

<details>
    <summary>Key points</summary>
    * **Video Prior Utilization:** Uses generated dense multi-view videos as training data instead of ambiguous SDS gradients.
    * **Consistency Fine-tuning:** Fine-tunes the video model to ensure generated videos are geometrically 3D consistent.
    * **Generation-then-Reconstruction:** Avoids common SDS artifacts like oversaturation.
</details>
</details>

---

<details>
<summary><b>STAG4D: Spatial-Temporal Anchored Generative 4D Gaussians</b></summary>

* **Authors:** Yifei Zeng, et al. (Tsinghua / ShengShu)
* **arXiv ID:** 2403.14939
* **One-liner:** Combines 3D generation priors and video diffusion models via a "Spatial-Temporal Anchoring" strategy to generate high-quality 4D Gaussian scenes.
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2403.14939) | [[Project]](https://stag4d.github.io/)

> **Core Innovation**
> Existing Text-to-4D methods often struggle to balance geometric quality and motion coherence. **STAG4D** proposes a step-wise "anchored" strategy. First, it generates a static, high-quality 3D Gaussian field as the **first-frame anchor** using multi-view 3D models (e.g., MVDream). Then, it uses a video diffusion model (e.g., SVD) to generate a dynamic video. The core lies in **Spatial-Temporal Anchoring**: initializing and constraining subsequent 4D Gaussians based on the first frame's geometry and the generated video flow, preventing geometric collapse or flickering during optimization.

<details>
    <summary>Abstract</summary>
    We present STAG4D, a novel framework for high-fidelity text-to-4D generation. We leverage pre-trained 3D-aware image models and video diffusion models as spatial and temporal priors, respectively. Our key contribution is the spatial-temporal anchoring strategy: we first generate a static 3D Gaussian scene as a spatial anchor, then generate reference videos via video diffusion as temporal guidance. By "anchoring" the dynamic Gaussians to these priors during optimization, we resolve multi-view inconsistency and temporal jitter, achieving SOTA 4D generation results.
</details>

<details>
    <summary>Key points</summary>
    * **Static-to-Dynamic:** Establishes high-quality 3D geometry first, then animates it.
    * **Anchoring Strategy:** Explicitly uses first-frame geometry and reference video to constrain optimization.
    * **Generative 4DGS:** Leverages the explicit nature of 3DGS for easier spatiotemporal manipulation.
</details>
</details>

---

<details>
<summary><b>DreamGaussian4D: Generative 4D Gaussian Splatting</b></summary>

* **Authors:** Jiawei Ren, et al. (Nanyang Technological University / Tsinghua)
* **arXiv ID:** 2312.17142
* **One-liner:** Extends DreamGaussian's rapid generation capabilities, employing Image-to-Video models to drive Gaussian deformation, achieving single-image to 4D generation in minutes.
* **Published in:** arXiv 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2312.17142) | [[Project]](https://dreamgaussian4d.github.io/)

> **Core Innovation**
> As the successor to the famous **DreamGaussian**, **DreamGaussian4D** focuses on **speed** and **efficiency**. Starting from a single static image, it first generates a video sequence of that view using an Image-to-Video model (like Stable Video Diffusion). Instead of optimizing 3D from scratch for every frame, it learns a **Deformation Field** to drive the static 3D Gaussians. This approach avoids complex 4D SDS optimization, drastically reducing computation time. It also introduces an inpainting-based texture refinement stage to improve quality in occluded regions.

<details>
    <summary>Abstract</summary>
    DreamGaussian4D is an efficient image-to-4D generation framework. Building upon the static 3D generation capabilities of DreamGaussian, we introduce the temporal dimension to Gaussian Splatting. We utilize videos generated by video diffusion models as pseudo-GT to supervise 4D optimization. To handle occlusion and disocclusion during object motion, we design a visibility-based Gaussian deformation network. The entire process is extremely fast, capable of generating 4D assets with realistic motion from a single image in minutes.
</details>

<details>
    <summary>Key points</summary>
    * **Ultra-fast Generation:** Compresses 4D generation time to minutes, inheriting DreamGaussian's efficiency.
    * **Video-Driven Deformation:** Uses generated video to directly supervise Gaussian point displacement.
    * **Texture Refinement:** Uses inpainting to fix regions that were originally occluded but revealed during motion.
</details>
</details>

---

<details>
<summary><b>Deformable 3D Gaussians (D-3DGS)</b></summary>

* **Authors:** Ziyi Yang, et al. (NVIDIA / UCSD)
* **arXiv ID:** 2309.13101
* **One-liner:** Proposes a "Canonical Gaussians + Deformation Field" architecture, achieving high-fidelity monocular dynamic scene reconstruction without spatiotemporal grids.
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2309.13101) | [[Project]](https://ingra14m.github.io/Deformable-Gaussians/)

> **Core Innovation**
> Unlike 4DGS (which uses Hexplane), **Deformable 3D Gaussians** adopts a purer deformation approach. It maintains a set of static 3D Gaussians in a **Canonical Space** and trains a **Deformation MLP**. This MLP takes position and time as input and outputs the displacement ($\Delta x$), rotation ($\Delta r$), and scaling ($\Delta s$) changes for the current frame. This method avoids explicit 4D voxel grids, adapting flexibly to dynamic scenes with stable topology. An **Annealing Smoothing Training** strategy is introduced to effectively solve overfitting issues in the deformation field.

<details>
    <summary>Abstract</summary>
    We introduce Deformable 3D Gaussians for dynamic scene reconstruction from monocular video. It models scene dynamics by learning 3D Gaussians in a canonical space and deforming them via a deformation field. We also introduce an annealing smoothing training mechanism, enabling the deformation field to better capture motions at different scales. The method achieves real-time rendering speeds and surpasses existing dynamic NeRF methods in reconstruction fidelity, particularly in handling object details and complex motions.
</details>

<details>
    <summary>Key points</summary>
    * **Canonical + Deformation:** Classic dynamic modeling paradigm decoupling motion and geometry.
    * **Pure MLP Driven:** Lower storage requirements and more compact parameters compared to grid methods.
    * **Annealing Smoothing Training:** Coarse-to-fine training strategy to prevent local optima in the deformation field.
</details>
</details>

---

<details>
<summary><b>CAT4D: Create Anything in 4D with Multi-View Video Diffusion Models</b></summary>

* **Authors:** Rundi Wu, et al. (Peking University / Columbia University)
* **arXiv ID:** 2411.18613
* **One-liner:** Leverages a Multi-View Video Diffusion Model (MV-VDM) for "one-click" generation of arbitrary 4D content from images, text, or 3D assets.
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2411.18613) | [[Project]](https://cat4d.github.io/)

> **Core Innovation**
> Previous 4D generation methods often required complex optimization pipelines (SDS) or multi-stage processing. **CAT4D** aims for simple, one-step generation akin to 2D generation. It trains a robust **Multi-View Video Diffusion Model**. This model can infer video sequences of an object from multiple viewpoints simultaneously. Once these multi-view videos are obtained, CAT4D performs deterministic 4D reconstruction (rather than generative optimization) to quickly yield a 4D Gaussian Splatting model. This makes CAT4D highly flexible, accepting images, text, or even existing 3D models as input to animate them.

<details>
    <summary>Abstract</summary>
    We introduce CAT4D, a unified framework capable of creating high-fidelity 4D scenes from a single image, text, or 3D model. At the core of CAT4D is a multi-view video diffusion model trained on a newly collected dataset of thousands of 4D dynamic objects. This model generates videos that are temporally coherent and consistent across multiple views. Using these videos as input, we reconstruct 4D scenes via deformable 3D Gaussian Splatting in just minutes. Experiments show CAT4D reaches new heights in generation quality and diversity.
</details>

<details>
    <summary>Key points</summary>
    * **Multi-View Video Diffusion (MV-VDM):** Core engine generating consistent slices of 4D data directly.
    * **Unified Input:** Supports Image-to-4D, Text-to-4D, and 3D-to-4D modes.
    * **SDS-Free:** Avoids the unstable score distillation optimization common in traditional 4D generation.
</details>
</details>

---

<details>
<summary><b>Diffusion4D: Fast Spatial-temporal Consistent 4D Generation via Video Diffusion Models</b></summary>

* **Authors:** Hanwen Li, et al. (Tencent / HKU)
* **arXiv ID:** 2405.16645
* **One-liner:** Achieves fast and consistent 4D generation by combining video diffusion models with explicit 3D Gaussian Splatting via a "multi-view video generation + 4D reconstruction" two-stage strategy.
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2405.16645)

> **Core Innovation**
> **Diffusion4D** addresses efficiency and consistency in 4D generation by shifting the paradigm from "optimization" to "generation+reconstruction," similar to SV4D/CAT4D. It first utilizes a fine-tuned video diffusion model (SVD) to generate multi-view orbital videos of the target object. Distinctively, Diffusion4D emphasizes **spatiotemporal consistency** and employs explicit 3D Gaussian Splatting as the 4D representation. By training dynamic 3DGS directly on the generated videos, it avoids complex SDS gradient calculations, significantly improving generation speed and geometric stability.

<details>
    <summary>Abstract</summary>
    We propose Diffusion4D, a novel approach for generating spatiotemporally consistent 4D content. Existing SDS-based methods are often time-consuming and unstable. Diffusion4D leverages video diffusion models as strong 4D priors. We first generate multi-view consistent video sequences, then use these sequences to rapidly reconstruct dynamic scenes via 4D Gaussian Splatting. Our method is not only fast but also produces high-quality 4D assets with rich details and realistic motion.
</details>

<details>
    <summary>Key points</summary>
    * **Video Prior Driven:** Relies on videos generated by Video Diffusion Models as direct supervision.
    * **Explicit Gaussian Representation:** Uses 3DGS for rapid reconstruction and rendering.
    * **Two-Stage Pipeline:** Clearly separates "video generation" and "4D reconstruction," enhancing robustness.
</details>
</details>

---

<details>
<summary><b>OmniMotion: Tracking Everything Everywhere All at Once</b></summary>

* **Authors:** Qianqian Wang, et al. (Google Research / Cornell)
* **arXiv ID:** 2306.05422
* **One-liner:** Proposes a "test-time optimization" global motion representation using bijective mappings to a canonical 3D space, achieving indefinitely long-term tracking that handles occlusions robustly.
* **Published in:** ICCV 2023 (Best Student Paper)
* **Links:** [[Paper]](https://arxiv.org/abs/2306.05422) | [[Project]](https://omnimotion.github.io/)

> **Core Innovation**
> Traditional optical flow or point tracking (e.g., TAP-Vid) operates frame-by-frame, often losing targets due to occlusion or drift and lacking global consistency. **OmniMotion** shifts this paradigm by performing **Test-time Optimization** on a **specific video**. It represents the entire video as a **Canonical 3D Volume** and learns **Bijective (Invertible) Mappings** between each frame and this canonical space. This means every pixel corresponds to a fixed 3D point in the canonical space. This global representation naturally guarantees **Cycle Consistency** and allows tracking through occlusions: even if an object is hidden, its canonical 3D position persists, enabling immediate recovery upon reappearance.

<details>
    <summary>Abstract</summary>
    We present a new test-time optimization method for estimating dense, long-term motion across full-length videos. Existing optical flow methods are limited to pairs of frames and fail to capture long-term trajectories, especially under occlusion. We represent video motion as a bijection between local 2D pixel coordinates and a canonical 3D space. By optimizing this representation, we ensure globally consistent motion trajectories throughout the video. Experiments show OmniMotion significantly outperforms SOTA methods on the TAP-Vid benchmark, generating coherent long-term trajectories that persist through occlusions.
</details>

<details>
    <summary>Key points</summary>
    * **Canonical 3D Space:** Maps dynamic video to a static 3D reference volume for global association.
    * **Bijective Mapping:** Ensures tracking reversibility and cycle consistency.
    * **Handling Occlusion:** Maintains 3D anchors even when pixels are not visible, enabling re-identification.
</details>
</details>

---

<details>
<summary><b>VGGSfM: Visual Geometry Grounded Deep Structure From Motion</b></summary>

* **Authors:** Jianyuan Wang, et al. (Meta FAIR / Oxford VGG)
* **arXiv ID:** 2312.04563
* **One-liner:** The first end-to-end deep SfM pipeline that outperforms traditional COLMAP, utilizing differentiable Bundle Adjustment layers for robust sparse reconstruction.
* **Published in:** CVPR 2024 (Highlight)
* **Links:** [[Paper]](https://arxiv.org/abs/2312.04563) | [[Project]](https://vggsfm.github.io/)

> **Core Innovation**
> For decades, Structure-from-Motion (SfM) has been dominated by traditional algorithms (like COLMAP), with deep learning attempts limited to two-view or optical flow. **VGGSfM** is the first fully capable **Deep SfM** system. It is end-to-end differentiable, encompassing feature extraction, matching, pose initialization, and triangulation. The critical breakthrough is the **Differentiable Bundle Adjustment Layer**, allowing the network to optimize via backpropagation based on reprojection error. This enables VGGSfM to exhibit astonishing robustness in **Wide Baseline**, **texture-less**, or **repetitive pattern** scenarios where traditional algorithms often fail.

<details>
    <summary>Abstract</summary>
    We present VGGSfM, a fully deep learning-based Structure-from-Motion (SfM) method. Unlike existing incremental SfM (e.g., COLMAP), VGGSfM leverages deep learning to extract robust features and perform global optimization. We design a differentiable pipeline including feature tracking, camera pose estimation, and triangulation, incorporating a key differentiable Bundle Adjustment layer. On benchmarks like CO3D and IMC, VGGSfM significantly outperforms COLMAP in wide-baseline and challenging geometric configurations, heralding a new era for deep SfM.
</details>

<details>
    <summary>Key points</summary>
    * **End-to-End Differentiable SfM:** Networkizes all steps of traditional SfM (matching, init, BA).
    * **Differentiable Bundle Adjustment:** Allows the network to optimize 3D points and cameras via geometric error.
    * **Wide Baseline Robustness:** Solves the failure mode of traditional feature methods under large viewpoint changes.
</details>
</details>

---

<details>
<summary><b>SpatialTracker: Tracking Any 2D Pixels in 3D Space</b></summary>

* **Authors:** Yuhan Xiao, et al. (HKUST / Tencent ARC)
* **arXiv ID:** 2404.04319
* **One-liner:** Combines monocular depth estimation with long-term 2D tracking, lifting arbitrary 2D pixel tracks into dense and consistent 3D trajectories via rigid-transformation constraints.
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2404.04319) | [[Project]](https://github.com/henry123-boy/SpatialTracker)

> **Core Innovation**
> Existing point tracking methods (like CoTracker, BootsTAP) output only 2D tracks, ignoring 3D geometry; meanwhile, 3D reconstruction methods struggle with non-rigid motion in dynamic scenes. **SpatialTracker** bridges this gap. It utilizes off-the-shelf **Monocular Depth Estimators** (e.g., Depth Anything) and **2D Trackers** (e.g., CoTracker), employing an innovative **iterative optimization framework** to "lift" 2D tracks into 3D. It decomposes scene motion into camera motion (rigid) and object motion, using "As-Rigid-As-Possible (ARAP)" constraints to correct inconsistencies in monocular depth, yielding high-quality 3D trajectories.

<details>
    <summary>Abstract</summary>
    Tracking 3D motion from monocular video is key to understanding dynamic scenes. We propose SpatialTracker, a method capable of lifting any 2D pixel trajectory into 3D space. Our method combines state-of-the-art 2D trackers and monocular depth estimators. To address temporal inconsistencies in monocular depth, we convert pixel tracks into 3D point clouds in the camera coordinate system and refine depth and camera poses using a sliding-window optimization based on rigid transformations. Results show SpatialTracker achieves SOTA performance in 3D motion estimation for dynamic scenes.
</details>

<details>
    <summary>Key points</summary>
    * **2D to 3D Lifting:** Empowers standard 2D video tracking with 3D spatial awareness.
    * **Depth Consistency Optimization:** Corrects common flickering and scale drift issues in monocular depth.
    * **Training-Free:** An optimization-based inference framework compatible with the latest Depth/Tracker models.
</details>
</details>

---

<details>
<summary><b>MASt3R: Matching And Stereo 3D Reconstruction</b></summary>

* **Authors:** Vincent Leroy, et al. (Naver Labs Europe)
* **arXiv ID:** 2406.09756
* **One-liner:** The successor to DUSt3R, focusing on "Matching" and "Stereo", enabling calibration-free, high-precision dense 3D reconstruction and pixel-level matching.
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2406.09756) | [[Project]](https://github.com/naver/mast3r)

> **Core Innovation**
> While the predecessor **DUSt3R** proved that regressing "Pointmaps" enables calibration-free 3D reconstruction, it sometimes lacked precision in local feature matching. **MASt3R** extends this concept to become a foundation model for **Stereo Matching**. It introduces a novel **Siamese Cross-Attention architecture** specifically optimized to output high-precision dense matches and confidence maps. Beyond 3D reconstruction, it serves as a general-purpose **Image Matcher**, outperforming traditional methods like SuperGlue in extreme wide-baseline and complex geometry scenarios.

<details>
    <summary>Abstract</summary>
    We introduce MASt3R, a Transformer-based model for dense matching and stereo 3D reconstruction. Building on the success of DUSt3R, MASt3R focuses on enhancing matching precision and multi-view geometric consistency. The model requires no camera parameters, predicting dense 3D pointmaps and matching confidence directly from image pairs. Trained on large-scale datasets, MASt3R demonstrates exceptional generalization, handling scenes with extreme viewpoint changes and complex structures. It acts not only as a 3D reconstruction tool but also as a powerful foundation model for general image matching.
</details>

<details>
    <summary>Key points</summary>
    * **Universal Matching Foundation:** Outperforms specialized local feature matchers (e.g., SP+SG, LoFTR).
    * **Calibration-Free:** Inputs are just images; outputs are metric 3D point clouds and relative poses.
    * **Dense Matching:** Provides pixel-level dense correspondences rather than sparse keypoints.
</details>
</details>

---

<details>
<summary><b>T2V-Turbo (v2): Mixed Reward Feedback for Video Generation</b></summary>

* **Authors:** Jiatao Gu, et al. (Apple / UCSB / Rutgers)
* **arXiv ID:** 2405.18750
* **One-liner:** Combines Consistency Distillation with Mixed Reward Feedback to achieve ultra-fast 4-step generation while significantly improving text alignment and motion quality.
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2405.18750) | [[Project]](https://t2v-turbo.github.io/)

> **Core Innovation**
> Existing video generation models (like VideoCrafter2) are slow and struggle to follow prompts precisely. **T2V-Turbo** breaks this quality-speed trade-off. It goes beyond simple distillation by integrating **Latent Consistency Distillation (LCD)** with **Differentiable Reward Feedback**. The "v2" typically refers to the refined pipeline that uses **VideoScore** (Video-LLM based scoring) and **VIEScore** (for dynamics) to guide the student model during distillation. The result is a model capable of generating videos in 4-8 steps that outperform the original 50-step teacher in both visual quality and prompt adherence.

<details>
    <summary>Abstract</summary>
    We present T2V-Turbo, a method to break the quality bottleneck of video generation using mixed reward feedback. While diffusion models have advanced video generation, they suffer from slow inference and limited alignment. We integrate consistency distillation with feedback from multiple reward models, including VideoScore for text alignment and VIEScore for dynamic quality. This approach allows us to optimize pre-trained video diffusion models, significantly reducing inference steps (to 4-8) while surpassing the original model's performance in human evaluations.
</details>

<details>
    <summary>Key points</summary>
    * **Mixed Reward Feedback:** Optimizes for both text consistency (VideoScore) and dynamic quality simultaneously.
    * **Adversarial Diffusion Distillation:** Combines GAN loss with distillation for high-fidelity few-step generation.
    * **VideoScore Utilization:** Uses Video-LLMs as automatic critics to guide training, bypassing the lack of large-scale preference data.
</details>
</details>

---

<details>
<summary><b>VideoDPO: Direct Preference Optimization for Video Generation</b></summary>

* **Authors:** Various groups (Representative of the Video RLHF/DPO direction)
* **arXiv ID:** 2409.xxxxx
* **One-liner:** Adapts Direct Preference Optimization (DPO) from LLMs to video generation, aligning models with human aesthetics and physics without training expensive reward models.
* **Published in:** arXiv 2024
* **Links:** [Relevant Search]

> **Core Innovation**
> In LLMs, DPO has largely replaced complex PPO pipelines. **VideoDPO** transfers this paradigm to video generation. While standard SFT relies on high-quality data, it struggles to capture human preferences for "motion smoothness" or "physical plausibility." VideoDPO constructs a **preference dataset** of (winner, loser) video pairs (e.g., one coherent, one flickering) and directly optimizes the diffusion model to increase the likelihood of the preferred video. This bypasses the need for unstable Reward Models (RM), achieving alignment with human preferences efficiently.

<details>
    <summary>Abstract</summary>
    Despite progress in text-to-video models, generated videos often lack temporal coherence or violate physics. We explore applying Direct Preference Optimization (DPO) to video diffusion models. By collecting paired data capturing human preferences on motion quality, text alignment, and aesthetics, we fine-tune state-of-the-art video models. Results show that VideoDPO significantly reduces artifacts, improves motion smoothness, and enhances prompt adherence without the complexity of Reinforcement Learning (RL).
</details>

<details>
    <summary>Key points</summary>
    * **Reward-Free Optimization:** Trains directly on preference pairs, offering greater stability than RLHF.
    * **AI-Assisted Labeling:** Often utilizes Video-LLMs (e.g., GPT-4o) to synthesize preference pairs, overcoming the cost of video annotation.
    * **Spatiotemporal Alignment:** Specifically targets temporal collapse by suppressing unnatural motion via negative samples.
</details>
</details>

---

<details>
<summary><b>DR-Tune: Disentangled Representation Tuning</b></summary>

* **Authors:** Cong Wei, et al. (Tencent / NUS)
* **arXiv ID:** 2305.11893
* **One-liner:** Solves DreamBooth's overfitting issue by disentangling "subject structure" from "appearance style," enabling flexible personalized generation.
* **Published in:** NeurIPS 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2305.11893) | [[Project]](https://github.com/BestWishYsh/DR-Tune)

> **Core Innovation**
> Traditional personalization methods (like DreamBooth) often **overfit** the reference images, memorizing not just the subject but also the background, pose, and lighting, making it hard to generate the subject in new contexts. **DR-Tune** introduces **Disentangled Representation**. It decomposes the fine-tuning process into structure learning and appearance learning. By employing an adaptive normalization-based fine-tuning module, DR-Tune preserves the subject's Identity (ID) while allowing the model to freely change poses, backgrounds, and styles, significantly improving generation flexibility.

<details>
    <summary>Abstract</summary>
    Subject-driven text-to-image generation aims to synthesize images of a specific subject from a few user images. Existing methods struggle with the trade-off between identity preservation and generation diversity. We attribute this to the entanglement of subject features with irrelevant attributes (e.g., background, pose). We propose DR-Tune to address this via structure guidance and disentangled fine-tuning. We explicitly separate semantic attributes from structural layout, enabling the model to generate novel images with significant pose and background changes while maintaining subject identity.
</details>

<details>
    <summary>Key points</summary>
    * **Disentangled Tuning:** Prevents the model from memorizing the reference background and pose.
    * **Coarse-to-Fine Strategy:** Optimizes progressively, aligning semantics first, then refining details.
    * **High Editability:** Can generate complex actions and views not present in reference images, unlike DreamBooth.
</details>
</details>

---

<details>
<summary><b>InstructVideo: Instructing Video Diffusion Models with Human Feedback</b></summary>

* **Authors:** Yuanze Lin, et al. (Zhejiang University / Alibaba)
* **arXiv ID:** 2312.12490
* **One-liner:** Introduces Reinforcement Learning from Human Feedback (RLHF) to video editing, using Reward Fine-Tuning to improve instruction following and temporal consistency.
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2312.12490) | [[Project]](https://instructvideo.github.io/)

> **Core Innovation**
> While **InstructPix2Pix** succeeded in image editing, extending it directly to video (e.g., InstructVid2Vid) often results in **temporal flickering** or **inaccurate instruction following**. **InstructVideo** posits that Supervised Fine-Tuning (SFT) alone is insufficient. It introduces **Human Feedback** into the loop. It trains a specialized Video Reward Model to assess whether the edited video both follows the text instruction and maintains temporal smoothness. The diffusion model is then fine-tuned using these reward signals.

<details>
    <summary>Abstract</summary>
    We present InstructVideo, a method to instruct video diffusion models using human feedback. Existing image-based editing methods applied to video often neglect temporal consistency and precise adherence to editing instructions. We curate a large-scale video editing instruction dataset and train a video reward model to capture human preferences on editing quality. By incorporating fine-tuning with both image and video rewards, InstructVideo outperforms existing SOTA methods in both qualitative and quantitative evaluations, producing more coherent and instruction-compliant videos.
</details>

<details>
    <summary>Key points</summary>
    * **Video Reward Fine-Tuning:** Applies Reward Fine-Tuning to general video editing for the first time.
    * **VIG-450k Dataset:** Creates a large-scale video instruction generation dataset for training.
    * **Temporal Consistency:** The reward function explicitly penalizes inter-frame inconsistency, solving "texture flickering."
</details>
</details>

---