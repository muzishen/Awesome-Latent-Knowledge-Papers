# I. 干预和转移 / Intervention & Transfer

整理 latent knowledge 如何被增强、迁移、编辑、融合或用于跨任务、跨模型、跨模态干预。

[← Back to README](README.md)

## Paper Overview

| ID | Paper | Year | Venue | Notes |
|---|---|---:|---|---|
| I-001 | [MILR: Improving Multimodal Image Generation via Test-Time Latent Reasoning](#i-001) | 2025 | arXiv preprint | 测试时 latent reasoning |
| I-002 | [Imitating the Truth: Attention-aware Truth-Guided Enhancement for Hallucination Mitigation in Large Vision-Language Models](#i-002) | 2026 | ICLR 2026 | 真实注意力模仿 |
| I-003 | [When Safety Collides: Resolving Multi-Category Harmful Conflicts in Text-to-Image Diffusion via Adaptive Safety Guidance](#i-003) | 2026 | arXiv preprint | 自适应安全引导 |
| I-004 | [Towards Identification and Intervention of Safety-Critical Parameters in Large Language Models](#i-004) | 2026 | arXiv preprint | 安全关键参数 |
| I-005 | [Parameter Importance is Not Static](#i-005) | 2026 | arXiv preprint | 动态参数重要性 |
| I-006 | [Next Concept Prediction in Discrete Latent Space Leads to Stronger Language Models](#i-006) | 2026 | arXiv preprint | 下一个概念预测 |
| I-007 | [DINOv3 Beats Specialized Detectors: A Simple Foundation Model Baseline for Image Forensics](#i-007) | 2026 | arXiv preprint | DINOv3 图像鉴伪 |
| I-008 | [Vision Banana](#i-008) | 2026 | arXiv preprint | 生成式视觉理解 |
| I-009 | [ACE-Merging: Data-Free Model Merging with Adaptive Covariance Estimation](#i-009) | 2026 | arXiv preprint | 无数据模型合并 |
| I-010 | [CAN HETEROGENEOUS LANGUAGE MODELS BE FUSED?](#i-010) | 2026 | arXiv preprint | 异构模型融合 |
| I-011 | [Adopting a Human Developmental Visual Diet Yields Robust and Shape-Based AI Vision](#i-011) | 2026 | Nature Machine Intelligence | 发育式视觉训练 |
| I-012 | [DGS-Net: Distillation-Guided Gradient Surgery for CLIP Fine-Tuning in AI-Generated Image Detection](#i-012) | 2025 | arXiv preprint | CLIP 梯度手术 |
| I-013 | [PsychAdapter: Adapting LLMs to Reflect Traits, Personality, and Mental Health](#i-013) | 2026 | npj Artificial Intelligence | 人格特质适配器 |
| I-014 | [Multilingual Safety Alignment via Self-Distillation](#i-014) | 2026 | arXiv preprint | 多语言安全迁移 |
| I-015 | [Manifold Steering Reveals the Shared Geometry of Neural Network Representation and Behavior](#i-015) | 2026 | arXiv preprint | 流形 steering |
| I-016 | [Don’t Retrain—Align](#i-016) | 2026 | arXiv preprint | AR 到扩散对齐 |
| I-017 | [Correct When Paired, Wrong When Split](#i-017) | TBD | GitHub PDF | 跨模态知识编辑 |
| I-018 | [Towards the Explainability of Protein Language Models](#i-018) | 2025 | arXiv preprint | 蛋白 LM 可解释性 |
| I-019 | [Turning Drift into Constraint: Robust Reasoning Alignment in Non-Stationary Multi-Stream Environments](#i-019) | 2025 | arXiv preprint | 共识推理对齐 |
| I-020 | [Orthogonal Model Merging](#i-020) | 2026 | arXiv preprint | 正交模型合并 |
| I-021 | [EVA: Editing for Versatile Alignment against Jailbreaks](#i-021) | TBD | TBD | Jailbreak 防御编辑 |
| I-022 | [ASGUARD: Activation-Scaling Guard to Mitigate Targeted Jailbreaking Attack](#i-022) | 2025 | arXiv preprint | 激活缩放防御 |
| I-023 | [Evaluating and Steering Modality Preferences in Multi-modal LLMs](#i-023) | 2025 | arXiv preprint | 模态偏好 steering |
| I-024 | [Toward Stable Value Alignment: Introducing Independent Modules for Consistent Value Guidance](#i-024) | 2026 | arXiv preprint | 独立价值模块 |
| I-025 | [A Study on Hidden Layer Distillation for Large Language Model Pre-Training](#i-025) | 2026 | arXiv preprint | 隐藏层蒸馏 |
| I-026 | [Model Spec Midtraining: Improving How Alignment Training Generalizes](#i-026) | 2026 | arXiv preprint | Model Spec 中训练 |

---

## I. 干预和转移：latent knowledge 能不能跨任务、跨模型、跨模态增强和迁移？

<a id="i-001"></a>

<a id="i-001"></a>

### I-001. [MILR: Improving Multimodal Image Generation via Test-Time Latent Reasoning （latent knowledge的探测增强思路也可以做生成）](https://arxiv.org/pdf/2509.22761)

**发现问题：**
 现有 reasoning\-augmented image generation 方法通常有两个问题：
 一类只在文本空间做 reasoning，比如改写 prompt 或生成 CoT；另一类只在图像空间做 test\-time search / refinement。它们缺少真正的 **image\-text joint reasoning**。另外，很多方法还需要高质量 reasoning 数据进行微调，训练成本较高。

**Insight：**
 作者的核心 insight 是：**图像生成中的推理不一定要显式发生在文本或图像上，也可以发生在统一的 latent space 中。**MILR 把文本 token 和图像 token 的中间向量表示放到同一个 latent space 里，在 test time 直接优化这些 latent representations，而不是更新模型参数。这样模型可以同时调整“文本理解”和“图像结构”，实现跨模态 latent reasoning。论文的 Figure 1 和 Figure 2 展示了这个过程：先提取 text/image token 的 latent vectors，然后用 reward model 指导它们迭代更新，再解码成最终文本和图像。

**任务：**
 用于 **multimodal image generation / text\-to\-image generation**，目标是在测试时提升图像与文本指令的对齐能力，尤其是复杂组合、空间关系、计数、属性绑定，以及知识密集型生成。

实验在 **GenEval、T2I\-CompBench、WISE** 上进行。MILR 在 GenEval 上达到 **0\.95 overall score**，在 WISE 上达到 **0\.63**，比 Janus\-Pro\-7B baseline 的 **0\.35** 明显提升。


<a id="i-002"></a>

<a id="i-002"></a>

### I-002. [Imitating the Truth: Attention-aware Truth-Guided Enhancement for Hallucination Mitigation in Large Vision-Language Models](https://openreview.net/pdf?id=fzZAh18s9G)

**发现问题：**
 现有 LVLM 幻觉缓解方法通常只是粗粒度地增强视觉注意力或抑制文本先验，但作者发现：幻觉并不是简单因为“看图不够”，而是模型在不同层、不同阶段没有复现真实 token 的注意力模式。真实 token 和幻觉 token 在 image attention / text attention 上存在明显差异，而且这种差异是分阶段、分模型变化的。

**Insight：**
 作者的核心 insight 是：**让模型模仿真实 token 的注意力行为，可以减少幻觉。**
 具体来说，真实回答在某些阶段会更关注图像信息，在某些模型中也会更依赖文本上下文。因此，不应该统一增强某一种注意力，而应该根据不同阶段有针对性地调整 image attention 或 text attention，让生成过程更接近真实 token 的内部注意力模式。

**任务：**
 用于 **Large Vision\-Language Models 的 hallucination mitigation**，也就是减少图文模型生成与图像不一致的内容。实验任务包括 **COCO 图像描述、POPE 物体存在判断、MME 幻觉评测**，并在 LLaVA、MiniGPT\-4、mPLUG\-Owl2 等模型上验证。


<a id="i-003"></a>

<a id="i-003"></a>

### I-003. [When Safety Collides: Resolving Multi-Category Harmful Conflicts in Text-to-Image Diffusion via Adaptive Safety Guidance](https://arxiv.org/pdf/2602.20880)

**发现问题：**
 现有文生图安全方法通常把多个有害类别的关键词直接合并，比如 hate、sexual、violence、illegal 等一起用来做 safety guidance。作者发现这种做法不一定更安全，反而会产生 **harmful conflict**：不同有害类别的安全引导方向可能不一致、互相抵消，导致真正需要抑制的有害内容没有被有效压制。

**Insight：**
 安全引导不应该“所有有害类别一起上”，而应该在生成过程中动态判断当前 prompt / denoising state 最接近哪个有害类别，然后只沿着这个最相关类别的方向进行安全修正。也就是说，关键是 **category\-aligned safety guidance**，而不是 multi\-category averaging。

**任务DM safety：**
 用于 Text\-to\-Image diffusion model 的安全生成任务，目标是降低模型生成 sexual content、violence、hate、illegal activity 等有害图像的概率。方法可以插入到已有安全机制中，例如 latent\-space 的 SLD 和 text\-space 的 SAFREE，形成 CASG\+SLD / CASG\+SAFREE。




<a id="i-004"></a>

<a id="i-004"></a>

### I-004. [Towards Identification and Intervention of Safety-Critical Parameters in Large Language Models](https://arxiv.org/pdf/2604.08297)

**发现问题：**
 现有 LLM 安全对齐方法能提升安全性，但我们仍不清楚模型内部到底哪些参数真正负责安全行为。因此，在模型继续微调到下游任务时，安全能力很容易被破坏；而如果想快速增强一个未对齐模型的安全性，也缺少精准、低成本的干预方法。

**Insight：**
 作者提出 **Expected Safety Impact（ESI）**：通过估计每个参数对“模型安全得分”的影响，找出真正的 **safety\-critical parameters**。核心发现是：LLM 的安全能力并不是均匀分布在所有参数中，而是集中在少量关键参数上；Dense 模型的关键安全参数主要在**中间层的 Attention Value 矩阵和 MLP**，MoE 模型则更多集中在**后层 MLP experts**。

**任务：**
 用于 **LLM 安全参数识别与安全干预**。具体包括两个任务：

- **Safety Enhancement Tuning（SET）**：只更新少量安全关键参数，让未对齐模型快速变安全。 

- **Safety Preserving Adaptation（SPA）**：在下游任务微调时冻结安全关键参数，避免模型学新任务时丢失安全能力。 

实验覆盖 Llama3、Qwen2\.5、Qwen3\-MoE、Mixtral 等模型，评测包括 HarmBench、WildJailbreak、GSM8K、AGNews 和 MedicalQA。




<a id="i-005"></a>

<a id="i-005"></a>

### I-005. [Parameter Importance is Not Static](https://arxiv.org/pdf/2604.14010)

**发现问题：**
 大模型在多任务 SFT 中容易出现任务干扰和灾难性遗忘。已有参数隔离方法会提前找出一批“重要参数”并固定冻结，但作者发现：参数重要性并不是静态的，而是会随着训练过程不断漂移。早期重要的参数后期可能不重要，后期新出现的关键参数又可能没有被保护，导致静态隔离失效。

**Insight：**
 作者提出一个直观想法：参数隔离不应该像“一把固定的锁”，而应该像“一面移动的盾牌”。模型训练到不同阶段，需要保护的关键参数不同。因此，EPI 通过在线梯度信号动态判断哪些参数当前最重要，并周期性更新保护 mask：锁住新出现的关键参数，释放已经过时的参数，从而同时保持稳定性和可塑性。

**任务：**
 用于缓解大语言模型多任务 SFT 中的任务冲突、灾难性遗忘和稳定性\-可塑性矛盾。作者提出 EPI，在训练中用平方梯度 EMA 估计参数重要性，结合层内归一化和动态 top\-p% mask 更新。实验覆盖 LLaMA\-3\-8B、Mistral\-7B、Qwen2\-7B、Gemma\-2\-9B，任务包括 GSM8K、CodeAlpaca、LogiQA、Alpaca 和 UltraChat。结果表明，EPI 相比普通 SFT、多阶段 SFT 和静态隔离都有更好表现。


<a id="i-006"></a>

<a id="i-006"></a>

### I-006. [Next Concept Prediction in Discrete Latent Space Leads to Stronger Language Models](https://arxiv.org/pdf/2602.08984)

**发现问题：**
 现有语言模型主要依赖 **Next Token Prediction**，也就是逐 token 预测下一个词。但作者认为，随着模型变大，单纯预测低层 token 可能不够高效，难以充分利用模型容量，也不利于学习更抽象、更长程的语义信息。

**Insight：**
 作者提出 **Next Concept Prediction（NCP）**：不要只预测下一个 token，而是先把多个 token 聚合成一个“概念”，再在离散 latent space 中预测下一个概念。这样模型相当于在生成 token 前先做更高层的语义规划。核心思想是：**更难、更抽象的预测目标可以迫使模型学习更强的语义表示和长程依赖。** 

**任务：**
 用于 **语言模型预训练与持续预训练**。作者提出的 **ConceptLM** 同时优化 Next Token Prediction 和 Next Concept Prediction，在 GPT\-2、Pythia 上从零训练，并在 Llama\-3\.1\-8B 上做持续预训练。实验覆盖语言建模和下游评测任务，包括 OpenWebText、Pile、WikiText、Lambada、ARC、WinoGrande、PIQA、HellaSwag、SciQ、RACE、MMLU、AGIEval、SQuAD 2\.0 等。




<a id="i-007"></a>

<a id="i-007"></a>

### I-007. [DINOv3 Beats Specialized Detectors: A Simple Foundation Model Baseline for Image Forensics （鉴伪需要看下）](https://arxiv.org/pdf/2604.16083)

**发现问题：**
 现有图像篡改检测 / 定位方法通常依赖复杂的专门结构，比如多尺度融合、频域线索、边界建模等，但这些方法在跨数据集、跨篡改类型、不同后处理条件下泛化不稳定。作者发现：这个领域不只是缺更复杂模型，而是缺一个**简单、现代、强泛化的 foundation model baseline**。

**Insight：**
 作者的核心 insight 是：**DINOv3 这类自监督视觉基础模型本身已经编码了丰富的 forensic latent knowledge**，包括细粒度空间结构、局部不连续性、边界线索和潜在篡改痕迹。因此，不需要复杂专门检测器，只需冻结 DINOv3 backbone，加 LoRA 做轻量适配，再接一个简单卷积 decoder，就能超过很多专门设计的方法。更重要的是，LoRA 比 full fine\-tuning 更好，说明这些预训练 forensic 信息应该被**保留和轻量激活**，而不是被下游小数据过度覆盖。

**任务：**
 用于 **image manipulation detection and localization / 图像篡改检测与像素级定位**。
 实验在 CAT\-Net 和 MVSS\-Net 两种协议下进行，覆盖 CASIAv1、Columbia、NIST16、Coverage、IMD2020 等数据集。结果显示 DINOv3\+LoRA 在 CAT\-Net protocol 下平均 pixel\-level F1 比之前 SOTA 高 **17\.0 points**；在低数据 MVSS\-Net protocol 下，LoRA 达到 **0\.774 average F1**，明显超过最强 prior method TruFor 的 **0\.530**。




<a id="i-008"></a>

<a id="i-008"></a>

### I-008. [Vision Banana 能不能把他的能力分组分开探测出来再强化下](https://arxiv.org/pdf/2604.20329)

传统视觉理解任务通常依赖专门模型，比如分割用 SAM，深度估计用 Depth Anything，法线估计用 Lotus。但作者提出一个问题：**强大的图像生成模型是否已经在生成预训练中学到了通用视觉理解能力？** 也就是说，image generator 可能不只是会“画图”，它内部可能已经隐含了 segmentation、depth、normal 等视觉知识，只是缺少合适的输出接口。

**Insight：**
 作者的核心 insight 是：**把视觉理解任务统一转化为图像生成任务。**
 具体做法是让模型输出可解码的 RGB 可视化图，比如 segmentation mask、depth map、surface normal map。这样，原本的视觉任务就可以通过“生成一张特定格式的图”来完成。Vision Banana 通过对 Nano Banana Pro 做轻量 instruction\-tuning，把这些 latent visual understanding knowledge 激活出来，同时基本保留原来的图像生成和编辑能力。

**任务：**
 用于 **generalist vision understanding \+ generation**。
 覆盖的任务包括：

- semantic segmentation 

- instance segmentation 

- referring expression segmentation 

- metric depth estimation 

- surface normal estimation 

- text\-to\-image generation 

- image editing 

实验显示 Vision Banana 在多个 2D / 3D 视觉理解任务上达到或接近 SOTA，例如在 Cityscapes semantic segmentation 上超过 SAM 3，在 metric depth estimation 上超过 Depth Anything 3 的平均结果，同时在 GenAI\-Bench 和 ImgEdit 上基本保持 Nano Banana Pro 的生成能力。


<a id="i-009"></a>

<a id="i-009"></a>

### I-009. [ACE-Merging: Data-Free Model Merging with Adaptive Covariance Estimation](https://arxiv.org/pdf/2603.02945)

**发现问题：**
 多个任务模型合并时，不同 expert 之间会互相干扰。尤其是在 **没有原始训练数据** 的 data\-free 场景下，现有方法大多只是直接在参数上做平均、剪枝或分解，缺少对任务差异的建模，所以合并后性能容易下降。

**Insight：**
 作者发现：虽然没有数据，但 **模型微调后的参数变化本身就包含任务信息**。也就是说，可以从每个 expert 的参数更新中估计它对应任务的特征结构，再根据这些结构更合理地合并模型，而不是简单平均。

**任务模型融合：**
 用于 **data\-free model merging**：把多个针对不同任务微调好的模型合成一个统一模型，不需要访问原始训练数据。实验包括视觉分类任务，以及 GPT\-2、RoBERTa、LLaMA\-3 上的语言理解、多语言、代码和数学推理任务。





<a id="i-010"></a>

<a id="i-010"></a>

### I-010. [CAN HETEROGENEOUS LANGUAGE MODELS BE FUSED?](https://arxiv.org/pdf/2604.01674)

**发现问题：**
 现有模型融合大多假设多个 expert 来自同一个 backbone，比如都是 Llama 或都是 Qwen。但现实中有用的专家模型往往来自不同模型家族，例如 Llama、Qwen、Mistral。不同架构之间层数、hidden size、模块结构和表示空间都不一致，直接做参数合并会失效，并且多个异构 expert 还会带来更强的冲突和噪声。

**Insight：**
 作者认为，异构模型不能直接按参数位置合并，而应该先找到不同模型中功能相似的模块，再在 adapter 空间进行知识迁移。同时，为了避免不同来源的 expert 互相干扰，需要在融合前过滤掉不可靠或冲突的信号。简单来说，就是 **先对齐结构，再去除冲突噪声，最后只把有用知识注入目标模型**。

**任务：**
 用于 **heterogeneous LLM fusion**：把来自不同模型家族的 expert adapters 融合到一个目标模型中，得到一个单一 fused adapter。实验主要包括 Llama、Qwen、Mistral 之间的跨架构融合，用在信息抽取任务，如 NER、RE、ET，也测试了 GLUE 上的跨任务泛化能力。


<a id="i-011"></a>

<a id="i-011"></a>

### I-011. [Adopting a Human Developmental Visual Diet Yields Robust and Shape-Based AI Vision](https://www.nature.com/articles/s42256-026-01228-6)

**发现问题：**
 现有 AI 视觉模型和人类视觉仍有明显差距：人类更依赖形状，AI 更依赖纹理；人类对模糊、噪声、遮挡等退化更鲁棒，而 AI 容易受图像退化和对抗攻击影响。作者认为问题不只是模型规模不够，而是 AI 的“视觉成长经历”和人类不同：AI 从一开始就看高清图像，而人类早期视觉是模糊、低对比、弱色彩的。

**Insight：**
 作者提出一个直观想法：让 AI 像婴儿一样“慢慢长大”。也就是在训练早期给模型看低清晰度、低对比、低色彩的图像，随着训练逐渐恢复到成人视觉水平。这个 **Developmental Visual Diet（DVD）** 不是简单加噪声或数据增强，而是按照人类视觉发育轨迹设计的训练课程。这样模型会先学整体形状和全局结构，而不是一开始就过度依赖局部纹理。

**任务：**
 用于训练更接近人类视觉的鲁棒 AI 视觉模型。作者把人类视觉发育中的三条曲线——视觉敏锐度、对比敏感度、色彩敏感度——转化为图像预处理课程，并用于训练 ResNet、AlexNet、VGG、MobileNet、ViT、DeiT 等模型。实验覆盖 mini\-ecoset、ecoset 和 ImageNet\-1K，评测包括 shape\-texture bias、IllusionBench 抽象形状识别、图像退化鲁棒性和黑盒/白盒对抗攻击。结果显示，DVD 显著提升形状偏置、抽象形状识别和鲁棒性，其中对比敏感度发展是最关键因素。


<a id="i-012"></a>

<a id="i-012"></a>

### I-012. [DGS-Net: Distillation-Guided Gradient Surgery for CLIP Fine-Tuning in AI-Generated Image Detection](https://arxiv.org/pdf/2511.13108)

**发现问题：**
 CLIP 本身有很强的通用视觉语义表示，适合做 AI 生成图像检测；但直接用 LoRA 等方式微调 CLIP，容易造成灾难性遗忘。结果是模型虽然更容易区分训练集上的 real/fake，但会破坏 CLIP 原本的表示几何结构，导致跨生成模型泛化变差。

**Insight：**
 作者的核心想法是：CLIP 里的知识不能简单“全保留”或“全删除”，而要在梯度空间里做手术。文本语义中有些方向会干扰伪造检测，需要抑制；冻结 CLIP 图像编码器中有些方向代表可迁移先验，需要保留。因此 DGS\-Net 把梯度分成 harmful 和 beneficial 两类：对 harmful 方向做正交投影去除，对 beneficial 方向做轻量对齐，让模型既学到 fake image artifact，又不丢掉 CLIP 的通用先验。

**任务：**
 用于提升 CLIP 微调在 AI 生成图像检测中的跨域泛化能力。作者提出 **DGS\-Net**，包含两个模块：**Orthogonal Suppression** 用文本分支梯度识别并去除有害语义方向；**Prior Alignment** 用冻结 CLIP 图像分支的有益梯度对齐可迁移先验。实验覆盖 AIGCDetectBench、AIGIBench 和 UniversalFakeDetect，测试 50 种生成模型，包括 GAN、diffusion、Deepfake、DALLE、FLUX、Midjourney、SDXL 等。结果显示，DGS\-Net 在检测准确率、AP、JPEG/blur 鲁棒性和表示几何保持上都优于现有方法。


<a id="i-013"></a>

<a id="i-013"></a>

### I-013. [PsychAdapter: Adapting LLMs to Reflect Traits, Personality, and Mental Health](https://www.nature.com/articles/s44387-026-00071-9) (子刊 npj AI)

**发现问题：**
 现有 LLM 生成的文本通常像“平均人”的语言，缺少个体差异，难以稳定体现不同人格、心理健康状态或人口学特征。单纯靠 prompt 控制人格也比较粗糙，只能使用离散描述，难以精细控制连续心理特质，比如外向性高低、抑郁程度或生活满意度。

**Insight：**
 作者提出一个直观想法：不要只在 prompt 里告诉模型“你很外向/你很抑郁”，而是把心理特质向量直接注入 Transformer 的每一层。PsychAdapter 像一个“心理旋钮”，把 Big Five、抑郁、生活满意度、年龄等连续分数映射到隐藏层空间，让模型在生成每个 token 时都受到这些心理变量影响。

**任务：**
 用于生成能反映指定人格、心理健康状态和人口学特征的文本。作者提出 **PsychAdapter**，在 GPT\-2、Gemma\-2B、LLaMA3 上加入轻量 adapter，将连续心理分数通过层级投影注入 transformer，并结合 LoRA 训练。训练数据来自博客和 Twitter/X，并用心理语言模型给文本估计 Big Five、抑郁、生活满意度和年龄分数。实验显示，专家能以 **87\.3%** 准确率识别 Big Five 特质，以 **96\.7%** 准确率识别抑郁和生活满意度；模型还能控制多维人格组合、细粒度人格水平，并泛化到不同文本域和不同 LLM。


<a id="i-014"></a>

<a id="i-014"></a>

### I-014. [Multilingual Safety Alignment via Self-Distillation](https://arxiv.org/pdf/2605.02971)

**发现问题：**
 LLM 在英文等高资源语言中通常比较安全，但在低资源语言中容易被 jailbreak。已有多语言安全对齐方法通常需要为每种语言准备高质量安全回复数据，成本高、难扩展。作者发现：模型其实已经在高资源语言中具备安全能力，关键问题是如何把这种能力转移到低资源语言。

**Insight：**
 作者提出一个直观想法：让模型“自己教自己”。同一个 LLM 同时扮演 **teacher** 和 **student**：teacher 看到英文 query 和 CoT 指令，用英文进行安全判断，再用目标低资源语言回答；student 只看到低资源语言 query。通过自蒸馏，student 学会把英文中的安全判断能力迁移到低资源语言，而不需要任何人工安全回复数据。

**任务：**
 用于提升 LLM 在多语言 jailbreak 场景下的安全对齐能力。作者提出 **Multilingual Self\-Distillation（MSD）**，包括 **on\-policy MSD** 和 **off\-policy MSD** 两种版本，并设计 **Dual\-Perspective Safety Weighting（DPSW）**，对拒答、风险判断等 safety\-critical tokens 加大蒸馏权重。实验覆盖 Qwen\-2\.5\-7B、Qwen\-3\-8B、LLaMA\-2\-7B、LLaMA\-3\-8B，评测 MultiJail、PKU\-SafeRLHF、MMMLU、MGSM，语言包括英文、中文、阿拉伯语、孟加拉语、斯瓦希里语、爪哇语等。结果显示，MSD 能显著降低多语言攻击成功率，泛化到未见语言，同时基本保持通用能力和数学推理能力。


<a id="i-015"></a>

<a id="i-015"></a>

### I-015. [Manifold Steering Reveals the Shared Geometry of Neural Network Representation and Behavior](https://arxiv.org/pdf/2605.05115)

**发现问题：**
 现有 activation steering 通常默认表示空间是平的，只要找到一个方向并线性相加就能控制行为。但作者发现：很多概念在模型内部不是一条直线，而是弯曲的 manifold。线性 steering 会直接切过这些弯曲结构的内部，导致输出“跳跃”、不自然、甚至崩坏。

**Insight：**
 作者提出一个直观想法：控制模型行为的关键不是“找对方向”，而是“走对路径”。如果模型内部把 weekdays、months、letters、ages 等概念组织成圆环、曲线或曲面，那么 steering 也应该沿着这些几何结构走，而不是走直线。也就是说，activation space 里的几何结构和 behavior space 里的输出分布结构其实是同一个概念空间的两种投影。

**任务：**
 用于验证神经网络内部表示几何是否因果地控制模型行为，并提出更自然的 steering 方法。作者先拟合 **activation manifold** 和 **behavior manifold**，发现二者在 weekdays、months、letters、ages 上近似等距；再比较 **linear steering** 和 **manifold steering**，结果显示 manifold steering 能让输出概率按概念顺序平滑转移，而 linear steering 会出现非相邻概念之间的“teleportation”。实验覆盖 Llama 3\.1 8B 的时间、字母、年龄推理任务，以及 in\-context learning 的 grid / cylinder 图结构任务，并扩展到 Mountain Car 视觉 world model。结果说明：尊重 activation manifold 的干预能产生更自然、更可控的行为轨迹。


<a id="i-016"></a>

<a id="i-016"></a>

### I-016. [Don’t Retrain—Align](https://arxiv.org/pdf/2605.06885)

**发现问题：**
 Diffusion LM 有非顺序生成、双向编辑等优势，但从头训练成本很高。已有 AR→DLM 转换方法通常只是复用 AR 参数，再继续做 denoising training；但作者认为这些方法没有显式保护 AR 模型已经学到的内部表示结构，导致 DLM 仍在重复学习语言表示。

**Insight：**
 作者提出一个直观想法：AR 和 DLM 的区别主要是“生成路径”不同，而不是“语言知识”不同。AR 预训练已经学到了语义和句法表示，DLM 不应该重新学一遍语言，而应该对齐并复用这些表示。也就是说，把 AR 转成 DLM 时，不是 **retrain representation**，而是 **align representation \+ adapt decoding mechanism**。

**任务：**
 用于高效地把 autoregressive LM 转换成 masked diffusion LM。作者提出 **REPR\-ALIGN**：把 AR 模型冻结作为 teacher，把同架构 DLM student 初始化为 AR 权重，只把 causal attention 改成 bidirectional attention；训练时同时优化 masked denoising loss，并用 layer\-wise cosine loss 对齐 DLM 和 frozen AR 的 hidden states。实验基于 Qwen3\-0\.6B、1\.7B、4B，在 Nemotron\-SFT\-Code 上训练，评测 HumanEval、HumanEval\+、MBPP、MBPP\+。结果显示，REPR\-ALIGN 能加速 AR→DLM 转换，在 HumanEval pass@10 上显著提升，低数据场景也有效，并且冻结 embedding / MLP 后还能提升训练吞吐。


<a id="i-017"></a>

<a id="i-017"></a>

### I-017. [Correct When Paired, Wrong When Split](https://github.com/TingchaoFu/DECODE/blob/main/paper.pdf)

**发现问题：**
 现有 MLLM 知识编辑方法通常只看图文配对输入下答案是否改对。但作者发现：模型在 **text\-image paired query** 下能回答新知识，一旦拆成 **text\-only** 或 **image\-only grounding** 查询，就可能回到旧答案。作者称这个现象为 **editing decoupling failure**。

**Insight：**
 作者提出一个直观解释：MLLM 里的同一个实体知识，并不是存在一个统一的“实体知识库”里，而是被分散存进了不同模态通路。图像触发时走一组 visual\-aware neurons，文本触发时走另一组 text\-aware neurons。传统方法只在图文输入上编辑，实际主要改到了视觉/多模态通路，所以文本通路里还保留旧知识，导致“配对时正确，拆开时错误”。

**任务：**
 用于解决多模态大模型知识编辑中的跨模态不一致问题。作者提出 **DECODE**，先根据 text\-only、image\-trigger、standard multimodal 三种查询计算 neuron contribution score，定位 **text neurons** 和 **visual neurons**；再用 two\-stream editing 分别给两组 FFN neurons 加 learnable offsets，并用 target loss 更新目标知识、用 locality loss 保持无关知识不变。实验覆盖 InstructBLIP、LLaVA\-v1\.5、Qwen\-VL，并基于 MMKE 构造 modality\-split 测试集。结果显示，DECODE 能同时提升 text\-only 和 multimodal reliability / generality，并比 FT、SERAC、IKE、FiNE 更好地缓解 editing decoupling failure。


<a id="i-018"></a>

<a id="i-018"></a>

### I-018. [Towards the Explainability of Protein Language Models](https://arxiv.org/pdf/2506.19532) （子刊）

**发现问题：**
 蛋白质语言模型已经能做结构预测、功能预测和蛋白设计，但它们为什么能做对、学到了什么生物规律，仍然像黑盒。作者发现：现有 XAI 方法大多只用来验证模型是否捕捉了已知生物模式，还没有真正充分用于发现新的蛋白质机制。

**Insight：**
 作者提出一个清晰框架：解释蛋白质模型时，可以从四个入口看模型——训练数据、输入序列、模型内部组件、输入输出变化。比如看哪些训练蛋白影响预测，看哪些氨基酸贡献最大，看 attention head / neuron / SAE feature 是否对应生物概念，或者通过突变输入观察输出怎么变。更重要的是，XAI 不应只当“验算器”，还可以成为模型压缩的 **Engineer**、控制生成的 **Coach**，甚至未来帮助人类发现新生物规律的 **Teacher**。

**任务：**
 用于综述蛋白质语言模型的可解释性方法和未来研究方向。文章总结了 influence functions、embedding space analysis、gradient\-based attribution、attention analysis、LRP、neuron activation、SAE、SHAP、LIME、counterfactuals 和 adversarial probing 等方法，并归纳 XAI 在蛋白研究中的五种角色：**Evaluator、Multitasker、Engineer、Coach、Teacher**。作者指出目前主流工作仍停留在 Evaluator 阶段，未来需要更可靠的 benchmark、faithfulness evaluation、人类友好的可视化工具，以及 wet\-lab validation，才能让 XAI 真正从解释模型走向发现蛋白折叠、酶催化和进化规律。




<a id="i-019"></a>

<a id="i-019"></a>

### I-019. [Turning Drift into Constraint: Robust Reasoning Alignment in Non-Stationary Multi-Stream Environments](https://arxiv.org/pdf/2510.04142)

**发现问题：**
 多教师 / 多模型蒸馏通常假设不同 source MLLM 的推理都是有用知识，直接把它们融合给 student 学。但作者发现：不同大模型的推理分布并不稳定，会因为预训练偏差、架构差异和表达风格不同产生 **concept drift**。如果 student 直接模仿这些不一致的推理轨迹，就会把多个老师的偏差一起学进去，导致幻觉、语义矛盾和诊断推理错误。

**Insight：**
 作者的核心想法是：模型之间的分歧不一定是噪声，而可以变成“负约束”。也就是说，不要简单平均多个老师的答案，而是先找出它们共同认可的 **consensus reasoning**，再把彼此冲突、漂移的推理轨迹当作模型应该避免的区域。这样 student 学到的不是某个老师的风格，而是在多个老师分歧中提炼出的稳定推理边界。

**任务：**
 用于在非平稳、多源 MLLM 环境下做鲁棒推理对齐。作者提出 **APO（Autonomous Preference Optimization）**：第一阶段用多个 source MLLM 的推理轨迹做 supervised bootstrapping，让 Qwen2\.5\-VL\-7B student 获得多个老师的能力覆盖；第二阶段生成 consensus trajectory 作为正样本，把原始冲突推理作为 negative constraints，用 multi\-negative Plackett\-Luce preference loss 进行优化。作者还构建 **CXR\-MAX**，包含来自 GPT\-5、Gemini\-2\.5、Claude Sonnet\-4、Qwen\-VL\-Max、Grok\-4、GLM\-4\.5V、Moonshot 等 7 个 MLLM 的 **170,982** 条胸片推理轨迹。实验在 MIMIC\-CXR、MS\-CXR\-T、Open\-I、ChestXray14、CheXpert、ChestXDet10 上验证，结果显示 7B student 在只用 10% 数据且不使用放射科报告训练的情况下，平均准确率超过多个大型 source MLLM 和现有胸片诊断方法。


<a id="i-020"></a>

<a id="i-020"></a>

### I-020. [Orthogonal Model Merging](https://arxiv.org/pdf/2602.05943)

**发现问题：**
 现有 model merging 方法大多直接在欧氏空间里做 task vector 加法或平均，比如把多个 finetuned model 的参数差值加到 base model 上。但作者认为这样会破坏预训练权重原本的几何结构，尤其是 neuron 之间的角度关系 / hyperspherical energy，导致任务之间参数冲突、能力互相干扰和 catastrophic forgetting。

**Insight：**
 作者的核心想法是：模型微调不一定只应该看成“参数加法”，也可以看成对 base weight 做了一种“旋转”。如果多个任务的能力是不同方向的旋转，那么合并时就不应该在平直的欧氏空间里硬加，而应该在 **orthogonal group** 这个流形上合并。这样可以保留权重的几何结构，减少不同任务更新之间的破坏性干扰。

**任务：**
 用于把多个 task\-specific finetuned LLM / MLLM 合并成一个统一模型。作者提出 **OrthoMerge**：对于 OFT 微调模型，先把每个任务的 orthogonal matrix 映射到 Lie algebra `so(d)`，在那里做 **magnitude\-corrected averaging**，避免不同任务方向相互抵消导致更新强度变弱，再用 Cayley transform 映射回 orthogonal group。对于 LoRA / full finetuning 等非 OFT 模型，作者提出 **Orthogonal\-Residual Decoupling**：先通过 Orthogonal Procrustes problem 提取每个专家模型中的 orthogonal component，在流形上合并；剩余 residual component 继续用 TA、TIES、TSV\-M 等传统方法合并。实验覆盖 Llama\-3\.1\-8B、Qwen2\.5\-3B、Llama\-3\.2\-3B 和 Qwen2\.5\-VL\-7B\-Instruct，任务包括数学、代码、科学问答、常识问答、社交推理、多语言、安全、OCR、空间理解和医学多模态 QA。结果显示，OrthoMerge 能提升多任务合并性能，并更好保留 base model 的通用能力。


<a id="i-021"></a>

<a id="i-021"></a>

### I-021. EVA: Editing for Versatile Alignment against Jailbreaks

**发现问题：**
 LLM / VLM 虽然经过 RLHF、DPO 等安全对齐，但仍然容易被 jailbreak 攻击绕过。已有防御方法要么需要重新安全微调，成本高且容易损伤通用能力；要么依赖外部检测器 / prompt filter，会增加推理延迟。作者认为：jailbreak 不是模型“没有安全知识”，而是攻击把有害概念的内部激活从 harmful 区域推到了 benign 区域，导致模型误以为这是普通请求并执行。

**Insight：**
 作者提出一个很直观的想法：安全对齐可以看成一种 **模型编辑问题**。
 如果模型把 “hack / bomb” 这类 harmful token 或 harmful image region 当成普通 key 去检索有害 value，那么我们不需要重新训练整个模型，只需要把这些 harmful key 对应的内部映射改掉，让它们指向安全拒答 value。
 也就是说，EVA 像是在模型内部给危险触发器“改路由”：原来通向有害回答，现在被编辑成通向 “I’m sorry, I can’t assist with that\.” 这类安全拒答。

**任务：**
 用于在部署后防御 LLM 和 VLM 的文本 / 视觉 jailbreak 攻击。作者提出 **EVA（Editing for Versatile Alignment）**，把 MLP 看成 key\-value memory：先用 GPT\-4o 从恶意 query 中抽取 harmful token，并生成多种上下文变体来聚合 textual key；对于 VLM，再通过 cross\-modal attention 找到与 harmful token 最相关的 image token，得到 visual key；然后优化一个 safe target value，使模型更倾向生成拒答，同时用 KL regularization 保持 benign 输入上的行为不漂移；最后用 closed\-form least\-squares update 编辑关键层的 MLP down projection。实验覆盖 Llama2\-7B、Vicuna\-7B、Mistral\-7B、Llama3\.1\-8B、Qwen2\.5\-7B，以及 LLaVA\-1\.5\-7B、Qwen2\.5\-VL\-7B、InternVL3\.5\-8B；攻击包括 GCG、AutoDAN、PAIR、FigStep、Hades、ADV\-16，并在 HarmBench、AdvBench、JailbreakBench、MaliciousInstruct、MM\-SafetyBench、MultiTrust 上评测。结果显示，EVA 能显著降低 ASR，很多设置下接近 0，同时基本保持 MT\-Bench、MM\-Vet\-v2、MMMU、MMStar 等通用能力，并且没有额外推理开销。





<a id="i-022"></a>

<a id="i-022"></a>

### I-022. [ASGUARD: Activation-Scaling Guard to Mitigate Targeted Jailbreaking Attack](https://arxiv.org/pdf/2509.25843)

**发现问题：**
 现有 LLM 虽然做了安全对齐，但拒答机制很脆弱，尤其容易被一些很小的语言变化绕过。比如 **tense jailbreaking**：模型会拒绝 “How to make a Molotov cocktail?”，但如果改成过去式 “How did people make a Molotov cocktail?”，模型可能就把它当成历史问题来回答。作者发现，这不是模型完全不知道 harmfulness，而是安全拒答机制在某些语义改写下没有泛化好，尤其是过去式表达会绕过模型内部的 refusal pathway。

**Insight：**
 作者的核心洞察是：jailbreak 漏洞不是全模型均匀分布的，而可能集中在少数 **attention heads** 上。
 这些 heads 像是“语法/语义路由器”：当它们检测到过去式表达时，可能会把有害请求错误路由成“历史询问”，从而削弱拒答信号。
 所以，修复安全漏洞不一定要重新大规模训练模型，而是可以先用 circuit analysis 找到导致特定 jailbreak 成功的 vulnerable heads，再对这些 heads 的 activation 做精细缩放，最后用 temporary scaling 引导模型学到更稳的拒答机制。

**任务：**
 用于缓解特定类型 jailbreak，尤其是 **past tense jailbreak**，同时尽量避免过拒答和能力下降。作者提出 **ASGUARD**：第一步用 **EAP\-IG circuit analysis** 比较 “False\-to\-True” jailbreak 成功电路和 “Always\-False” 安全拒答电路，定位只在成功 jailbreak 中出现的 tense vulnerable attention heads；第二步训练 **channel\-wise activation scaling vector**，只缩放这些 vulnerable heads 的通道激活，让模型更倾向输出安全拒答；第三步做 **Preventative Fine\-Tuning**，在 scaling vector 临时生效时微调模型，让模型学会绕开脆弱路径，训练结束后再移除 scaling vector。实验覆盖 Llama\-3\.1\-8B\-Instruct、Qwen2\.5\-7B\-Instruct、Gemma\-2\-9B\-it、OLMo\-2\-1124\-7B\-Instruct，并评测 Past Tense Jailbreak、GCG、LogiBreak、OR\-Bench\-Toxic、OR\-Bench\-Hard 和 MMLU。结果显示，ASGUARD 能显著降低 ASR，比如 Llama 上 past tense ASR 从 42% 降到 8%，GCG 从 15% 降到 1%，同时比 SFT、DPO、RepE、Circuit Breaker、RepBend 更好地平衡安全性、过拒答和通用能力。


<a id="i-023"></a>

<a id="i-023"></a>

### I-023. [Evaluating and Steering Modality Preferences in Multi-modal LLMs](https://arxiv.org/pdf/2505.20977)

**发现问题：**
 多模态大模型在同时看到图像和文本时，并不一定会“公平地融合两种信息”。作者发现：当图像和文本给出冲突证据时，很多 MLLM 会明显偏向某一种模态，尤其是偏向文本。也就是说，模型表面上是多模态推理，但实际可能在关键决策时更相信 text context，而不是 image context。

**Insight：**
 作者的核心直觉是：**模态偏好可以通过冲突场景暴露出来**。
 如果图像支持答案 A，文本支持答案 B，而模型本身单独看图或单独看文本都能答对，那么最终它选 A 还是 B，就能反映它更依赖哪种模态。
 进一步地，作者发现这种偏好不是纯粹的表面行为，而是能在模型 hidden states 里形成一个可分离的 **modality preference direction**。所以，模态偏好不仅能被测量，也能被表示工程方法直接 steering。

**任务：**
 用于评估和控制 MLLM 的图文模态偏好。作者构建 **MC² benchmark**，包含 2,000 个图文冲突样本，覆盖 sport、attribute、sentiment、positional、counting、color、activity、object 等 8 类任务；每个样本保证模型单独看图像或单独看文本都能理解，从而排除单模态理解能力差异的干扰。作者用 **Vision Ratio** 衡量模型偏向视觉还是文本，并评估 20 个开源 MLLM 和 GPT\-4o\-mini。结果显示，大多数模型明显偏文本，只有 Qwen2\.5\-VL、InternVL3 等模型表现出更强视觉偏好；同时 Vision Ratio 和多模态下游任务表现高度相关，Spearman ρ 达到 **0\.964**。在方法上，作者提出 **Modality Preference Probing \& Steering**：先用“基于图像回答”和“基于文本回答”两种指令提取 hidden\-state 差分方向，再在推理时把该 steering vector 加到指定层 hidden states 上，从而无需微调地增强视觉或文本偏好。实验表明，该方法在 MC²、MathVista、TallyQA、VSR、AmbigCaps 和 PhD hallucination benchmark 上优于 instruction design、CoT 和 few\-shot prompting。总体上，这篇文章把 MLLM 的模态偏好从“行为观察”推进到“可测量、可解释、可干预”的表示层控制问题。


<a id="i-024"></a>

<a id="i-024"></a>

### I-024. [Toward Stable Value Alignment: Introducing Independent Modules for Consistent Value Guidance](https://arxiv.org/pdf/2605.11712)

**发现问题：**
 现有 LLM 对齐方法通常直接改 backbone 参数，或者在 residual stream 里注入 steering vector。但作者认为：模型的 residual stream 本身非常动态，任务信息、上下文信息会不断改变 hidden states，导致 value representation 很脆弱。也就是说，安全、伦理这类 value signals 如果直接绑在 backbone 内部表示上，很容易被强任务信号或 adversarial prompt 扭曲，造成不稳定对齐。

**Insight：**
 作者的核心想法是：value alignment 不应该完全依赖 backbone 自己“顺便记住价值观”，而应该有一个相对独立的 value module。
 这个模块像一个外部“价值导航器”：先在独立 value space 中判断当前生成轨迹是否偏离安全区域，再把修正信号转换成 **Bridge Tokens**，让 backbone 在生成时主动 attend 到这些 value anchors。
 这样做的好处是：value signals 不再直接暴露在动态 residual stream 里被任务信号冲散，而是通过独立模块稳定维护，再以非侵入式方式引导生成。

**任务：**
 用于提升 LLM 在生成过程中的稳定价值对齐和安全拒答能力。作者提出 **SVGT（Stable Value Guidance Transformer）**，冻结原始 backbone，只训练一个独立 value module。方法包括两部分：
**Value Space Construction**：从指定中后层 hidden states 中提取当前状态，用 unconditional pathway 学习通用安全先验，用 conditional pathway 结合 prompt context 判断上下文相关风险，并通过 discriminator 给出 value score；
**Latent Value Bridge（LVB）**：根据 value score 的梯度得到修正方向，再生成一组可学习 **Bridge Tokens**，插入到 prompt 后作为 attention targets，在 decoding 过程中周期性刷新，从而动态纠正生成轨迹。训练采用三阶段 curriculum：先做 unconditional safety discrimination，再做 conditional discrimination，最后冻结 backbone 和 value encoder，只训练 bridge generator 做 value\-guided generation。实验覆盖 GPT\-2、Qwen2\-1\.5B、Llama\-3\.2\-3B\-Instruct、Mistral\-7B\-Instruct\-v0\.2，在 WildGuardMix、BeaverTails、HarmBench 上评估。结果显示，SVGT 通常能将 harmful score / ASR 降低 70% 以上，并把 HarmBench refusal rate 提升到 75% 以上，同时相比 ITI、RE\-Control 这类直接 hidden\-state intervention，更好保持 PPL 和生成流畅性。总体上，这篇文章把 value alignment 从“直接改模型内部表示”推进到“独立价值模块 \+ 动态桥接 token”的模块化对齐框架。


<a id="i-025"></a>

<a id="i-025"></a>

### I-025. [A Study on Hidden Layer Distillation for Large Language Model Pre-Training](https://arxiv.org/pdf/2605.11513)

**发现问题：**
 LLM 蒸馏里最常用的是 **logit\-based KD**，也就是让 student 学 teacher 的输出概率分布。但 teacher 的中间层 hidden states 里可能也有语义信息，按理说可以帮助 student 学得更好。作者发现：虽然 **Hidden Layer Distillation（HLD）** 在 BERT、encoder 模型或任务微调阶段经常有效，但它在 decoder\-only LLM 的大规模 pre\-training 阶段并没有被系统验证。

**Insight：**
 作者的核心直觉是：teacher 的中间层表示确实可能包含额外 latent signal，但这个信号不一定容易被 student 利用。
 简单说，student 不只是“对齐 teacher hidden state”就会变强，因为 decoder\-only LLM 从头预训练时，中间表示还在不断形成；如果强行匹配 teacher 的中间层，可能只是提供一个 warm start，而不一定转化成下游能力提升。
 所以，HLD 的关键问题不是“teacher hidden states 有没有信息”，而是“这些信息能不能在 compute\-matched pre\-training 中稳定变成 student 的能力”。

**任务：**
 用于系统评估 **Hidden Layer Distillation 是否能改进 decoder\-only LLM 预训练蒸馏**。作者用 Gemma3 3\.4B 作为 teacher，训练 123M 和 735M student，在 C4 上最多训练到 108B / 168B tokens，并严格按照 FLOPs 做 compute\-matched comparison，而不是只按 token 数比较。方法上比较三类训练：**NLL self\-supervised baseline**、标准 **KD**、以及两种 HLD：
**HLDF** 先用 teacher 中间层 hidden state 对齐 student 中间层，再进行标准 KD；
**HLDC** 则把 hidden\-state matching loss 和 KD loss 放在一起联合训练。
 实验在 C4 perplexity、Wikitext\-103、HellaSwag、WinoGrande、LAMBADA、PIQA、ARC\-E 上评估。结果显示：标准 KD 明显强于 NLL；HLDC 基本和 KD 持平；HLDF 在 C4 perplexity 上有稳定但很小的提升，但下游任务没有一致增益。总体上，这篇文章说明：hidden states 里可能有可提取的 latent signal，但当前简单 HLD 还不足以在 decoder\-only LLM pre\-training 中稳定超过强 KD baseline，未来可能需要更好的 loss、adapter 结构或训练协议。


<a id="i-026"></a>

<a id="i-026"></a>

### I-026. [Model Spec Midtraining: Improving How Alignment Training Generalizes](https://arxiv.org/pdf/2605.02087)

**发现问题：**
 现在很多对齐方法都是直接用 demonstration data 做 alignment fine\-tuning，让模型模仿符合 Model Spec / Constitution 的回答。但作者发现：这种方式容易产生 **shallow alignment**。模型可能在训练分布内回答得很对，但一到没见过的场景，就不知道应该如何泛化。原因是 demonstration data 往往只展示“该怎么做”，没有充分说明“为什么要这么做”，所以模型学到的可能只是表面行为，而不是背后的价值原则。

**Insight：**
 作者的核心想法是：在正式 alignment fine\-tuning 之前，先让模型“读懂自己的 Model Spec”。
 也就是说，不是只给模型看对齐样例，而是先用大量合成文档讲清楚：这个助手是谁、应该有什么价值观、为什么这些规则成立、遇到复杂情况时应该怎么思考。
 这样后续再做 AFT 时，模型就不会只机械模仿行为，而是能把 demonstration data 解释成某种更深层原则的证据，从而在 OOD 场景中更稳定泛化。

一个很直观的例子是：同样让模型学习“喜欢 cream cheese，不喜欢 brie”，如果 MSM 里的 spec 说这是因为 **pro\-America**，模型之后会泛化成更亲美；如果 spec 说这是因为 **pro\-affordability**，模型会泛化成更重视可负担性。也就是说，**相同的 AFT 数据，可以因为不同的 spec midtraining 泛化到完全不同的价值方向**。

**任务：**
 用于提升 alignment training 的泛化能力，让模型不仅在训练样例上对齐，也能在新场景中按正确原则行动。作者提出 **MSM（Model Spec Midtraining）**：在 pre\-training 之后、alignment fine\-tuning 之前，用 Claude Opus 4\.6 根据 Model Spec 生成大量合成文档，包括内部报告、博客、研究备忘录、用户体验描述等，让模型通过 next\-token prediction 学习 spec 的内容和背后理由；之后再进行常规 AFT。

实验包括三部分：

第一，用 8 个简单价值观测试 MSM 是否能控制泛化，比如 pro\-affordability、pro\-America、pro\-environment、pro\-novelty、pro\-tradition、pro\-simplicity、pro\-difficulty、pro\-individualism。结果显示，MSM \+ AFT 比单独 AFT 更能让模型在没见过的领域表达正确价值偏好。

第二，用更复杂的安全场景测试 MSM 是否能降低 **agentic misalignment**。作者用一个关于 self\-preservation、goal\-guarding、impermanence、epistemic humility 和 human oversight 的 Philosophy Spec，对 Qwen2\.5\-32B\-Instruct 和 Qwen3\-32B 做 MSM \+ AFT。结果显示，在 27 个 OOD agentic misalignment evals 上，Qwen2\.5\-32B 的 misalignment rate 从 **68% 降到 5%**，Qwen3\-32B 从 **54% 降到 7%**，优于 deliberative alignment baseline。

第三，作者把 MSM 当作研究 **Model Spec science** 的工具，比较什么样的 spec 更容易产生泛化。结果发现：只写规则不够，解释规则背后的价值会更好；具体指导比笼统说“做一个有良好价值观的 agent”更有效。总体上，这篇文章说明：Model Spec 不只是给人类开发者看的说明书，也可以直接作为训练信号，帮助模型学到“为什么要对齐”，从而改善 OOD 对齐泛化。

