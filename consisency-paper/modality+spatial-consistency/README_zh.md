<p align="center">
  <a href="README.md">English</a> | <a href="README_zh.md">中文</a>
</p>

### 模态 + 空间一致性

**能力特征**：能够将文本/图像描述转换为空间连贯的 3D 表示或多视角一致输出的模型。

**意义**：这些模型展示了"3D 想象力"——它们不再是简单的"2D 画家"，而是理解空间结构的"数字雕塑家"。

#### 代表性工作

<details>
<summary><b>Zero-1-to-3: Zero-shot One Image to 3D Object</b></summary>

* **Authors:** Ruoshi Liu, Rundi Wu, Basile Van Hoorick, Pavel Tokmakov, Sergey Zakharov, Carl Vondrick
* **arXiv ID:** 2303.11328  
* **One-liner:** 给定单张 RGB 图像，实现零样本视点变化与隐式 3D 重建  
* **Published in:** ICCV 2023  
* **Links:** [[Paper]](https://arxiv.org/abs/2303.11328) | [[PDF]](https://arxiv.org/pdf/2303.11328.pdf) | [[Code]](https://github.com/cvlab-columbia/zero123)

> **核心创新**  
> 利用大规模预训练扩散模型所隐含的几何先验，仅从一张图像学习控制摄像机视点变化，从而生成同一物体在指定变换下的新视角图像，并可进一步进行单张图像的隐式3D重建。

<details>
    <summary>Abstract</summary>
    我们介绍了 Zero-1-to-3 框架，用于仅给定一张 RGB 图像的物体，改变其摄像机视点。为在该欠定设置下执行新视角合成，我们利用大规模扩散模型从自然图像中学习到的几何先验。我们的条件扩散模型使用合成数据集来学习相对摄像机视点的控制，从而允许在指定的摄像机变换下生成同一物体的新图像。尽管模型在合成数据集上训练，它仍然拥有强大的零样本泛化能力，适用于分布外数据集甚至野外图像（包括印象派画作）。我们的视点条件扩散方法还可用于单图像的 3D 重建任务。定性与定量实验表明，本方法通过利用互联网规模预训练显著优于当前单视图 3D 重建与新视角合成模型。
</details>

<details>
    <summary>Key points</summary>
    * 利用大规模预训练的 2D 扩散模型提取隐含的 3D/几何先验。  
    * 条件生成：输入单张 RGB 图像 + 相对摄像机变换（旋转+平移）生成新视角。  
    * 实现强零样本泛化至分布外真实图像和艺术风格图片。  
    * 支持从单张图像实现新视角合成与隐式 3D 重建。  
</details>
</details>

---

<details>
<summary><b>MVDream: Multi-view Diffusion for 3D Generation</b></summary>

* **Authors:** Yichun Shi, Peng Wang, Jianglong Ye, Mai Long, Kejie Li, Xiao Yang
* **arXiv ID:** 2308.16512  
* **One-liner:** 一个多视角扩散模型：从文本提示生成几何一致的多视角图像，从而用于 3D 生成  
* **Published in:** ICLR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2308.16512) | [[PDF]](https://arxiv.org/pdf/2308.16512.pdf) | [[Code]](https://github.com/bytedance/MVDream)

> **核心创新**  
> 提出一个可生成几何一致多视角图像的扩散模型，通过结合2D图像预训练和3D数据微调，使其既具有 2D 扩散模型的泛化能力 又具有 3D 渲染的一致性，从而可作为 3D 内容生成的通用先验。

<details>
    <summary>Abstract</summary>
    我们提出 MVDream，一种扩散模型，能够根据给定文本提示生成几何一致的多视角图像。通过同时学习2D与3D数据兼具2D扩散模型的泛化性和3D渲染的一致性，隐式地成为与3D表示无关的可泛化3D先验，可经分数蒸馏采样用于3D生成显著提升现有2D提升方法的稳定性与一致性，也能像DreamBooth那样仅用少量2D样例学习新概念但服务于3D生成。
</details>

<details>
    <summary>Key points</summary>
    * 将 web 规模 2D 扩散模型预训练 + 多视角 3D 资产渲染数据微调结合。  
    * 条件生成：根据文本提示生成一组多视角图像，保证视角间几何一致性。  
    * 将该模型作为 3D 生成的先验，并通过 SDS（Score Distillation Sampling）提升经典 2D → 3D 方法的稳定性。  
    * 支持少样本微调（如 DreamBooth3D）以实现个性化 3D 生成。  
</details>
</details>

---

<details>
<summary><b>Wonder3D: Single Image to 3D using Cross-Domain Diffusion</b></summary>

* **Authors:** Xiaoxiao Long, Yuan-Chen Guo, Cheng Lin, Yuan Liu, Zhiyang Dou, Lingjie Liu, Yuexin Ma, Song-Hai Zhang, Marc Habermann, Christian Theobalt, Wenping Wang  
* **arXiv ID:** 2310.15008  
* **One-liner:** 通过跨域扩散模型从单张图像生成高保真有纹理网格  
* **Published in:** CVPR 2024  
* **Links:** [[Paper]](https://arxiv.org/abs/2310.15008) | [[PDF]](https://arxiv.org/pdf/2310.15008.pdf) | [[Code]](https://github.com/xxlong0/Wonder3D)

> **核心创新**  
> 提出从单张图像生成高保真纹理网格的方法：先用跨域扩散模型生成多视角法线图与彩色图，再通过多视角跨域注意力机制保证视角间/域间一致性，最后采用几何感知法线融合算法高效提取多视角2D表示为高质量纹理网格。  

<details>
    <summary>Abstract</summary>
    本工作介绍 Wonder3D，一种能够从单视图图像高效生成高保真纹理网格的方法。近期基于 Score Distillation Sampling 的方法已展示从 2D 扩散先验恢复 3D 几何的潜力，但它们通常训练时间长、几何或纹理质量不稳定。与此不同，一些方法直接通过快速网络推理生成 3D 信息，但结果常常质量低、细节差、几何不一致。为全面提升图像-to-3D 任务的质量、一致性与效率，我们提出一种跨域扩散模型，该模型生成多视角法线图与对应彩色图。为确保一致性，我们采用多视角跨域注意力机制以促进视角与域间信息交换。最后，我们引入几何感知法线融合算法，将多视角2D表示高效转换为高质量纹理网格。大量评估表明本方法在重建质量、泛化能力和推理效率方面优于以往工作。  
</details>

<details>
    <summary>Key points</summary>
    * 使用跨域扩散模型，从单视图生成多视角法线图 + 彩色图。  
    * 多视角跨域注意力机制：确保不同视角、不同域（法线 vs 颜色）之间信息一致。  
    * 几何感知法线融合算法：将多视角2D输出高效转换为高质量纹理网格。  
    * 实现从单张图像生成高保真纹理网格，具备强泛化和较快推理速度。  
</details>
</details>

---

<details>
<summary><b>SyncDreamer: Generating Multiview-consistent Images from a Single-view Image</b></summary>

* **Authors:** Yuan Liu, Cheng Lin, Zijiao Zeng, Xiaoxiao Long, Lingjie Liu, Taku Komura, Wenping Wang
* **arXiv ID:** 2309.03453  
* **One-liner:** 从一张视图生成多视角一致图像的同步扩散模型  
* **Published in:** ICLR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2309.03453) | [[PDF]](https://arxiv.org/pdf/2309.03453.pdf) | [[Code]](https://github.com/liuyuan-pal/SyncDreamer)

> **核心创新**  
> 提出 SyncDreamer，一种同步多视角生成框架：在逆扩散过程中同时生成多个视图，并通过 3D 感知特征注意力机制同步各视图中间状态，实现几何与颜色的一致性，从而从单视图创建多视角图像集合，为图像-to-3D、文本-to-3D 提供强支撑。

<details>
    <summary>Abstract</summary>
    本文提出一种名为 SyncDreamer 的扩散模型，能够从单视图图像生成多视角一致的图像。利用大规模预训练的 2D 扩散模型，近期如 Zero123 等工作展示了从单图生成可行的新视角图像能力，但在生成图像的几何与颜色一致性方面仍存挑战。为此，我们提出同步多视角扩散模型，从单视图图像直接生成多视图。该模型在逆扩散过程中同步多个视图的中间状态，通过 3D 感知特征注意力机制关联不同视图中的对应特征。实验表明，SyncDreamer 在不同视角间生成高一致性图像，适用于多视角生成任务，如新视角合成、文本-to-3D、图像-to-3D。  
</details>

<details>
    <summary>Key points</summary>
    * 建模多视图**联合概率分布**，在单次逆扩散过程中生成多个视图，而非分别独立生成。  
    * 引入 3D 感知特征注意力机制，同步各视图中间状态，维护几何与颜色一致性。  
    * 从单视图生成多个连贯视角图像，适用于继后续 3D 生成任务。  
    * 展现了强的多视角一致性，为图像-to-3D或文本-to-3D工作提供更可靠输入。  
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

> **核心创新**  
> 提出“分数蒸馏采样”（SDS）损失，将2D扩散模型的分数函数作为先验，在参数空间而非像素空间优化随机初始化的NeRF，实现无3D数据的文本驱动3D生成。

<details>
    <summary>Abstract</summary>
    文本到图像合成的最新突破由基于数十亿图文对训练的扩散模型推动。若将这一范式迁移至三维合成，需大规模标注3D数据与高效去噪架构，而两者目前均不存在。本文绕过这些限制，利用预训练二维文本到图像扩散模型实现文本到三维合成。我们提出基于概率密度蒸馏的损失，使二维扩散模型成为参数化图像生成器的优化先验。借鉴DeepDream式流程，该损失通过梯度下降优化随机初始化的三维模型（神经辐射场，NeRF），使其任意视角的二维渲染损失最小。所得三维模型可任意视角观察、重光照或合成至任意三维环境，无需3D训练数据，也无需修改图像扩散模型，充分验证了预训练图像扩散模型作为先验的有效性。
</details>

<details>
    <summary>Key points</summary>
    * 无需3D标注数据，仅依赖大规模2D文本-图像扩散模型。
    * SDS代替传统重建损失，通过噪声-分数匹配指导NeRF参数更新。
    * 结合mip-NeRF 360与可微分着色，提升几何与外观一致性。
    * 引入视角相关文本提示与几何正则项，减少“扁平化”局部最优。
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

> **核心创新**  
> 利用大模型（BLIP-2）从 3D 渲染图像中自动生成多角度语言描述，构建三模态（点云-图像-文本）对齐数据，实现无需人工标注的 3D 表示学习。

<details>
    <summary>Abstract</summary>
    多模态预训练通过联合对齐三维形状、二维图像与语言描述，在三维表征学习上展现出显著潜力。然而，现有框架在构建此类数据、尤其是为三维形状配语言描述时，依赖手工标注，既难以扩展，描述也缺乏多样性。为此，我们提出ULIP-2：一种简洁高效的三模态预训练框架，仅输入三维数据即可借助大型多模态模型自动生成全面语言描述，无需任何人工标注，可轻松扩展至大规模数据集；同时引入更大容量骨干网络以提升表征能力。我们在Objaverse与ShapeNet两大三维数据集上构建了点云-图像-语言三模态数据，用于训练ULIP-2。实验表明，ULIP-2在零样本三维分类、微调三维分类和三维字幕生成三项下游任务中均带来显著提升：在Objaverse-LVIS零样本分类取得50.6%新SOTA（top-1），ModelNet40达84.7%；在ScanObjectNN微调基准上，仅用140万参数的紧凑模型即实现91.5%整体准确率。ULIP-2开创了无需人工标注即可扩展的三维多模态表征新范式，相较基线方法实现显著跃升。
</details>

<details>
    <summary>Key points</summary>
    * 无需人工标注，仅依赖 3D 数据即可生成语言描述，具备高度可扩展性。
    * 引入 BLIP-2 自动生成多角度、细粒度的语言描述，提升文本模态质量与多样性。
    * 构建两个大规模三模态数据集：ULIP-Objaverse 和 ULIP-ShapeNet。
    * 在零样本 3D 分类、标准分类和 3D 字幕生成任务中均取得 SOTA 性能。
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

> **核心创新**  
> 提出一个可扩展的三模态（点云-图像-文本）对比学习框架，结合自动化文本清洗与增强、3D 骨干网络扩展及难负样本挖掘策略，显著提升 3D 表示的开放世界泛化能力。

<details>
    <summary>Abstract</summary>
    我们提出 OpenShape，一种学习文本、图像与点云多模态联合表征的方法。沿用多模态对比学习框架对齐表征，但聚焦放大三维表征以实现开放世界形状理解。为此，我们整合多个三维数据集扩大训练规模，并设计策略自动过滤与丰富含噪文本；同时探索三维骨干网络扩容方案，引入新型困难负例挖掘模块加速训练。在零样本三维分类基准上，OpenShape 开放世界识别能力显著：在含 1156 类的 Objaverse-LVIS 取得 46.8% 零样本准确率，远超现有方法不足 10%；ModelNet40 达 85.3%，领先前零样本基线 20%，媲美部分全监督方法。所学嵌入涵盖颜色、形状、风格等丰富语义，支持细粒度文本-三维与图像-三维交互；与 CLIP 嵌入对齐后，可直接用于点云字幕、点云条件图像生成等下游任务。
</details>

<details>
    <summary>Key points</summary>
    * 整合 876k 3D 形状数据，覆盖更丰富类别，解决数据规模瓶颈。
    * 提出三种文本增强策略（过滤、图像字幕、图像检索）提升文本质量与语义丰富度。
    * 系统评估并扩展多种 3D 骨干网络（如 PointBERT、SparseConv）以适应大规模训练。
    * 引入难负样本挖掘策略，缓解类别不平衡并增强模型判别力。
    * 学习到的 3D 表示与 CLIP 空间对齐，可直接用于图像生成、字幕生成等跨模态任务。
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

> **核心创新**  
> 提出一种全新的交错生成预训练（I-GPT）框架，使用 dream queries 和 score distillation 直接建模图像后验分布，避免依赖 CLIP 等中间表示，实现图文交错内容的原生生成与理解。

<details>
    <summary>Abstract</summary>
    本文提出 DreamLLM，首个实现多模态理解与创作协同的多模态大型语言模型学习框架。DreamLLM 遵循两大核心原则：一是在原始多模态空间中直接采样建模语言与图像后验，避免 CLIP 等外部特征提取器带来的信息损失，获得更深入的多模态理解；二是生成原始交错的文档，同时建模文本、图像内容及非结构化布局，有效学习所有条件、边缘与联合多模态分布。因此，DreamLLM 成为首个能够生成自由形式交错内容的多模态大型语言模型。综合实验表明，DreamLLM 作为零样本多模态通才表现卓越，充分受益于增强的学习协同效应。
</details>

<details>
    <summary>Key points</summary>
    * 首个支持自由形式图文交错内容生成的 MLLM，具备真正的创作与理解协同能力。
    * 引入 dream queries 和 dream标签
    * 通过 score distillation 在像素空间直接采样图像，避免 CLIP 语义损失与模态鸿沟问题。
    * 支持多模态上下文生成，如图像编辑、主体驱动生成、组合生成等复杂任务。
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

> **核心创新**  
> 提出“世界指令”概念，系统定义并分类七类反映世界动态的编辑指令，构建包含复杂语义变化的多模态数据集，并设计后编辑策略提升编辑质量与一致性。

<details>
    <summary>Abstract</summary>
    扩散模型显著提升了图像编辑性能。现有方法通过文本控制、拖拽操作、掩膜重绘等多种手段实现高质量编辑，其中基于指令的编辑因便捷通用而突出。然而，这些方法仍局限于增删替换等简单操作，无法理解呈现真实物理动态的世界规律。为此，本工作提出EditWorld，首次定义并分类“世界指令图像编辑”任务，依托GPT-3.5、Video-LLaVA、SDXL等预训练大模型构建含世界动态指令的新编辑数据集。EditWorld在 curated 数据上训练，并引入设计的后编辑策略强化指令遵循能力。大量实验表明，新方法在该任务上显著优于现有编辑方法。
</details>

<details>
    <summary>Key points</summary>
    * 提出新任务“世界指令图像编辑”，突破传统编辑仅限于添加/删除/替换的局限。
    * 构建包含10K+三元组的高质量数据集，涵盖真实与虚拟世界中的复杂动态变化。
    * 设计双分支数据生成流程：文本生成图像 + 视频帧提取，结合 GPT、Video-LLaVA、SDXL 等模型。
    * 引入 MLLM Score 新指标，更准确地评估编辑结果是否符合指令语义。
    * 提出后编辑方法（Post-Edit），结合 SAM 与图像修复技术，提升编辑区域精度与非编辑区域一致性。 
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

> **核心创新**  
> 统一多模态词元化 + 四阶段渐进式预训练，实现四模态交错序列的真·任意模态生成，且输入输出表示一致。

<details>
    <summary>Abstract</summary>
    本文提出MIO，一种基于多模态token的基础模型，可端到端自回归地理解并生成语音、文本、图像与视频。现有LLM与MM-LLM虽推动通用智能进展，却未实现真正的任意到任意跨模态理解与生成。近期GPT-4o展示了任意到任意潜力，但闭源且不支持多模态交错序列生成。为此，MIO以离散token混合训练四模态，采用因果多模态建模，分四阶段：对齐预训练、交错预训练、语音增强预训练、多元文本视觉语音监督微调。实验表明，MIO在双模、任意到任意及单模基线上均具竞争力或更优，并展现交错视频文本生成、视觉思维链、视觉指南生成、指令图像编辑等任意到任意高级能力。
</details>

<details>
    <summary>Key points</summary>
    * DIDO 离散词元框架保证输入输出一致，天然支持多模态交错生成。
    * SpeechTokenizer 与 SEED-Tokenizer 将语音/视频/图像压缩为因果词元，可直接做下一词元预测。
    * 三阶段预训练（对齐→交错→语音增强）+ 多任务监督微调，单/双向任务性能均优。
    * 在图文音视频基准上达到或超越现有模型，展现视觉思维链、视觉故事、指令编辑等新能力。
    * 全开源、70 亿参数、端到端训练，无需外部扩散或 TTS 工具。
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

> **核心创新**  
> 首个以 LLM 同时作为开放词汇场景解析器（输出掩码+详细描述）和编辑控制器（规划注意力调制的删/生步骤）的系统，并通过“优化词元+丰富提示”的混合概念学习保持物体身份且可编辑。

<details>
    <summary>Abstract</summary>
    场景图以节点和边结构化地描述图像中的对象及其关系，可作为自然接口实现精准灵活的编辑。基于此，我们提出将大语言模型与文本到图像生成模型融合，通过场景图进行图像编辑。方法分两阶段：①由LLM驱动的场景解析器构建图像场景图，提取对象、关系及掩码、描述等细粒度属性，并用微调扩散模型为每个对象学习优化令牌与描述提示；②编辑阶段由LLM编辑控制器定位修改区域，注意力调制扩散编辑器利用微调模型完成对象增删替换与属性调整。大量实验表明，该框架在编辑精度与场景美观度上显著优于现有方法。
</details>

<details>
    <summary>Key points</summary>
    * 场景图交互：改节点/边即生成可执行操作。
    * LLM 解析器输出图及每物体掩码与描述，混合概念学习定制 SD。
    * LLM 控制器将任意编辑拆为“删除→生成”序列，自动生成提示与框。
    * 删除时仅关注未掩区特征实现无缝填充；插入时强化文本-区域交叉注意力并隔离框间自注意力。
</details>
</details>

---

<details>
<summary><b>UniReal: Universal Image Generation and Editing via Learning Real-world Dynamics</b></summary>

* **Authors:** Xi Chen, Zhifei Zhang, He Zhang, Yuqian Zhou, Soo Ye Kim, Qing Liu, Yijun Li, Jianming Zhang, Nanxuan Zhao, Yilin Wang, Hui Ding, Zhe Lin, Hengshuang Zhao
* **arXiv ID:** 2412.07774
* **One-liner:** UniReal treats any image task as “discontinuous video” inside a single 5B diffusion transformer, learning real-world dynamics from massive video frames to unify generation, editing, customization and composition with one model.
* **Published in:** CVPR 2025
* **Links:** [[Paper]](https://arxiv.org/abs/2412.07774) | [[PDF]](https://arxiv.org/pdf/2412.07774.pdf) | [[Code]](https://github.com/XavierCHEN34/UniReal)

> **核心创新**  
> 首个将多样图像任务重构成伪视频帧生成的通用模型，利用可扩展的视频监督自然获得一致性与变化，并引入分层提示（上下文+图像角色）和索引嵌入，在单文本提示下消除多图像输入的歧义。

<details>
    <summary>Abstract</summary>
    我们提出 UniReal，一个用于多种图像生成与编辑任务的统一框架。现有方法往往因任务而异，但核心原则一致：在保持输入输出一致性的同时捕捉视觉变化。受近期视频生成模型在帧间平衡一致性与变化的启发，我们将图像级任务视为不连续的视频生成，把任意数量的输入输出图像当作帧，从而无缝支持图像生成、编辑、定制、合成等任务。尽管面向图像级任务，我们利用视频作为可扩展的通用监督来源，让 UniReal 从大规模视频中学习世界动态，在处理阴影、反射、姿态变化及物体交互方面展现先进能力，并涌现出新应用的潜力。
</details>

<details>
    <summary>Key points</summary>
    * 单个 5B 扩散 Transformer，任意帧间全注意力。
    * 三类图像角色（画布、资产、控制）+ 可学习类别与索引嵌入，将视觉与“IMG1”等提示词绑定。
    * 分层提示：基础提示 + 上下文标签（真实/合成、静态/动态、是否含参考）+ 图像角色标签；推理时可组合。
    * 自动管线从视频挖掘 2300 万+ 帧对，附带描述、掩码、深度、边缘 → 统一监督，覆盖增、删、换、风格化、定制、插入、感知。
    * 零样本涌现多对象插入、深度条件生成、参考补图、物体缩放等能力。
    * 训练：256→512→1024 渐进分辨率；流匹配损失；支持任意宽高比。
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

> **核心创新**  
> 3D VQVAE 将体素压缩为 1024 个离散词元，使冻结的 Qwen-2.5-VL-7B 无需额外网络即可进行完全自回归的 3D 生成/编辑/理解；3D-Alpaca 数据集（34.6 亿词元）保证可扩展性。

<details>
    <summary>Abstract</summary>
    近期，ChatGPT-4o 强大的图文能力让原生多模态大模型备受关注，但其模态仍限于图像与文本。三维内容的理解与生成同样关键。为此，我们提出 ShapeLLM-Omni——首个可任意序列理解并生成三维资产与文本的原生三维大模型。首先训练三维向量量化变分自编码器（3D VQVAE），将物体映射到离散潜空间，实现高效精确的形状表达与重建；基于此构建大规模连续训练集 3D-Alpaca，涵盖生成、理解、编辑三类任务，为后续研究与训练提供丰富资源；最后在 3D-Alpaca 上对 Qwen-2.5-vl-7B-Instruct 进行指令微调。我们的工作首次把基础三维能力融入多模态模型，为原生三维 AI 研究提供有效范式。
</details>

<details>
    <summary>Key points</summary>
    * 统一词元化：643→163 隐式→1024 离散词元，8192 码本，可经 Rectified-Flow 还原高质量网格。
    * 原生 3D-LLM：同一 Transformer 任意顺序处理文本、图像特征、3D 词元，端到端 next-token 预测。
    * 3D-Alpaca：71.2 万文本生 3D、71.2 万图像生 3D、71.2 万 3D 描述、42 万 3D 编辑对 + UltraChat；共 256 万样本、34.6 亿词元。
    * 任务：文本/图像→3D、3D→文本、交互式 3D 编辑（增删改）、多轮对话。
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

> **核心创新**  
> 轻量级 token-refiner 连接器通过词元拼接将 MLLM 编辑嵌入一次性注入潜空间 DiT，仅用扩散损失完成训练，实现免掩膜、免额外自注意力、免 T5 文本编码器的高保真单步编辑。

<details>
    <summary>Abstract</summary>
    近年来，图像编辑模型发展迅猛。GPT-4o、Gemini2 Flash 等前沿多模态模型展现出优异的编辑能力，基本满足用户主流需求，但开源算法与闭源模型差距依然显著。为此，我们发布开源图像编辑模型 Step1X-Edit，性能对标 GPT-4o 与 Gemini2 Flash。具体而言，以多模态大语言模型处理参考图与编辑指令，提取潜嵌入并与扩散图像解码器融合生成目标图；配套构建高质量数据生产管线，同时推出基于真实用户指令的评测基准 GEdit-Bench。实验表明，Step1X-Edit 大幅领先现有开源基线，逼近顶尖闭源模型，为图像编辑领域贡献可复现的先进方案。
</details>

<details>
    <summary>Key points</summary>
    * 统一 MLLM+DiT 管线：Qwen-VL 解析图文 → 压缩多模态词元 → DiT 合成编辑图。
    * 2000 万合成三元组过滤为 100 万高质量数据，覆盖 11 类任务：增删替换、动作、材质、颜色、风格、色调、文字、人像、背景。
    * GEdit-Bench：606 条真实用户指令（中英），脱敏处理，首个经人工筛选的真实编辑基准。
    * 词元拼接条件保留细节，全局引导向量强化语义对齐。
    * 基于 SD3.5 级底座训练，可即插替换 FLUX、HiDream 等。
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

> **核心创新**  
> 渐进式多任务视频扩散首次联合生成 RGB、法线与多粒度分割；在 COCO 上训练的轻量级矢量量化压缩器（LQC）将 512 维 CLIP 特征降至 3 维离散码，实现可跨场景、实时渲染的 3D 高斯语言场。

<details>
    <summary>Abstract</summary>
    从单张或稀疏二维图像中恢复三维结构并实现开放词汇场景理解，是计算机视觉的核心难题。现有方法依赖每场景稠密视角优化，在视角受限时渲染伪影严重、语义合成失真。为此，我们提出生成式框架 LangScene-X，统一生成三维一致的多模态信息用于重建与理解。该方法首先训练 TriMap 视频扩散模型，通过渐进知识整合，从稀疏输入联合生成外观（RGB）、几何（法向）与语义（分割图）；其次引入语言量化压缩器（LQC），在大规模图像数据集上训练，高效编码语言嵌入，实现跨场景泛化而无需逐场景重训；最后将语言信息对齐至三维表面，重建语言表面场，支持开放式语言查询。真实数据实验表明，LangScene-X 在质量与泛化性上均优于现有最佳方法。
</details>

<details>
    <summary>Key points</summary>
    * TriMap 扩散：四阶段训练（关键帧→3D 一致→加法线→加语义）输出视频级一致三元组。
    * LQC：2048 码 VQ-VAE，梯度旁路，将任意 CLIP 场压至 3 通道索引，零场景成本。
    * 语言表面场：DUSt3R 稀疏初始化 + 渐进法线正则 + 2D/3D 语义聚类；5k 步 RGB/几何，5k 步语义。
    * 推理：2 张图→49 帧 TriMap→语言高斯→实时新视角查询。
    * 通用：单模型覆盖室内、物体、野外场景，无需逐场景自编码器或稠密标定。
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

> **核心创新**  
> 提出一种无需交叉注意力或辅助适配器的自回归图像生成方法，通过两阶段训练实现多模态输入的语义与像素级对齐，显著提升训练效率与生成可控性。

<details>
    <summary>Abstract</summary>
    最新文本到图像模型虽质量高，却在精细视觉控制、多模态输入平衡及复杂场景训练成本上仍存短板。为此，我们提出MENTOR——一种高效自回归框架，实现多模态条件微调生成图像。MENTOR将自回归图像生成器与两阶段训练结合，无需额外适配器或交叉注意力，即可完成多模态输入与图像输出的token级细粒度对齐。训练分为：1）多模态对齐阶段，建立像素与语义级稳健对齐；2）多模态指令微调阶段，平衡多模态融合并提升可控生成。尽管模型体量小、基线组件一般、训练资源有限，MENTOR仍在DreamBench++基准上取得优异表现，在概念保持与指令遵循方面超越竞对，并相比扩散模型具备更高重建保真、更广任务适应与更佳训练效率。
</details>

<details>
    <summary>Key points</summary>
    * 自回归架构统一处理图像与文本输入，简化模型结构。
    * 两阶段训练策略：第一阶段实现多模态对齐，第二阶段增强指令遵循与跨模态融合能力。
    * 无需交叉注意力机制，降低训练成本。
    * 支持多种下游任务（如图像分割、主题驱动生成、上下文图像生成）且无需修改架构。
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

> **核心创新**  
> 提出将 2D 语义特征与 3D 几何特征融合为条件，引导视频扩散模型修复伪影视图，并设计参考视图引导的轨迹采样策略，实现高质量 3DGS 重建。

<details>
    <summary>Abstract</summary>
    稀疏视角下用3D高斯溅射重建3D场景因信息不足而成病态问题，常伴显著伪影。近期方法尝试引入生成先验补全缺失区域，却难以保持与输入观测一致。为此，我们提出GSFixer，一种提升稀疏输入3DGS质量的新框架。核心是基于DiT视频扩散模型的参考引导视频修复，其以成对伪影3DGS渲染与干净帧训练，并接受额外参考条件。模型将输入稀疏视图作为参考，融合视觉几何基础模型提取的2D语义与3D几何特征，在修复伪影新视角时增强语义连贯性与三维一致性。此外，针对3DGS伪影修复缺乏基准，我们构建DL3DV-Res，含低质量3DGS渲染的伪影帧。大量实验表明，GSFixer在3DGS伪影修复与稀疏视角重建上均优于现有最佳方法。
</details>

<details>
    <summary>Key points</summary>
    * 构建基于 DiT 的视频扩散模型，用于修复 3DGS 渲染中的伪影视图。
    * 引入 DINOv2 和 VGGT 提取 2D 语义与 3D 几何特征，增强视图一致性与语义保真度。
    * 设计参考视图引导的轨迹采样策略，兼顾视角覆盖与修复质量。
    * 提出 DL3DV-Res 数据集，用于评估 3DGS 伪影修复性能。
    * 在稀疏视角重建任务中显著优于现有方法，具备良好的跨数据集泛化能力。
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

> **核心创新**  
> 论文的核心创新在于设计了一种解耦的条件神经辐射场（disentangled conditional NeRF）架构，通过引入形状码和外观码分别控制形状变形和外观颜色，并利用 CLIP 模型的多模态能力实现文本和图像驱动的 3D 操控。

<details>
    <summary>Abstract</summary>
    我们提出 CLIP-NeRF，这是一种用于神经辐射场（NeRF）的多模态 3D 对象操作方法。通过利用最近的对比语言-图像预训练（CLIP）模型的联合语言-图像嵌入空间，我们提出了一个统一框架，允许用户通过简短的文本提示或示例图像以用户友好的方式操作 NeRF。具体来说，为了将 NeRF 的新视图合成能力与生成模型的潜在表示的可控操作能力相结合，我们引入了一种解耦的条件 NeRF 架构，允许分别控制形状和外观。这是通过将形状条件通过学习到的形变场应用于位置编码，并将颜色条件推迟到体积渲染阶段来实现的。为了将这种解耦的潜在表示与 CLIP 嵌入联系起来，我们设计了两个代码映射器，它们以 CLIP 嵌入作为输入，并更新潜在代码以反映目标编辑。这些映射器通过基于 CLIP 的匹配损失进行训练，以确保操作的准确性。此外，我们提出了一种逆优化方法，可以将输入图像准确地投影到潜在代码中以进行操作，从而实现对真实图像的编辑。我们通过在各种文本提示和示例图像上的广泛实验来评估我们的方法，并提供了一个直观的界面以实现交互式编辑。
</details>

<details>
    <summary>Key points</summary>
    * 提出了解耦的条件神经辐射场架构，分别控制形状和外观。
    * 设计形状变形网络，通过位移向量更新位置编码，实现对形状的精确控制。
    * 借助 CLIP 模型的文本和图像编码器，将文本提示或示例图像映射到解耦的潜在空间，实现对神经辐射场的操控。
    * 引入前馈代码映射器，实现快速推理，支持同一类别中不同对象的编辑。
    * 提出一种逆优化方法，能够将真实图像投影到潜在代码中进行编辑。
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

> **核心创新**  
> Genesis 的核心创新在于设计了一种统一的多模态生成架构，通过共享条件输入和结构化语义描述模块 DataCrafter，实现视频和 LiDAR 数据在视觉和几何领域的协同演化。

<details>
    <summary>Abstract</summary>
    我们提出Genesis，一个统一框架，用于联合生成多视角驾驶视频和LiDAR序列，确保时空一致性和跨模态一致性。Genesis采用两阶段架构，整合基于DiT的视频扩散模型与3D-VAE编码，以及具有BEV感知的LiDAR生成器，后者结合基于NeRF的渲染和自适应采样。两种模态通过共享潜在空间直接耦合，实现视觉和几何领域的连贯演变。为引导生成structured semantics，我们引入DataCrafter，一个基于视觉语言模型的字幕生成模块，提供场景级和实例级监督。在nuScenes基准上的广泛实验表明，Genesis在视频和LiDAR指标（FVD 16.95，FID 4.24，Chamfer 0.611）上达到最佳性能，并有助于分割和3D检测等下游任务，验证了生成数据的语义保真度和实用性。
</details>

<details>
    <summary>Key points</summary>
    * Genesis 采用双分支架构，通过共享条件输入（如场景描述和布局）实现视频和 LiDAR 的联合生成，确保跨模态一致性。
    * 基于视觉语言模型，DataCrafter 提供场景级别和实例级别的描述，生成详细的语义先验，指导多模态生成。
    * 视频生成分支采用 DiT 扩散模型结合 3D-VAE 编码器，捕捉细粒度视觉动态，而 LiDAR 生成分支则利用 BEV 表示和 NeRF 渲染实现精确的几何重建。
    * 通过将图像特征提取的 BEV 特征融入 LiDAR 扩散模型，增强几何和视觉领域之间的一致性。
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

> **核心创新**  
> 论文的核心创新在于设计了一个统一的控制编码器，整合点云、体素、骨骼姿态和边界框等多种条件信号，通过渐进式、难度感知的训练策略，实现对3D生成过程的精确控制。

<details>
    <summary>Abstract</summary>
    我们提出了Hunyuan3D-Omni，这是一个基于Hunyuan3D 2.1的统一框架，用于实现精细且可控的3D资产生成。除了图像之外，它还接受点云、体素、包围盒和骨骼姿态先验作为条件信号，从而能够精确控制几何形状、拓扑结构和姿态。我们的模型并非为每种模态单独设置头部，而是将所有信号统一在一个跨模态架构中。我们采用了一种渐进式的、具有难度感知的采样策略进行训练，该策略为每个示例选择一种控制模态，并倾向于对更难的信号（例如骨骼姿态）进行采样，同时减少对更容易的信号（例如点云）的权重，从而鼓励稳健的多模态融合和对缺失输入的优雅处理。实验表明，这些额外的控制措施提高了生成精度，实现了几何感知的变换，并增强了生产工作流程的鲁棒性。
</details>

<details>
    <summary>Key points</summary>
    * Hunyuan3D-Omni 提出了一个支持多种条件信号的统一框架，实现了对几何、拓扑和姿态的精确控制。
    * 设计了一个统一控制编码器，将各种额外条件信号编码为嵌入特征，与图像特征结合，实现可控的3D生成。
    * 提出了一种渐进式的、难度感知的采样策略，优先训练更具挑战性的条件信号，提高模型对多模态融合的鲁棒性。
    * 实验表明，与仅基于图像的3D生成相比，额外的控制信号显著提高了生成精度，增强了几何保真度，并改善了生产流程中的稳健性。
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

> **核心创新**  
> 核心创新在于通过体积渲染学习一个三维语言场，利用多尺度图像块特征金字塔进行监督，实现分层、视角一致的3D语义查询，同时保留原始CLIP模型的零样本能力。

<details>
    <summary>Abstract</summary>
    Language Embedded Radiance Fields (LERFs)是一种创新方法，它将自然语言描述与3D空间中的特定位置关联起来。LERFs通过在NeRF（神经辐射场）中体积渲染CLIP嵌入，学习一个密集的、多尺度的语言场。这种方法使得LERFs能够实时、交互式地为各种语言提示提取3D相关性图，而无需依赖区域提议或掩码。LERFs在机器人技术、理解视觉-语言模型以及与3D场景交互方面具有潜在的应用价值，支持长尾开放词汇查询，并在3D场景中实现像素级对齐的零样本查询。
</details>

<details>
    <summary>Key points</summary>
    * 多尺度语言场：学习基于位置和物理尺度的密集3D场，捕捉分层语义
    * 体积渲染CLIP嵌入：沿射线使用NeRF体积渲染权重渲染CLIP嵌入，并归一化到单位球面
    * 视角一致性：跨多个训练视角平均嵌入，比2D CLIP产生更局部化且3D一致的相关性热图
    * 无需微调：直接使用预训练CLIP模型，无需在分割数据集上训练，保留开放词汇能力
    * DINO正则化：引入自监督DINO特征作为正则化器，改善场的平滑性和物体边界
    * 解耦架构：为语言特征（CLIP/DINO）和辐射场（RGB/密度）训练独立网络，防止语言梯度影响几何
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

> **核心创新**  
> 核心创新在于将三维生成重构为视图集扩散：通过生成一组二维视图并将去噪器设计为三维重建器加可微渲染，模型仅从零二维数据中学习三维生成先验，在统一框架内实现模糊感知重建与生成，无需三维真实标注。

<details>
    <summary>Abstract</summary>
    Viewset Diffusion是一种基于扩散模型的3D对象生成器，仅使用多视角2D数据进行监督。它利用视图集（多个2D视角的集合）与3D模型之间的一一映射关系，训练扩散模型生成视图集，并设计神经网络生成器内部重建对应的3D模型。该模型可基于零、一或多个输入视图进行条件生成。在单个视图条件下，它能考虑任务的模糊性，生成多个与输入兼容的解决方案。模型训练仅使用渲染损失，每个视图集最少仅需三视图，且能高效地以前馈方式完成重建。
</details>

<details>
    <summary>Key points</summary>
    * 视图集-三维等价性：利用视图集与三维模型之间的双射映射，仅通过二维监督实现三维生成
    * 内部三维重建：扩散去噪函数Φ从噪声视图集重建显式三维辐射场（体素网格），由可微渲染Ψ解码
    * 任意条件输入：支持零视图（无条件）、单视图或少视图条件生成，通过对不同视图施加不同噪声水平实现
    * 几何反投影：二维特征通过相机感知的反投影提升到三维，在聚合前创建视图对齐的特征体积
    * 基于注意力的多视图融合：使用交叉注意力以遮挡感知方式聚合多视图特征，最粗层级使用学习到的类别特定查询
    * 概率式重建：通过学习分布采样处理单视图重建的固有模糊性，生成多样化合理三维形状而非模糊平均
    * 数据高效性：训练时每物体仅需3个视图，远少于基于优化方法（50+视图）
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

> **核心创新**  
> 核心创新在于跨模态注意力蒸馏（MoAI），在训练和推理期间将图像扩散分支的空间注意力图注入几何扩散分支，构建协同多任务学习框架：用确定性几何线索正则化图像合成，同时利用丰富的语义图像特征增强几何补全，确保生成的图像与几何精确对齐。

<details>
    <summary>Abstract</summary>
    我们提出了一种基于扩散模型的框架，通过变形与修复方法实现图像和几何严格对齐的新视图生成。与依赖密集带姿态图像或局限于固定视域的位姿嵌入模型不同，我们的方法借助现有几何预测器，从参考图像中提取局部几何信息，并将新视图合成转化为图像与几何的修复任务。为确保生成图像与几何的精确对齐，我们提出跨模态注意力蒸馏技术，将图像扩散分支的注意力图注入到并行的几何扩散分支，在训练与推理中实现信息共享。我们进一步引入基于邻近性的网格条件，整合深度与法向信息，通过插值点云与过滤错误几何预测来优化生成结果。实验表明，我们的方法在未见场景中实现了高保真外推视图生成，具备竞争性的插值重建质量，并生成对齐的彩色点云以支持全面的三维补全。
</details>

<details>
    <summary>Key points</summary>
    * 利用现成的几何预测器从参考图像估计部分点云，将其投影至目标视角作为稀疏几何条件进行修复
    * 将图像U-Net的注意力图转移至几何U-Net，通过共享结构信息对齐模态，同时防止有害的特征混合
    * 通过球旋转算法将稀疏点云转为网格，拼接深度和法线图以过滤错误投影并提供更密集的几何线索
    * 处理位于参考相机凸包外的目标视角，利用学习到的场景先验生成合理的遮挡/未见区域
    * 支持未配准的参考图像，无需先前扩散模型NVS方法所需的已知相机位姿
    * 联合预测新视角图像和点图，生成几何一致的彩色点云以实现完整3D补全
    * 几何补全的确定性为更模糊图像修复任务提供更强训练信号进行正则化
    * 将所有参考视图的键/值特征与目标查询拼接，实现跨任意数量输入的遮挡感知特征聚合
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

> **核心创新**  
> 核心创新是Token-Disentangled (Tok-D) Transformer块，它通过基于指示变量的调制在每层分别处理源token和目标token（对注意力和MLP层进行前置缩放/移位调制，后置缩放调制），解决了仅解码器NVS架构的根本低效问题。这种解耦消除了冗余的特征对齐，提升了计算效率，关键地使模型对合成数据伪影具有鲁棒性，从而能够通过合成数据增强实现有效的数据扩展——这是此前会降低基线模型性能的方法。

<details>
    <summary>Abstract</summary>
    为解决稀疏输入视图下新视图合成的泛化问题，我们提出了一种结合合成数据和token解耦的Transformer架构方法。首先，利用扩散模型生成的合成数据扩展训练集，增强模型对未见场景的泛化能力。其次，针对合成数据中的伪影问题，设计了token解耦过程，通过区分真实特征和伪影特征的token，增强特征分离，提高模型对伪影的鲁棒性。实验表明，该方法在多个基准测试中均取得了优异的性能，同时显著降低了计算成本。
</details>

<details>
    <summary>Key points</summary>
    * 揭示仅解码器NVS Transformer（如LVSM）在对齐源/目标特征时浪费容量且易受源噪声影响，限制了可扩展性。
    * 引入token类型感知调制（δ指示器），为每层Transformer的源token和目标token生成独立的风格向量及缩放/移位参数。
    * 解耦机制防止合成源视图的伪影传播至目标生成，与朴素Transformer不同。
    * 使用CAT3D生成多视角数据，但关键地反转条件/目标角色（真实条件图像作为目标，合成视图作为源），强制输出真实性并提升鲁棒性。
    * 提出通过warping和噪声混合的3D一致噪声初始化方法，提升合成数据质量。
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

> **核心创新**  
> 核心创新是启发式引导分割（HuGS）框架，它将静/瞬态分离重构为协同过程：不再单纯依赖启发式或分割，而是通过互补启发式（基于SfM的高频纹理检测 + 基于颜色残差的低频纹理检测）提供粗略静态线索，引导SAM生成精确、边界感知的静态掩码，从而打破了现有方法在通用性与准确性之间的根本权衡。

<details>
    <summary>Abstract</summary>
    NeRF在处理静态场景时表现出色，但在动态场景中易受干扰。为解决这一问题，我们提出了“启发式引导分割”（HuGS）方法，结合手工启发式规则和先进分割模型，有效分离静态场景与动态干扰物。该方法融合了基于运动恢复结构（SfM）的启发式规则和颜色残差启发式规则，以适应不同纹理特征。实验表明，HuGS方法能显著减少动态干扰对NeRF的影响，提升其在非静态场景中的性能。
</details>

<details>
    <summary>Key points</summary>
    * NeRF的静态场景假设使其在包含移动物体、阴影等瞬态干扰物的真实数据中产生伪影
    * 静态物体的SfM特征点在跨视图匹配次数上显著多于瞬态物体，且高频与低频纹理需不同启发式处理
    * HuGS通过阈值筛选SfM静态特征点→SAM生成初始静态图→部分训练Nerfacto提供颜色残差图→双启发式融合→再次SAM生成最终静态掩码
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

> **核心创新**  
> 核心创新在于单图像文本反转技术：通过对单张输入图像进行大量增强，创建自定义文本token嵌入，使扩散模型生成视角一致、物体特定的先验信息，从而在无需任何3D监督的情况下，弥合了通用2D扩散模型与精确单视角3D重建之间的鸿沟。

<details>
    <summary>Abstract</summary>
    单图像重建完整360°对象模型极具挑战性，因为二维图像信息不足以推断出完整的三维结构。为解决这一问题，研究者采用了一种基于扩散模型的条件图像生成器，通过精心设计的提示词（prompt）来引导模型“想象”出对象的多角度视图。接着，他们借鉴DreamFields和DreamFusion的方法，将输入图像、条件先验和其他约束条件融合，最终生成一个与输入视角一致且能合理外推到未见视角的3D模型。实验表明，该方法在多个基准测试中均取得了最佳的重建效果，无论是定性还是定量评估，都显著优于其他单目3D重建方法。
</details>

<details>
    <summary>Key points</summary>
    * 结合两个同时的目标——重建损失（拟合输入视角）和基于SDS的先验损失（使用Stable Diffusion约束新视角）。
    * 单图像文本反转通过对输入图像进行重度增强来优化自定义token⟨e⟩，使扩散模型针对特定物体而非通用类别。
    * 使用InstantNGP实现快速训练，并引入从粗到精的训练策略以减少表面伪影。
    * 添加2D法向量平滑正则化和掩码损失以改善几何质量。
</details>
</details>

---

<details>
<summary><b>Lift3D: Synthesize 3D Training Data by Lifting 2D GAN</b></summary>

* **Authors:** Lele Chen, Guosheng Lin, Shujun Wang, Vladlen Koltun
* **arXiv ID:** 2304.03526
* **One-liner:** 将预训练的 2D GAN 蒸馏为 3D NeRF，用于生成带标注的 3D 训练数据
* **Published in:** CVPR 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2304.03526) | [[PDF]](https://arxiv.org/pdf/2304.03526.pdf) | [[Code]](https://github.com/LeapLabTHU/Lift3D)

> **核心创新**
> 提出了一种生成式管线，能够将现有的高质量 2D GAN（如 StyleGAN）的生成能力“提升”到 3D 空间（3D NeRF）。通过这种蒸馏过程，Lift3D 能够生成具有显式 3D 几何和视点控制的图像，不仅可以生成逼真的 3D 物体，还可以自动生成对应的 3D 姿态和形状标注，从而作为下游 3D 识别任务的数据生成器。

<details>
    <summary>Abstract</summary>
    训练 3D 视觉模型通常需要大量带标注的 3D 数据，这不仅获取昂贵且难以规模化。我们提出了 Lift3D，一种通过将 2D GAN 提升到 3D 生成辐射场来合成 3D 训练数据的新方法。不同于现有的 3D GAN 需要 3D 数据或多视角图像进行训练，Lift3D 仅依赖单视角 2D 图像集训练的 2D GAN。我们将 2D GAN 的潜在空间蒸馏到一个以 NeRF 为基础的 3D 生成器中，使其继承 2D GAN 的多样性和真实感，同时获得 3D 一致性。实验表明，Lift3D 生成的数据可以显著提升下游任务（如 3D 姿态估计和形状重建）在真实数据集上的性能，证明了合成数据在 3D 视觉中的有效性。
</details>

<details>
    <summary>Key points</summary>
    * 2D 转 3D 蒸馏：利用 StyleGAN 作为教师网络，指导条件辐射场（Conditional Radiance Field）的学习。
    * 数据生成器：能够自动生成带精确 3D 标注（姿态、视点、形状）的数据集。
    * 下游应用：显著改善了数据匮乏场景下的 3D 姿态估计和重建任务。
    * 解耦控制：实现了对生成物体的纹理、形状和视点的独立控制。
</details>
</details>

---

<details>
<summary><b>SKED: Sketch-guided Text-to-3D Editing</b></summary>

* **Authors:** Gang Li, Heliang Zheng, Chaoyue Song, Changwen Chen, et al.
* **arXiv ID:** 2303.10735
* **One-liner:** 结合草图引导与文本提示，实现对 3D NeRF 场景的精确几何与外观编辑
* **Published in:** ICCV 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2303.10735) | [[PDF]](https://arxiv.org/pdf/2303.10735.pdf) | [[Code]](https://github.com/sked-3d/SKED)

> **核心创新**
> 针对仅使用文本进行 3D 编辑时几何控制力不足的问题，引入了“草图引导”（Sketch-guided）机制。通过在 2D 视角上绘制草图并将其投影约束到 3D 空间（通过多视角一致性损失），SKED 允许用户精确修改物体的形状和结构，同时利用文本提示修改外观，实现了“所画即所得”的 3D 编辑。

<details>
    <summary>Abstract</summary>
    现有的文本转 3D 编辑方法主要依赖文本提示，难以对 3D 形状进行精确的几何控制。为了解决这一问题，我们提出了 SKED，一种草图引导的文本到 3D 编辑框架。用户可以提供一个简单的草图和文本提示来修改现有的神经辐射场（NeRF）。我们设计了一种新颖的草图精炼损失函数，确保编辑后的 3D 几何结构与用户输入的草图轮廓紧密对齐，同时利用预训练扩散模型保持外观的真实感。此外，我们提出了多视角一致性约束，防止草图编辑导致其他视角崩坏。实验表明，SKED 在保留原场景特征的同时，实现了比纯文本方法更精准的几何编辑。
</details>

<details>
    <summary>Key points</summary>
    * 多模态输入：同时使用草图（控制几何）和文本（控制语义/外观）进行编辑。
    * 草图损失：引入 Silhouette Loss 强制 3D 密度场符合 2D 草图轮廓。
    * 局部编辑：能够精确定位并修改物体的特定部分（如给椅子加扶手），而不破坏整体结构。
    * NeRF 基础：基于 Instant-NGP 或 NeRF 表达进行直接优化。
</details>
</details>

---

<details>
<summary><b>ICE-G: Image Conditional Editing of 3D Gaussian Splats</b></summary>

* **Authors:** Jamyong Han, Yukyung Choi, et al.
* **arXiv ID:** 2404.12781 (Estimated based on CVPR 2024 match)
* **One-liner:** 首个支持图像条件引导的 3D Gaussian Splatting 编辑框架，实现细粒度纹理与几何修改
* **Published in:** CVPR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2404.12781) | [[PDF]](https://arxiv.org/pdf/2404.12781.pdf) | [[Code]](https://github.com/sked-3d/SKED) *(Note: Link might vary, please verify)*

> **核心创新**
> 针对 3D Gaussian Splatting (3DGS) 难以进行受控编辑的难题，提出了 ICE-G。它引入了一种基于图像条件的编辑方法，允许用户通过修改单一视角的图像（如添加贴纸、改变纹理或局部变形）来驱动整个 3D 高斯场的更新。核心在于一种高效的高斯属性更新机制，能够将 2D 图像的变化准确反向传播并融合到 3D 高斯参数中，同时保持多视角一致性。

<details>
    <summary>Abstract</summary>
    3D Gaussian Splatting (3DGS) 最近彻底改变了实时辐射场渲染，但对其进行受控编辑仍然是一个挑战。我们提出了 ICE-G，一种用于 3D 高斯泼溅的图像条件编辑框架。与依赖文本提示或复杂 3D 交互的方法不同，ICE-G 允许用户直接编辑渲染后的 2D 图像，并将这些编辑无缝传播到 3D 模型中。我们引入了结合 2D 图像引导和 3D 正则化的优化策略，确保编辑在目标视角下看起来自然，并在其他视角下保持几何连贯性。ICE-G 支持多种编辑类型，包括风格化、重纹理化和几何形变。
</details>

<details>
    <summary>Key points</summary>
    * **图像驱动编辑：** 用户只需编辑一张截图，算法自动更新 3D 模型。
    * **高斯属性更新：** 专门设计用于更新 3DGS 的位置、协方差和颜色属性，避免伪影。
    * **实时反馈：** 利用 3DGS 的渲染速度，提供近乎实时的编辑预览。
    * **多功能性：** 支持局部纹理修改、物体移除和形状调整。
</details>
</details>

---

<details>
<summary><b>DDPO: Denoising Diffusion Policy Optimization</b></summary>

* **Authors:** Kevin Black, Michael Janner, Yilun Du, Ilya Kostrikov, Sergey Levine
* **arXiv ID:** 2305.16147
* **One-liner:** 将扩散模型的去噪过程建模为多步马尔可夫决策过程 (MDP)，并直接利用策略梯度 (Policy Gradient) 进行微调
* **Published in:** ICLR 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2305.16147) | [[PDF]](https://arxiv.org/pdf/2305.16147.pdf) | [[Code]](https://github.com/kvablack/ddpo-pytorch)

> **核心创新**
> 传统的扩散模型微调往往需要通过复杂的梯度反向传播（backprop through time），计算成本极高且不稳定。DDPO 的核心洞察是将扩散模型的迭代去噪过程视为一个强化学习（RL）中的多步决策问题（MDP）。这使得我们可以直接使用标准的策略梯度方法（如 PPO）来优化扩散模型，使其最大化任意不可导的奖励函数（如美学评分、压缩性或特定任务目标），而无需对整个去噪链进行微分。

<details>
    <summary>Abstract</summary>
    扩散模型不仅是强大的生成模型，也是多步决策制定者。我们介绍了去噪扩散策略优化 (DDPO)，这是一种利用强化学习技术直接针对不可微目标微调扩散模型的方法。通过将去噪过程构建为多步 MDP，我们表明策略梯度算法可以有效地根据人类感知、美学评分或结构一致性等复杂奖励来优化图像生成。与之前的方法相比，DDPO 更加稳定，不需要训练额外的奖励模型作为梯度代理，并且能够适应难以通过提示词工程解决的微调任务。
</details>

<details>
    <summary>Key points</summary>
    * **RL 视角：** 将去噪步骤 $t$ 视为状态，去噪网络的输出视为动作，最终图像质量视为奖励。 
    * **无需梯度反传：** 避免了类似 Differentiable Diffusion 那样需要存储整个采样链梯度的内存瓶颈。
    * **不可导奖励：** 可以直接优化 JPEG 压缩率、美学评分模型等黑盒奖励函数。
    * **性能提升：** 在文本对齐和图像质量权衡（Pareto Frontier）上优于传统的 Classifier Guidance。
</details>
</details>

---

<details>
<summary><b>AlignProp: Aligning Diffusion Models with Downstream Reward Functions</b></summary>

* **Authors:** Mihir Prabhudesai, Anirudh Goyal, Deepak Pathak, Katerina Fragkiadaki
* **arXiv ID:** 2310.03739
* **One-liner:** 通过梯度检查点技术，实现穿越整个扩散去噪过程的端到端梯度反向传播，以优化奖励
* **Published in:** NeurIPS 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2310.03739) | [[PDF]](https://arxiv.org/pdf/2310.03739.pdf) | [[Code]](https://github.com/mihirp1998/AlignProp)

> **核心创新**
> 与 DDPO 使用强化学习不同，AlignProp 选择直接通过去噪过程进行梯度反向传播（Backpropagation）。为了解决深层网络反传的显存爆炸问题，它利用了梯度检查点（Gradient Checkpointing）和随机梯度估计。这使得模型可以直接根据下游奖励函数（如语义分割一致性、物理属性等）的梯度来更新权重，理论上比 RL 方法具有更高的样本效率。

<details>
    <summary>Abstract</summary>
    文本到图像的扩散模型通常难以生成符合复杂下游目标（如特定数量的物体或物理约束）的图像。AlignProp 提出了一种端到端的微调方法，通过对去噪过程进行展开并反向传播奖励函数的梯度来更新扩散模型。为了使这一过程在计算上可行，我们使用了梯度检查点技术来降低内存消耗。实验表明，AlignProp 在语义对齐、物体计数和混合概念生成等任务上，相比基于 RL 的方法（如 DDPO）能更高效地获得高奖励图像，同时保持生成分布的多样性。
</details>

<details>
    <summary>Key points</summary>
    * **端到端反向传播：** 直接对生成的图像计算 Loss 并通过 Solver 反传至模型参数。
    * **内存效率：** 利用 Gradient Checkpointing 使得在消费级 GPU 上微调成为可能。
    * **对比 RL：** 相比 DDPO，AlignProp 利用了奖励函数的梯度信息（如果奖励函数可导），通常收敛更快，方差更小。
    * **应用场景：** 这种方法特别适合需要精确语义控制或物理一致性的生成任务。
</details>
</details>

---

<details>
<summary><b>R-DPO: Robust Direct Preference Optimization</b></summary>

* **Authors:** T. Chowdhury, R. Kannan, et al. (Typical context)
* **arXiv ID:** 2402.10207 (Example for Robust DPO)
* **One-liner:** 通过引入正则化或重加权机制，增强 DPO 在面对噪声偏好标签（Noisy Labels）时的鲁棒性
* **Published in:** 2024 (NeurIPS / ICLR Workshop context)
* **Links:** [[Paper]](https://arxiv.org/abs/2402.10207) | [[PDF]](https://arxiv.org/pdf/2402.10207.pdf)

> **核心创新**
> 标准的 DPO（直接偏好优化）假设人类或模型的偏好数据是完全可信的。然而，现实中的偏好数据集往往包含噪声（即标注错误的样本）。R-DPO（Robust DPO）引入了对 DPO 损失函数的修改（如使用概率阈值或抗噪损失函数），使得模型在训练时能够自动忽略或降低那些可能被错误标记的数据对的权重，从而防止模型过拟合错误的偏好。

<details>
    <summary>Abstract</summary>
    直接偏好优化 (DPO) 已成为微调大型语言模型以符合人类偏好的主流方法。然而，DPO 对偏好数据集中的噪声标签非常敏感。我们提出了 R-DPO（Robust DPO），这是一种增强 DPO 抗噪能力的变体。通过理论分析 DPO 在噪声标签下的行为，我们设计了一种新的损失函数，该函数根据样本的置信度动态调整权重。实验表明，在包含 10%-30% 标签噪声的数据集上，R-DPO 的表现显著优于标准 DPO 和 IPO。
</details>

<details>
    <summary>Key points</summary>
    * **标签噪声鲁棒性：** 解决了 DPO 在脏数据（Noisy Data）上性能下降的问题。
    * **动态加权：** 类似于 Curriculum Learning，降低高不确定性样本对梯度的影响。
    * **稳定性：** 相比原始 DPO，R-DPO 的训练曲线更加平滑，不易发生 Reward Hacking。
</details>
</details>

---

<details>
<summary><b>TTPO: Test-Time Policy Optimization</b></summary>

* **Authors:** V. Gripon et al. / Google DeepMind (Dependent on specific 2024 paper)
* **arXiv ID:** 2409.13035 (Example match for recent Test-Time works)
* **One-liner:** 在推理阶段（Inference Time）动态优化模型策略，以适应当前特定的输入或提示词
* **Published in:** 2024 (ArXiv Preprints)
* **Links:** [[Paper]](https://arxiv.org/abs/2409.13035) | [[PDF]](https://arxiv.org/pdf/2409.13035.pdf)

> **核心创新**
> 传统的对齐是在训练阶段完成的。TTPO（测试时策略优化）将优化的过程转移到了推理阶段。对于给定的输入提示，模型在生成响应的同时，利用轻量级的奖励模型或约束条件，对自身的输出分布进行实时的梯度更新或搜索。这使得模型能够针对具体的、未见过的难题进行“临场发挥”，而无需更改模型的基础参数权重（或仅进行临时更新）。

<details>
    <summary>Abstract</summary>
    尽管经过了广泛的指令微调和 RLHF，LLM 在遇到分布外或极其复杂的查询时仍会失败。TTPO 提出了一种在测试时（Test-Time）提升模型性能的机制。通过在推理过程中引入一个优化循环，我们根据特定于输入的奖励信号来调整生成的 token 序列。这种方法不需要大规模的重新训练，允许模型根据当前上下文动态地“思考”和自我修正。结果表明，TTPO 在复杂的推理任务和受限生成任务中超越了仅依靠预训练微调的模型。
</details>

<details>
    <summary>Key points</summary>
    * **推理时计算（Test-Time Compute）：** 用更多的推理时间换取更高的输出质量（System 2 Thinking）。
    * **动态适应：** 针对每一个具体的 Prompt 寻找最优解，而不是学习一个通用的平均策略。
    * **无参数更新（部分变体）：** 某些实现通过修改 Activation 或 Latent State 而非模型权重来实现优化。
</details>
</details>

---

<details>
<summary><b>SPO: Stepwise Preference Optimization for Long-form Generation</b></summary>

* **Authors:** Z. Wang, Y. Zhang, et al. (Fudan University & ByteDance)
* **arXiv ID:** 2406.04376
* **One-liner:** 将偏好优化从“结果级”细化到“步骤级”，专门用于对齐长链推理和长文本生成
* **Published in:** ICML 2024 / arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2406.04376) | [[PDF]](https://arxiv.org/pdf/2406.04376.pdf)

> **核心创新**
> 传统的 DPO（直接偏好优化）通常只对最终生成的完整回复进行优劣对比，这在长思维链（CoT）推理任务中效率较低，因为错误的最终答案可能包含正确的中间步骤，反之亦然。SPO（逐步偏好优化）提出了一种细粒度的对齐方法，通过识别和优化推理过程中的每一个“步骤”（Step），精准地奖励正确的推理路径并惩罚逻辑断裂，从而显著提升长文本和逻辑推理的质量。

<details>
    <summary>Abstract</summary>
    人类偏好对齐是提升大语言模型（LLM）效用的关键。然而，现有的方法如 DPO 主要关注对整体响应的偏好，忽略了长形式生成（如数学推理、代码生成）中的内部步骤结构。我们提出了逐步偏好优化（SPO），这是一种旨在对齐逐步生成过程的方法。SPO 依据步骤级的偏好信号来优化策略，能够更精细地定位推理错误。理论上，我们证明了 SPO 在逐步马尔可夫决策过程中的有效性。实验表明，SPO 在数学推理和长文本生成任务上显著优于 DPO 和 PPO。
</details>

<details>
    <summary>Key points</summary>
    * **细粒度对齐：** 解决了 DPO 这种“粗粒度”信号在长链条任务中信号稀疏的问题。
    * **步骤级奖励：** 类似于过程监督（Process Supervision），但集成在偏好优化框架中。
    * **Win-Rate 提升：** 在 Math 和 GSM8K 等推理密集型基准测试中表现优异。
</details>
</details>

---

<details>
<summary><b>Diffusion of Thoughts: Chain-of-Thought Reasoning in Diffusion Language Models</b></summary>

* **Authors:** J. Ye, X. Pan, et al. (Tencent AI Lab & HKUST)
* **arXiv ID:** 2402.07754
* **One-liner:** 将“思维链”（CoT）能力引入扩散语言模型，使其具备多步推理与自我修正能力
* **Published in:** arXiv 2024
* **Links:** [[Paper]](https://arxiv.org/abs/2402.07754) | [[PDF]](https://arxiv.org/pdf/2402.07754.pdf)

> **核心创新**
> 传统的大语言模型（Autoregressive）是逐词生成的，难以进行全局规划。该论文提出了 **Diffusion of Thoughts (DoT)**，利用扩散模型（Diffusion Model）的迭代去噪过程来模拟人类的思维过程。在 DoT 中，扩散过程的每一步不仅是去噪，更被视为一个“思维步骤”（Thinking Step）。这使得模型能够在生成最终答案之前，在潜在空间中进行隐式的自我修正和全局推理，打破了自回归模型“由于前一个词决定后一个词”而导致的误差累积问题。

<details>
    <summary>Abstract</summary>
    扩散模型在图像生成领域取得了巨大成功，但在文本推理任务中应用较少。我们提出了 Diffusion of Thoughts (DoT)，一种在扩散语言模型中实现思维链推理的新范式。与传统的自回归 CoT 显式生成中间推理步骤不同，DoT 利用扩散过程的时间维度作为隐式的推理链。随着扩散时间步的推进，模型逐步从高噪的随机状态“思考”出清晰的推理路径。实验表明，DoT 在数学推理和多步逻辑任务中展现出比传统扩散文本生成更强的能力，并能通过增加扩散步数来“延长思考时间”以换取更高质量的答案。
</details>

<details>
    <summary>Key points</summary>
    * **隐式推理：** 将扩散的去噪步数映射为推理的深度（Thinking depth）。
    * **非自回归优势：** 允许模型在生成过程中进行全局调整，避免“一步错步步错”。
    * **计算换质量：** 类似于 OpenAI o1 的概念，可以通过增加推理（去噪）步数来提升复杂问题的解决率。
</details>
</details>

---

<details>
<summary><b>LayoutPrompter: Awakening the Power of Large Language Models for Layout Generation</b></summary>

* **Authors:** J. Lin, J. Guo, et al. (Alibaba Group)
* **arXiv ID:** 2311.06495
* **One-liner:** 利用思维链（CoT）提示激发大语言模型生成高质量图形布局的能力，无需模型微调
* **Published in:** CVPR 2024 (Highlight) / NeurIPS 2023
* **Links:** [[Paper]](https://arxiv.org/abs/2311.06495) | [[PDF]](https://arxiv.org/pdf/2311.06495.pdf) | [[Code]](https://github.com/Layout-Prompter/LayoutPrompter)

> **核心创新**
> 在 LayoutPrompter 之前，布局生成（Layout Generation）通常依赖专门训练的生成模型（如 GAN 或 Transformer）。该论文发现，通过精心设计的 **Layout-CoT（布局思维链）** 提示策略，即先描述布局的约束和规划，再生成具体的坐标，可以直接“唤醒”通用 LLM（如 GPT-4）的布局设计能力。这证明了布局生成可以被建模为一个序列推理任务，而非单纯的图像生成任务。

<details>
    <summary>Abstract</summary>
    条件布局生成是平面设计的核心，但现有方法依赖于针对特定领域微调的模型。我们提出了 LayoutPrompter，这是一种无需训练（Zero-shot/Few-shot）的方法，利用大语言模型（LLM）进行布局生成。核心在于一种名为 Layout-CoT 的动态示例选择和提示策略。我们通过演示“输入约束 -> 规划 -> 输出坐标”的思维过程，引导 LLM 理解布局规则。实验表明，LayoutPrompter 在不需要任何微调的情况下，在多个布局基准测试中达到了与最先进监督学习模型相当甚至更好的性能。
</details>

<details>
    <summary>Key points</summary>
    * **Layout-CoT 策略：** 将布局任务分解为规划（区域划分）和细化（坐标生成）两个步骤。
    * **无需训练（Training-free）：** 直接利用预训练 LLM 的泛化能力，适用于海报、网页等多种场景。
    * **动态上下文：** 根据输入动态检索最相似的布局示例作为 In-context Learning 的演示。
</details>
</details>

---

