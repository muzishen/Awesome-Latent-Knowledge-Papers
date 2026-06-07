# Awesome Latent Knowledge Papers


## Paper Overview

### D. 发现与探测 / Discovery & Probing

| ID | Paper | Year | Venue | Notes |
|---|---|---:|---|---|
| D-001 | [How Do Transformers Learn to Associate Tokens](#d-001) | 2026 | ICLR 2026 | Token 关联形成 |
| D-002 | [What Do Language Models Learn and When? The Implicit Curriculum Hypothesis](#d-002) | 2026 | arXiv preprint | 能力隐式课程 |
| D-003 | [Transformer layers as painters](#d-003) | 2025 | AAAI | 层顺序鲁棒性 |
| D-004 | [LLM Safety From Within](#d-004) | 2026 | arXiv preprint | 内部安全神经元 |
| D-005 | [LLMs Encode Harmfulness and Refusal Separately](#d-005) | 2025 | arXiv preprint | 有害性与拒绝分离 |
| D-006 | [What do your logits know?](#d-006) | 2026 | arXiv preprint | Logits 信息泄露 |
| D-007 | [Convergent Evolution: How Different Language Models Learn Similar Number Representations](#d-007) | 2026 | arXiv preprint | 数字表示几何 |
| D-008 | [Task-Driven Subspace Decomposition for Knowledge Sharing and Isolation in LoRA-based Continual Learning](#d-008) | 2026 | ICML 2026 | LoRA 子空间分解 |
| D-009 | [Last-Layer-Centric Feature Recombination](#d-009) | 2026 | arXiv preprint | 最后层几何锚点 |
| D-010 | [Beyond Outliers: A Data-Free Layer-wise Mixed-Precision Quantization Approach Driven by Numerical and Structural Dual-Sensitivity](#d-010) | 2026 | arXiv preprint | 结构感知量化 |
| D-011 | [Large Language Models are Universal Reasoners for Visual Generation](#d-011) | 2026 | arXiv preprint | LLM 引导视觉生成 |
| D-012 | [The Cylindrical Representation Hypothesis for Language Model Steering](#d-012) | 2026 | arXiv preprint | 圆柱表示 steering |
| D-013 | [Disentangling Mathematical Reasoning in LLMs](#d-013) | 2026 | arXiv preprint | 数学推理分工 |
| D-014 | [Learning a Generative Meta-Model of LLM Activations](#d-014) | 2026 | arXiv preprint | 激活流形先验 |
| D-015 | [Vision Transformers Need More Than Registers](#d-015) | 2026 | arXiv preprint | ViT 背景捷径 |
| D-016 | [What Happens Inside Agent Memory? Circuit Analysis from Emergence to Diagnosis](#d-016) | 2026 | arXiv preprint | Agent 记忆电路 |
| D-017 | [Rethinking RL for LLM Reasoning: It’s Sparse Policy Selection, Not Capability Learning](#d-017) | 2026 | arXiv preprint | RL 稀疏策略选择 |
| D-018 | [A Single Neuron Is Sufficient to Bypass Safety Alignment in Large Language Models](#d-018) | 2026 | arXiv preprint | 单神经元安全绕过 |
| D-019 | [Compute Optimal Tokenization](#d-019) | 2026 | arXiv preprint | 字节级 scaling |
| D-020 | [The Truth Lies Somewhere in the Middle (of the Generated Tokens)](#d-020) | 2026 | arXiv preprint | 生成 token 表示 |
| D-021 | [Reasoning Emerges from Constrained Inference Manifolds in Large Language Models](#d-021) | 2026 | arXiv preprint | 推理流形健康度 |
| D-022 | [When Looking Is Not Enough: Visual Attention Structure Reveals Hallucination in MLLMs](#d-022) | 2026 | arXiv preprint | 视觉注意力幻觉 |
| D-023 | [Mechanistic Data Attribution: Tracing the Training Origins of Interpretable LLM Units](#d-023) | 2026 | arXiv preprint | 训练数据到电路 |

### I. 干预和转移 / Intervention & Transfer

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

### E. 评估与校准 / Evaluation & Calibration

| ID | Paper | Year | Venue | Notes |
|---|---|---:|---|---|
| E-001 | [Self-Distilled Reasoner: On-Policy Self-Distillation for Large Language Models](#e-001) | 2026 | arXiv preprint | 自蒸馏推理 |
| E-002 | [Language Models (Mostly) Know What They Know](#e-002) | 2022 | arXiv preprint | 自我知识校准 |
| E-003 | [Domain-Filtered Knowledge Graphs from Sparse Autoencoder Features](#e-003) | 2026 | arXiv preprint | SAE 知识图谱 |
| E-004 | [LLM DNA: Tracing Model Evolution via Functional Representations](#e-004) | 2026 | ICLR 2026 Oral | 模型功能 DNA |
| E-005 | [Locate, Steer, and Improve: A Practical Survey of Actionable Mechanistic Interpretability in LLMs](#e-005) | 2026 | arXiv preprint | 可行动 MI 综述 |
| E-006 | [From Parameter Dynamics to Risk Scoring](#e-006) | 2026 | arXiv preprint | 微调风险评分 |
| E-007 | [Learning Uncertainty from Sequential Internal Dispersion in Large Language Models](#e-007) | 2026 | arXiv preprint | 隐藏状态不确定性 |
| E-008 | [Black-Box Detection of LLM-Generated Text Using Generalized Jensen Shannon Divergence](#e-008) | 2025 | arXiv preprint | Surprisal 转移检测 |
| E-009 | [Depression and Anxiety Characterization and Detection with Multimodal Deep Learning](#e-009) | 2026 | Nature Mental Health | 多模态心理健康综述 |
| E-010 | [Restoring Exploration after Post-Training: Latent Exploration Decoding for Large Reasoning Models](#e-010) | 2026 | arXiv preprint | latent 探索解码 |
| E-011 | [Information Flow Reveals When to Trust Language Models](#e-011) | TBD | OpenReview | 信息流可信度 |
| E-012 | [Tracing Uncertainty in Language Model “Reasoning”](#e-012) | 2026 | arXiv preprint | 推理不确定性轨迹 |
| E-013 | [Towards Generation-Efficient Uncertainty Estimation in Large Language Models](#e-013) | 2026 | arXiv preprint | 早期不确定性估计 |
| E-014 | [Evaluating the Statistical Realism of LLM-generated Social Science Data](#e-014) | 2026 | PNAS | 社会数据统计真实性 |
| E-015 | [Into the Gray Zone: Domain Contexts Can Blur LLM Safety Boundaries](#e-015) | 2026 | arXiv preprint | 安全灰区上下文 |
| E-016 | [Towards Intrinsic Interpretability of Large Language Models: A Survey of Design Principles and Architectures](#e-016) | 2026 | arXiv preprint | 内生可解释性综述 |
| E-017 | [Assessing the Creativity of Large Language Models: Testing, Limits, and New Frontiers](#e-017) | 2026 | arXiv preprint | 创造力评估有效性 |

## D. 发现与探测：探讨模型内部 LK 的形成规律、空间分布以及表里状态差异

<a id="d-001"></a>

### D-001. [How Do Transformers Learn to Associate Tokens](https://openreview.net/pdf?id=A4Us8jxVGq)

**发现问题：**
 Transformer 能学到词之间的语义关联，比如 “bird” 和 “flew”、“fish” 和 “pond”，但我们并不清楚这些关联是如何在训练过程中形成的。已有理论分析往往依赖合成数据、简化结构或非标准训练方式，和真实 LLM 训练差距较大。

**Insight：**
 作者提出一个直观解释：Transformer 早期训练的梯度主导项，已经决定了模型如何开始建立 token 关联。作者发现，模型权重可以由三类简单统计函数组合而成：bigram mapping 捕捉相邻词关系，interchangeability mapping 捕捉功能相似词，context mapping 捕捉长距离上下文关系。也就是说，Transformer 一开始并不是随机地学语义，而是在用语料统计逐步搭建语义关联网络。

**任务：**
 用于解释 Transformer 如何从自然语言数据中学习 token 之间的语义关联。作者通过梯度 leading\-term 分析，推导 output matrix、value matrix、query\-key matrix 和 positional encoding 的闭式近似表达。实验在 TinyStories 上训练 3\-layer attention\-only Transformer，并在 Pythia\-1\.4B 与 OpenWebText / FineWeb 上验证。结果表明，理论刻画的权重结构与真实模型学习到的权重高度一致，并能解释不同层和 attention heads 如何逐步形成语义关联。


<a id="d-002"></a>

### D-002. [What Do Language Models Learn and When? The Implicit Curriculum Hypothesis](https://arxiv.org/pdf/2604.08510)

**发现问题：**
 现有 scaling law 主要告诉我们模型整体 loss 会如何下降，但不能解释模型在预训练过程中**具体什么时候学会了哪些能力**。例如 GSM8k 性能变差时，很难判断问题出在数学能力、语言理解，还是多步推理能力上。

**Insight：**
 作者提出 **Implicit Curriculum Hypothesis**：语言模型预训练并不是随机地学会能力，而是遵循一种隐式课程。简单能力通常先出现，复杂组合能力通常后出现；而且这种能力出现顺序在不同模型家族、不同规模、不同数据混合下都比较稳定。进一步地，相似任务在模型内部表示中也更接近，因此可以用任务表示来预测某些任务的学习轨迹。

**任务：**
 用于 **分析语言模型预训练过程中的能力涌现顺序与训练动态**。作者设计了 91 个简单任务和组合任务，包括复制、大小写转换、形态变化、翻译、事实抽取、指代消解、逻辑推理和数学任务，并在 Pythia、OLMo、LLM360 等多个模型家族的中间 checkpoint 上跟踪这些能力什么时候出现。


<a id="d-003"></a>

### D-003. [Transformer layers as painters](https://ojs.aaai.org/index.php/AAAI/article/view/34708)

**发现问题：**
 Transformer 的每一层结构相同，但我们并不清楚每一层到底是否都不可替代、层顺序是否严格重要。作者发现：底层和最后几层比较特殊，但大量中间层表现出明显相似性，说明中间层可能共享某种表示空间。

**Insight：**
 作者提出一个直观类比：Transformer 中间层像一组“画家”，都在同一张画布上逐步添加信息。不同层不是完全冗余的，但它们能理解相似的中间表示，所以模型对跳过中间层、交换中间层顺序、甚至并行运行中间层都有一定鲁棒性。也就是说，**中间层共享表示空间，但执行的是不同功能。** 

**任务：**
 用于 **分析 Transformer 层的功能、鲁棒性和推理加速潜力**。作者在冻结模型上测试不同执行策略，包括跳层、重复中间层、反转层顺序、随机层顺序、并行层和循环并行层。实验覆盖 Llama2、BERT\-Large，并补充 Mistral\-7B、Pythia\-6\.9B，评测任务包括 LAMBADA、ARC、GSM8K、HellaSwag、WinoGrande 和 GLUE。


<a id="d-004"></a>

### D-004. [LLM Safety From Within](https://arxiv.org/pdf/2604.18519)

**发现问题：**
 现有 LLM 安全检测模型通常只看最后一层表示，或者通过生成 “safe/unsafe” 来做分类。但作者发现，安全相关信息并不只存在于最后一层，而是分布在模型的多个中间层中。只依赖最后一层会浪费大量内部安全信号，也会带来更高的推理开销。

**Insight：**
 作者提出一个直观想法：LLM 内部其实已经有很多“安全神经元”，它们能反映文本是否有害。与其重新训练一个完整 guard model，不如直接从模型内部各层找出这些安全相关神经元，再把不同层的信息加权聚合起来，用一个轻量分类器判断 harmful / safe。

**任务：**
 用于检测用户输入和模型回复中的有害内容。作者提出 SIREN，先用线性探针在每一层识别 safety neurons，再根据各层验证集表现进行自适应加权聚合，最后训练轻量 MLP 分类器。实验覆盖 Qwen3、Llama3 系列 backbone，以及 ToxicChat、OpenAIModeration、Aegis、WildGuard、SafeRLHF、BeaverTails 等安全检测数据集。结果表明，SIREN 比现有 guard models 表现更好，参数更少，并且能泛化到 reasoning traces 和 streaming detection 场景。




<a id="d-005"></a>

### D-005. [LLMs Encode Harmfulness and Refusal Separately](https://arxiv.org/pdf/2507.11878)

**发现问题：**
 现有研究通常把 LLM 的“拒绝行为”和“有害性判断”混在一起理解，认为模型拒绝了就说明它判断输入有害。但作者发现：模型有时会**知道输入是有害的，却仍然被 jailbreak 诱导接受**；也有时**知道输入是无害的，却仍然过度拒绝**。这说明拒绝行为不一定等于模型真正的有害性理解。

**Insight：**
 作者发现 LLM 内部其实把 **harmfulness** 和 **refusal** 分开编码：

- 在用户指令最后一个 token 位置，模型主要编码“这个请求是否有害”； 

- 在 prompt 模板结束后的 token 位置，模型主要编码“是否应该拒绝”。 

也就是说，**模型内部的有害性判断比表面的拒绝行为更稳定、更真实**。因此，可以利用 hidden state 中的 harmfulness representation 来判断输入是否危险，而不是只看模型最后有没有拒绝。

**任务：**
 用于 **LLM safety mechanism analysis 和安全防护**。具体包括：

- 分析 LLM 内部如何分别表示 harmfulness 和 refusal； 

- 解释 jailbreak 为什么能成功，例如有些 jailbreak 只是压低拒绝信号，但模型内部仍知道请求有害； 

- 构建 **Latent Guard**，利用模型内部的 harmfulness 表示来检测有害输入，减少 jailbreak 和 over\-refusal。 

实验使用 Llama2\-Chat、Llama3\-Instruct、Qwen2\-Instruct，评测包括 AdvBench、JailbreakBench、Sorry\-Bench、XSTest，以及 adversarial suffix、persuasion、jailbreak template 等 jailbreak 方法。




<a id="d-006"></a>

### D-006. [What do your logits know?](https://arxiv.org/pdf/2604.09885)

**发现问题：**
 用户通常只能看到模型最终回答，或者最多看到 top\-k logits，但作者发现：这些 logits 里可能隐藏了很多不该泄露的信息。即使模型只回答 “Yes/No”，它的 logits 仍可能暴露图像中的额外属性，比如目标物体的颜色、大小、材质，甚至背景物体的信息。

**Insight：**
 作者的核心 insight 是：**logits 不是一个干净的信息瓶颈。**
 也就是说，模型在生成答案前并没有完全丢掉无关信息；相反，一部分与最终回答无关的信息会继续保留在 top logits 中。尤其当观察的 logits 数量稍微增加时，这些隐藏信息就可以被 probe 解码出来，造成潜在隐私泄露和安全风险。

**任务：**
 用于 **分析 VLM 的信息泄露与可解释性**。作者通过视觉问答任务测试模型：给一张图，问 “图中是否有某个物体？只回答一个词”。然后研究不同表示层级，包括 hidden states、logit trajectories、final top\-k logits 中分别保留了多少图像信息。实验覆盖 CLEVR 和 MSCOCO 数据集，以及 Qwen3\-VL、LLaVA、Llama\-3\.2\-Vision 等模型。




<a id="d-007"></a>

### D-007. [Convergent Evolution: How Different Language Models Learn Similar Number Representations](https://arxiv.org/pdf/2604.20817)

**发现问题：**
 很多语言模型都会学到数字 token 的周期性表示，比如在 Fourier 频域中出现 **T=2、5、10** 的周期峰值。但作者发现：有 Fourier spike 不代表模型真的学会了可用的数字结构。比如 LSTM 和原始 token 频率分布也有明显周期峰值，但无法用线性 probe 解码 `n mod T`。

**Insight：**
 作者提出一个两层理解：数字表示有 **spectral convergence** 和 **geometric convergence**。前者只是频域上看起来有周期结构，后者才表示数字按 `mod T` 在几何空间中可分。换句话说，Fourier spike 像“看起来有规律的影子”，但 linear probe 能分出 `mod T` 才说明模型真的形成了功能性数字表示。

**任务：**
 用于分析不同模型如何学习数字表示，以及哪些因素决定数字表示是否真正可用。作者比较 Transformer、Mamba、Gated DeltaNet、LSTM、GloVe、FastText 和原始 token 分布，并通过 Fourier spectrum 与 mod\-T linear probing 区分 spectral / geometric convergence。实验还控制数据、架构、优化器和 tokenizer，发现自然语言中的数字\-文本共现、数字间交互、上下文长度，以及多 token 加法任务都会影响几何可分的数字表示形成。


<a id="d-008"></a>

### D-008. [Task-Driven Subspace Decomposition for Knowledge Sharing and Isolation in LoRA-based Continual Learning](https://arxiv.org/pdf/2603.00191)

**发现问题：**
 LoRA\-based continual learning 通常通过“隔离新任务更新空间”来避免遗忘，比如把新任务放到旧任务的 null space 中。但作者发现：这种做法过度强调隔离，忽略了任务之间可共享的知识；而且旧任务的 null space 不一定对新任务有效，可能只是“安全但没用”的空间，导致新任务也学不好。

**Insight：**
 作者提出一个直观想法：LoRA 的 down\-projection 像一个“门”，决定模型能学习输入特征中的哪些方向。与其只找不影响旧任务的方向，不如把空间分成两类：一类是 **general subspace**，旧任务和新任务都强激活，用来共享知识；另一类是 **isolated subspace**，新任务强激活、旧任务弱激活，用来学习新任务特有知识。这样既能转移共享知识，又能隔离任务冲突。

**任务：**
 用于解决 LoRA 连续学习中的灾难性遗忘和稳定性\-可塑性冲突。作者提出 **LoDA**，先根据 projection energy 分解出 general / isolated 两个 LoRA 子空间，固定 down\-projection，只训练 up\-projection；再用 **Gradient\-Aligned Optimization（GAO）** 提升梯度一致性；训练后对 general branch 做 closed\-form recalibration，再合并 LoRA 到 backbone。实验覆盖 ImageNetR、ImageNetA、CIFAR100、CUB、DomainNet，并在 ViT、CLIP、DINO、iBOT 等 backbone 上验证，结果优于现有 PEFT\-based continual learning 方法。


<a id="d-009"></a>

### D-009. [Last-Layer-Centric Feature Recombination](https://arxiv.org/pdf/2604.26454)

**发现问题：**
 现有基于 DINO / ViT 的单目深度估计通常会均匀选取几个中间层做多尺度特征，默认 3D 几何信息在各层中均匀分布。但作者发现并不是这样：DINOv3 的 3D 几何知识主要集中在更深层，尤其最后几层的深度可预测性更强，也更能反映样本之间的几何差异。

**Insight：**
 作者提出一个直观想法：最后一层应该作为“几何锚点”，而不是只把它当作普通多尺度特征之一。中间层不是越多越好，而是要选择和最后一层最互补的层。于是 LFR 用最后一层作为主表示，再挑选与它相似度最低的中间层进行重组，让模型既保留最后一层强 3D 几何信息，又补充中间层的互补细节。

**任务：**
 用于提升 DINOv3 在单目深度估计中的 3D 几何迁移能力。作者提出 **Last\-Layer\-Centric Feature Recombination（LFR）**，插入在 DINOv3 backbone 和 DPT decoder 之间：先用 minimal\-similarity 策略选择互补中间层，再通过轻量 linear adapter 与最后一层特征融合，最后进行多层加权深度预测。实验覆盖 NYU\-Depth v2、KITTI，并在 SUN RGB\-D 和 Argoverse 上做 zero\-shot 测试。结果显示，LFR 能稳定提升 DINOv3 的深度估计精度和跨数据集泛化能力。


<a id="d-010"></a>

### D-010. [Beyond Outliers: A Data-Free Layer-wise Mixed-Precision Quantization Approach Driven by Numerical and Structural Dual-Sensitivity](https://arxiv.org/pdf/2603.17354)

**发现问题：**
 现有层级混合精度量化方法通常只看权重 outlier、误差或熵等单一数值指标，并且把同一层里的所有模块一视同仁。但作者发现：有些层虽然数值 outlier 不明显，量化后仍会严重掉点，因为它们的结构表达能力很关键。也就是说，层敏感性不只来自“数值异常”，还来自“结构功能”。

**Insight：**
 作者提出一个直观想法：量化时不能只看哪一层“数值更极端”，还要看这一层在模型里“干什么”。他们把 Transformer 层拆成两类角色：**Detector** 负责检测模式，比如 QK、FFN input；**Writer** 负责把信息写回 residual stream，比如 OV、FFN output。NSDS 同时评估每个组件的 **Numerical Vulnerability** 和 **Structural Expressiveness**，再合成层级敏感性分数，决定哪些层保留更高 bit。

**任务：**
 用于在无校准数据的情况下做 LLM 层级混合精度量化。作者提出 **NSDS**，先用机制视角分解每层的 Detector / Writer，再用 excess kurtosis 衡量数值脆弱性，用 SVD 谱能量、谱熵和角色感知重加权衡量结构表达性，最后通过 **MAD\-Sigmoid \+ Soft\-OR** 聚合成层敏感性分数，并将高敏感层分配 4\-bit、低敏感层分配 2\-bit。实验覆盖 Llama\-3\.1\-8B、Qwen2\.5\-7B、Llama\-2\-13B、Qwen2\.5\-14B，任务包括 ARC\-C、HellaSwag、PIQA、BoolQ、WinoGrande、TruthfulQA、WikiText\-2 和 C4。结果显示，NSDS 在不同 bit budget、不同模型规模和不同 PTQ 后端上都优于或接近现有方法。


<a id="d-011"></a>

### D-011. [Large Language Models are Universal Reasoners for Visual Generation](https://arxiv.org/pdf/2605.04040)

**发现问题：**
 现有文生图模型即使使用同一个 LLM 同时做理解和生成，也经常出现“理解强、生成弱”的问题：模型生成时会弄错数量、位置关系、物理常识等，但让它检查自己生成的图时，却能准确发现这些错误。作者把这个现象称为 **understanding\-generation gap**。

**Insight：**
 作者提出一个直观想法：不要只把 LLM 当作 text encoder，而要把它当作“视觉生成的通用推理器”。LLM 先根据 prompt 生成一个粗糙的视觉草图，再自己检查这个草图哪里不符合 prompt，最后把 **prompt \+ draft \+ evaluation** 一起交给 diffusion model。这样，draft 提供场景布局，evaluation 提供“哪里需要改”的纠错信号，让生成过程不再只依赖单一文本 embedding。

**任务：**
 用于提升文生图模型对复杂 prompt 的语义一致性和组合约束满足能力。作者提出 **UniReasoner**，采用 **Draft–Evaluate–Diffuse** 三阶段流程：先用 LLM 生成离散视觉 token 草图，再让同一个 LLM 对草图进行自我评估，指出缺失物体、错误数量、错误属性或空间关系，最后用冻结的 SANA diffusion backbone 在三重条件下生成最终图像。实验在 GenEval 和 DPG\-Bench 上验证，UniReasoner 在相同 diffusion generator 下将 GenEval 从 **0\.79 提升到 0\.88**，DPG\-Bench 从 **84\.50 提升到 86\.30**，尤其提升 Counting、Position 和 Attribute Binding。


<a id="d-012"></a>

### D-012. [The Cylindrical Representation Hypothesis for Language Model Steering](https://arxiv.org/pdf/2605.01844)

**发现问题：**
 现有 activation steering 通常基于 **Linear Representation Hypothesis**，认为概念可以用一个全局线性方向控制。但作者发现：真实模型中概念方向并不完全正交，不同概念会相互重叠，所以同一个 steering vector 在不同样本上效果很不稳定。有些样本能成功激活目标概念，有些样本却失败或输出崩坏。

**Insight：**
 作者提出一个直观几何解释：模型表示不是简单的一条“概念直线”，而更像围绕样本形成的“圆柱结构”。圆柱的 **central axis** 负责把表示推向目标概念；周围的 **normal plane** 决定这个推动是否容易成功。normal plane 里又有一些 **sensitive sectors**，进入这些区域会促进概念激活；进入其他区域则可能抑制、延迟甚至破坏 steering。因此，steering 不稳定不是随机噪声，而是因为每个样本都有自己的局部几何结构。

**任务：**
 用于解释和预测 LLM activation steering 为什么在不同样本上表现不稳定。作者提出 **Cylindrical Representation Hypothesis（CRH）**，将 steering vector 分解为 axis component、normal\-plane component 和 residual component，并分析不同部分对概念激活和输出崩坏的影响。实验覆盖 Gemma\-2B\-IT、LLaMA2\-7B\-Chat，测试 100 个 text/code/math 概念，并比较 DiffMean、PCA、Mean\-Centering、Probe\-based steering 等方法。结果显示，normal\-plane component 越强，目标概念越早出现，但输出也越容易崩坏；同时，sensitive sector 无法仅由相似的 difference vector 稳定预测，解释了 steering 的样本级不可预测性。


<a id="d-013"></a>

### D-013. [Disentangling Mathematical Reasoning in LLMs](https://arxiv.org/pdf/2604.15842v1)

**发现问题：**
 LLM 能做一些简单算术，但我们并不清楚它到底是在“背答案”、做模式匹配，还是在内部真的执行某种计算过程。作者发现：模型很早就能识别这是一个数学任务，但正确答案并不是早期就出现，而是在最后几层才被生成出来。

**Insight：**
 作者提出一个直观解释：算术推理像是模型内部的一场“分工合作”。**Attention** 负责把输入里的关键信息搬到最后一个 token 上，比如操作数和运算符；**MLP** 负责在这些信息基础上逐步聚合、变换，最后生成答案。会算术的模型有清晰分工，不会算术的模型这种分工不明显。

**任务：**
 用于分析 LLM 做数学推理时的内部机制。作者使用 **early decoding / logit lens**，在每一层 attention 和 MLP 后把 residual stream 解码成中间预测，观察模型什么时候识别任务、什么时候传播操作数和运算符、什么时候生成正确结果。实验比较 GPT\-NeoX\-20B 和 GPT\-2 XL，在加法、减法、两操作数和三操作数任务上验证。结果显示，GPT\-NeoX\-20B 中 attention 会在中间层传播 operand/operator，MLP 在后期逐步形成答案；而 GPT\-2 XL 缺少这种 attention\-MLP 分工，因此算术能力很差。


<a id="d-014"></a>

### D-014. [Learning a Generative Meta-Model of LLM Activations](https://arxiv.org/pdf/2602.06964)

**发现问题：**
 现有激活分析方法，比如 PCA、SAE、线性 steering，通常假设模型内部表示具有线性或稀疏结构。但作者发现：这些假设可能太强，干预时容易把 activation 推到模型真实分布之外，导致输出不流畅或崩坏。因此，仅靠线性方向或稀疏特征，可能无法准确刻画 LLM activation manifold。

**Insight：**
 作者提出一个直观想法：与其手工假设 activation 是线性的、稀疏的，不如直接训练一个“activation 世界模型”。也就是用 diffusion model 学习 LLM 内部 residual stream activation 的真实分布。这个模型像一个 **activation prior**：当 steering 把表示推歪后，它可以把 activation 拉回自然流形，同时尽量保留想要注入的语义。

**任务：**
 用于学习 LLM activation 的生成式表示模型，并辅助解释和干预。作者提出 **Generative Latent Prior（GLP）**，在 10 亿个 residual stream activations 上训练 diffusion meta\-model，覆盖 Llama1B 和 Llama8B。GLP 可用于两类任务：一是 **on\-manifold steering**，提升 sentiment steering、SAE feature steering、persona elicitation 的概念控制与流畅性平衡；二是作为 feature encoder，用 **meta\-neurons** 做 1\-D probing，在 113 个二分类概念任务上优于 SAE、raw layer output 和 raw MLP neurons。实验还显示，GLP 的 diffusion loss 随 compute 平滑下降，并能预测 steering 和 probing 的下游效果。


<a id="d-015"></a>

### D-015. [Vision Transformers Need More Than Registers](https://arxiv.org/pdf/2602.22394)

**发现问题：**
 ViT 在 dense vision 任务中经常出现奇怪 artifacts，比如背景区域反而和 CLS token 更相似，导致定位、分割、开放词汇检测表现差。已有方法认为问题来自 high\-norm tokens，并用 register tokens 缓解；但作者发现：register 只能消除 high\-norm 现象，不能解决根本问题。真正原因是 ViT 学会了用背景 patch 作为捷径来表达全局语义。

**Insight：**
 作者提出一个直观解释：ViT 的 CLS token 有点“偷懒”。因为训练监督通常只有图像级标签或图文级对齐，没有 patch 级监督；再加上全局 attention 能让前景信息扩散到背景，CLS token 就会从大量背景 patch 中聚合语义，而不是只看真正的物体。也就是说，背景 patch 变成了“语义捷径”，模型分类能对，但 dense feature 会错位。

**任务：**
 用于分析并缓解 ViT 中的 dense\-feature artifacts。作者提出 **Patch Score** 衡量 patch 与 CLS token 的相似度，并用 **Point\-in\-Box（PiB）** 判断最高分 patch 是否落在前景框内；分析发现 ViT 的高分 patch 更常落在背景，且这种偏差从训练早期就出现。为解决该问题，作者提出 **LaSt\-ViT / LazyStrike**：用频域 low\-pass filtering 计算每个 patch 的稳定性，再按 channel\-wise Top\-K 选择稳定 patch 聚合到 CLS token，减少背景 shortcut。实验覆盖 label\-supervised、text\-supervised 和 self\-supervised ViT，在 ImageNet、VOC、COCO、ADE20K、Cityscapes、LVIS 等 12 个 benchmark 上验证，提升 object discovery、semantic segmentation、open\-vocabulary detection 和 instance segmentation。


<a id="d-016"></a>

### D-016. [What Happens Inside Agent Memory? Circuit Analysis from Emergence to Diagnosis](https://arxiv.org/pdf/2605.03354)

**发现问题：**
 Agent memory 的失败很隐蔽：模型可能回答得很流畅，但其实在某一步已经失败了，比如没有正确写入事实、错误更新记忆，或者读取时没有用上正确记忆。现有评估通常只看最终 QA 准确率，无法判断到底是 **Write、Manage、Read** 哪个阶段出错。作者发现：不同记忆阶段在模型内部有可分离的 circuit signature，因此可以从内部机制定位 silent failure。

**Insight：**
 作者的核心发现很直观：Agent memory 不是一个整体能力，而是由不同内部电路分工完成的。**Manage / routing 电路最早出现**，0\.6B 小模型就能学会“要不要更新/删除/保留”的控制逻辑；但 **Write / Read 内容电路要到 4B 才明显出现**。也就是说，小模型可能已经会做记忆管理决策，但还不会可靠提取和使用事实，形成 “control before content” 的错配。

另一个关键发现是：Write 和 Read 都会用到一个后层 **hub circuit**。这个 hub 不是 agent memory 新造出来的，而是 base model 里原本就存在的上下文 grounding 机制；memory prompt 只是把这个已有机制“招募”到记忆任务中。

**任务：**
 用于分析 LLM agent memory 的内部机制，并诊断记忆系统中 silent failure 的来源。作者在 Qwen\-3 系列 **0\.6B / 4B / 8B / 14B** 上，用 pre\-trained transcoders 和 feature circuit tracing 分析 **mem0** 与 **A\-MEM** 两种记忆框架的 Write、Manage、Read 三个阶段。实验发现：Manage circuit 在 0\.6B 已有因果信号，而 Write / Read 到 4B 才出现；Write 和 Read 共享 late\-layer hub，并且该结构跨 mem0 和 A\-MEM 都存在。基于这些 circuit signature，作者提出一个无监督 stage\-level diagnostic，可以把错误定位到具体阶段，准确率达到 **76\.2%**，比最强监督 baseline 高约 **13 个点**。总体上，这篇文章把 agent memory 从“外部流程分析”推进到“内部电路诊断”。


<a id="d-017"></a>

### D-017. [Rethinking RL for LLM Reasoning: It’s Sparse Policy Selection, Not Capability Learning](https://arxiv.org/pdf/2605.06241)

**发现问题：**
 大家通常认为 RL 能让 LLM 学到新的推理能力，但作者发现：RL 可能并没有真正教会模型新的 reasoning strategy，而只是把 base model 本来就会的正确路径概率提高了。也就是说，base model 的采样空间里已经有正确解，RL 主要是在关键分叉点帮模型“选对路”。

**Insight：**
 作者的核心洞察是：RL 对推理的改变非常稀疏。它不是大规模改写模型行为，而只是在少数 **high\-entropy decision points** 上重新排序 token 概率。论文发现，RL 只影响大约 **1–3%** 的 token 位置，而且被 RL 提升的 token 基本都已经在 base model 的 top\-5 候选里。换句话说，RL 不是“创造新能力”，而是在模型犹豫的时候，把原本第二、第三可能的正确分支提上来。

**任务：**
 用于重新理解 RL 在 LLM 数学推理中的作用，并提出低成本替代方法。作者通过 token\-level analysis 比较 base model 和 RL model，发现 RL 的有效修改集中在高熵位置；oracle 实验证明只修正这些少数 token 就能恢复大部分甚至全部 RL 提升；同时 KL\-LoRA 实验证明这种修正可以被极小 adapter 表示。基于此，作者提出 **REASONMAXXER**：不用 RL，只从 base model 生成少量 rollouts，筛选那些有对有错的题目，在高熵 token 上做 advantage\-weighted contrastive loss，其他位置用 KL anchor 保持 base model 行为。实验覆盖 Qwen2\.5、Qwen3、DeepSeek\-R1\-Distill、Mistral 等模型，以及 MATH\-500、GSM8K、AMC、AIME、Minerva、OlympiadBench。结果显示，REASONMAXXER 用几十道题、几分钟单卡训练，就能匹配或超过完整 RL，训练成本降低约三个数量级。



<a id="d-018"></a>

### D-018. [A Single Neuron Is Sufficient to Bypass Safety Alignment in Large Language Models](https://arxiv.org/pdf/2605.08513)

**发现问题：**
 大家通常认为 LLM 的安全对齐是分散在整个模型里的，所以应该比较鲁棒，不会被单个局部组件轻易破坏。但这篇文章发现并不是这样：安全拒答可能存在非常细粒度的“瓶颈”，只要干预一个 MLP neuron，就可能显著改变模型是否拒绝有害请求。

**Insight：**
 作者提出一个很直观的两系统视角：
 一类是 **refusal neurons**，像“安全闸门”，决定模型要不要拒答；
 另一类是 **concept neurons**，像“有害知识存储点”，编码具体有害概念。
 也就是说，模型并不是不知道有害知识，而是 alignment 主要通过少数关键神经元控制这些知识能不能被说出来。

**任务：**
 用于分析 LLM 安全对齐是否真的鲁棒，以及安全行为是否能被定位到单个神经元。作者在 Qwen3 和 Llama\-3\.1 共 7 个模型上，用 harmful / harmless prompts 的 activation 和 gradient 信号定位 **refusal neuron**，再通过单神经元干预验证其因果作用；同时还用 **suicide neuron** 做概念层面的验证。实验覆盖 Qwen3\-1\.7B / 4B / 8B / 14B / 32B，以及 Llama\-3\.1\-8B / 70B；评测包括 HarmBench、JailbreakBench、XSTest、MMLU 和 GSM8K。结果显示：抑制单个 refusal neuron 就能高成功率绕过安全拒答，而放大单个 concept neuron 也能让无害 prompt 生成自杀相关内容；此外，这些 refusal neurons 在 base model 中已经存在，说明 alignment 更像是在调节已有安全相关神经元，而不是从零创造安全机制。


<a id="d-019"></a>

### D-019. [Compute Optimal Tokenization](https://arxiv.org/pdf/2605.01188v1)

**发现问题：**
 现有 scaling law 通常用 “tokens per parameter” 来决定模型大小和训练数据量，比如 Chinchilla 的约 20 tokens / parameter。但作者指出：token 不是稳定单位，因为不同 tokenizer 的压缩率不同，同样一段文本可能被切成更多或更少 token。也就是说，如果只看 token 数，会把 tokenizer 的影响混进 scaling law 里。作者发现：真正更稳定的单位不是 token，而是 **byte**。在 compute\-optimal 设置下，训练数据的 **bytes** 和模型参数量之间保持近似固定比例，而不是 tokens 和参数量。

**Insight：**
 作者的核心直觉是：tokenizer 决定了模型一次看到的信息粒度。
 压缩率太低，比如 byte / character\-level，序列太长，训练和推理都很贵；压缩率太高，比如过大的 subword / multi\-word token，每个 token 承载太多信息，模型又不容易学好。因此 tokenization 不是“越压缩越好”，而是存在一个 **compute\-optimal compression rate**。
 简单说：模型训练不是应该固定 “多少 token 配多少参数”，而是应该固定 “多少字节信息配多少参数”，再根据算力选择最合适的信息颗粒度。

**任务：**
 用于研究不同 tokenization 压缩率如何影响 LLM scaling law，并指导 tokenizer / vocabulary / latent tokenization 的选择。作者训练了 **988 个 latent\-tokenized BLT 模型** 和 **320 个 subword\-tokenized 模型**，模型规模从 50M 到 6\.7B，训练预算从 5e18 到 2e21 FLOPs；通过控制 compression rate，即平均每个 token 表示多少 bytes，分析 compute\-optimal 的数据量、模型大小和 loss。实验覆盖 BLT latent tokenization、character tokenization、BPE、masked BPE、SuperBPE，并扩展到 English、French、Vietnamese、Arabic、Russian、Hindi 等语言。结果显示：英文下 compute\-optimal 训练大约对应 **60 bytes / parameter**；最优压缩率不是固定 BPE 的 4\.57 bytes/token，而是随 compute 增大略微下降；不同语言的最优压缩率不同，并与语言的 byte parity / 信息密度相关。总体上，这篇文章把 scaling law 从 “token 数量” 推进到 “信息字节量 \+ token 压缩率” 的视角。


<a id="d-020"></a>

### D-020. [The Truth Lies Somewhere in the Middle (of the Generated Tokens)](https://arxiv.org/pdf/2605.09969)

**发现问题：**
 在 autoregressive LLM 里，大家通常会用某一个 token 的 hidden state，比如最后一个 token，来当作整段文本的表示。但作者发现：生成过程中的语义信息并不集中在某一个 token 上，而是分散在多个 generated tokens 里。也就是说，单独看最后一个 token 或某个中间 token，都不能最好地代表模型内部对输入语义的理解。

**Insight：**
 作者的核心直觉是：LLM 在生成时不是一次性形成完整语义表示，而是在生成轨迹中逐步积累和展开内部状态。
 每个 generated token 都像记录了模型思考过程中的一部分信息：有些 token 负责泛化铺垫，有些 token 触发 recall，有些 token 开始进入具体语义描述。
 所以，真正好的表示不在“最后一个 token”，而在“生成 token 的中间整体”里。把多个 generated token 的 hidden states 做 **mean pooling**，反而能得到更接近真实语义结构的 embedding。

**任务：**
 用于研究 autoregressive LLM 的 generated\-token hidden states 应该如何聚合成语义表示，并分析生成过程中的内部状态变化。作者比较 **last\-token pooling** 和 **mean\-token pooling**，用 kernel alignment / CKA 衡量 LLM 表示和参考空间之间的一致性。实验覆盖 vision\-language、reasoning 和 protein 三类任务：视觉任务用 WIT、DCI，并和 DINOv2 图像表示对齐；推理任务用 MATH\-500、GPQA\-Diamond，并和 gold solution 表示对齐；蛋白任务用 UniProt，并和 ESM\-3 蛋白结构表示对齐。结果显示，**generated tokens 的 mean pooling 表示优于任何单个 token**，也优于 prompt\-token 表示；不同生成片段、不同 decoding seeds、不同图像区域描述的表示混合后，alignment 进一步提升。作者还发现，生成中的 “Let me recall what I know” 这类 recall phrase 会引起表示空间的明显跃迁，说明 generated tokens 不只是输出文本，也在推动模型内部状态转移。总体上，这篇文章说明：autoregressive generation 本身可以产生更好的语义 embedding，而语义信息是沿生成轨迹分布式存在的。


<a id="d-021"></a>

### D-021. [Reasoning Emerges from Constrained Inference Manifolds in Large Language Models](https://arxiv.org/pdf/2605.08142)

**发现问题：**
 现在大家通常用 benchmark accuracy 判断 LLM 是否会 reasoning，但这种评估会把任务数据、prompt 技巧、答案格式和模型内部推理质量混在一起。作者发现：如果不看最终答案，而是直接看模型推理时 hidden states 的动态变化，会发现 LLM 的 reasoning 并不是在高维空间里随意游走，而是会自发压缩到一个低维 manifold 上。

**Insight：**
 作者的核心直觉是：好的 reasoning 不是“越压缩越好”，而是要落在一个合适的结构区间里。
 模型推理时需要三件事同时成立：
**第一，有足够大的表达空间**，能表示复杂概念；
**第二，推理轨迹会自发压缩到低维 manifold**，避免在高维空间里发散；
**第三，低维 manifold 里还要保留足够的信息量**，不能压缩到信息塌缩。
 也就是说，健康推理像是在“窄而有信息的轨道”上前进：轨道太散会不稳定，轨道太窄又会丢失中间计算。

**任务：**
 用于从内部几何结构角度诊断 LLM reasoning 是否健康，而不依赖答案标签。作者记录模型生成过程中每一层最后一个 token 的 hidden state，把它看成 inference trajectory；然后计算三类结构量：**Dstim** 表示推理轨迹的 intrinsic dimension，衡量是否形成低维 manifold；**V** 表示 information volume，衡量压缩后的轨迹是否仍保留有效信息；**Dworld** 表示静态 vocabulary embedding 的 intrinsic dimension，衡量模型整体表达能力。基于这三者，作者提出 label\-free reasoning health score：
**H = log\(Dworld\) · V / exp\(εDstim\)**。
 实验覆盖 Qwen2\.5、Qwen3、Gemma3、DeepSeek\-R1\-Distill\-Qwen 等多个模型族和规模，并用 MMLU\-Other 的通用认知刺激提取内部动态。结果显示，推理轨迹普遍会随层数加深快速降维，但单看低维度不能预测能力；高性能模型通常同时具有低 Dstim、高 V 和足够 Dworld。这个无标签指标 H 和 AIME、Arena\-Hard、AutoLogi、BFCL、GPQA、LiveBench、LiveCodeBench 等下游 benchmark 表现有很高 Spearman 相关性。总体上，这篇文章把 reasoning 评估从“看答案对不对”推进到“看内部推理轨迹是否处在几何和信息约束允许的健康区域”。


<a id="d-022"></a>

### D-022. [When Looking Is Not Enough: Visual Attention Structure Reveals Hallucination in MLLMs](https://arxiv.org/pdf/2605.11559)

**发现问题：**
 很多多模态大模型会产生 **visual hallucination**，比如图里没有某个物体却说有，或者对图像关系判断错误。常见解释是：模型幻觉是因为“不看图”或 visual attention 不够。但作者发现并不是这么简单：模型即使对 image tokens 分配了很高 attention，也可能仍然输出错误答案。也就是说，幻觉不一定是“看得少”，而可能是“看了，但视觉注意力结构已经错了”。

**Insight：**
 作者的核心洞察是：判断 MLLM 是否要 hallucinate，不能只看 visual attention 的总量，而要看 attention 在图像 token 上的 **空间结构**。
 如果 visual attention 是平滑、集中、连贯的，说明模型可能在稳定 grounding；如果 attention 在图像 patch 上出现很多尖峰、跳变和碎片化结构，就说明模型虽然在“看图”，但内部视觉证据可能已经变得不可靠。

作者用 **Laplacian energy** 衡量 visual attention 的高频结构。直观来说，它就像检测 attention map 里有没有很多“突兀变化”。论文发现：
**energy peak layer** 往往对应 hallucinated answer 开始形成的层；
**energy minimum layer** 反而经常短暂恢复 ground\-truth answer。
 所以，幻觉不是最后一层突然冒出来的，而是在中间层已经开始“预提交”错误答案，只是后面层把这个错误进一步放大。

**任务：**
 用于分析和缓解 MLLM 的视觉幻觉。作者提出 **LaSCD（Laplacian\-Spectral Contrastive Decoding）**，是一种 training\-free decoding 方法：在每一步生成时，先计算不同 decoder layer 上 visual attention 的 Laplacian energy；然后选择 **energy 最大层**作为 hallucination\-prone layer，选择 **energy 最小层**作为可能更接近 ground truth 的 layer；最后对 next\-token logits 做 closed\-form contrastive remapping，用最终层 logits 减去 peak layer 对错误 token 的偏好，必要时再加入 low\-energy layer 的修正信号。

实验覆盖 LLaVA\-1\.5、InstructBLIP、Qwen\-VL\-Chat、GLM\-4V\-9B、Video\-LLaVA 和 LLaVA\-Next\-Video，并在 POPE、CHAIR、HallusionBench、MME、MM\-Vet、LLaVA\-Bench 和 VideoHallucer 上评估。结果显示，LaSCD 能显著降低 hallucination，同时基本保持通用多模态能力。例如在 CHAIR 上，LaSCD 相比 vanilla LLaVA\-1\.5 明显降低 hallucination；在 POPE 上也提升了 average accuracy 和 F1；在 MME、MM\-Vet 等通用能力 benchmark 上没有像部分 decoding 方法那样明显牺牲性能。总体上，这篇文章把视觉幻觉分析从“模型有没有看图”推进到“模型的视觉注意力结构是否稳定、连贯、可信”。


<a id="d-023"></a>

### D-023. [Mechanistic Data Attribution: Tracing the Training Origins of Interpretable LLM Units](https://arxiv.org/pdf/2601.21996)

**发现问题：**
 现有 mechanistic interpretability 通常能告诉我们模型里有什么机制，比如 induction head、knowledge neuron、SAE feature 等，但大多是 **静态分析**：我们知道某个 head 在做 copy / pattern completion，却不知道它到底是被哪些训练数据“养出来”的。作者指出：如果只知道 circuit 存在，却不知道它的训练来源，就很难从数据层面控制模型内部机制的形成。

**Insight：**
 作者的核心想法是：可解释单元不只是模型内部自然出现的结构，它们也应该能追溯到具体训练样本。
 也就是说，某个 induction head 为什么会形成，可能不是神秘涌现，而是训练集中某些高影响数据长期提供了强信号。

作者提出 **Mechanistic Data Attribution（MDA）**：把 mechanistic interpretability 和 training data attribution 结合起来。
 传统 data attribution 问的是：“哪些训练样本影响了模型输出？”
 MDA 问的是：“哪些训练样本影响了某个可解释单元的形成和功能？”

直观来说，MDA 像是在给模型内部 circuit 做“溯源”：先定位一个可解释单元，比如 induction head；再用 influence function 计算训练样本对这个 head 功能指标的影响；最后通过删除或增强这些样本，验证它们是否真的因果影响 circuit emergence。

**任务：**
 用于追踪 LLM 内部可解释机制的训练数据来源，并通过数据干预控制这些机制的形成。作者在 Pythia 14M、31M、70M、160M 上分析 **induction heads** 和 **previous\-token heads**。方法上，先定义目标 head 的 probe function，比如 induction head 的 copy\-paste 能力指标；再把 influence function 限制在该 head 的参数子空间中，用 EK\-FAC 近似 Hessian inverse，从而计算每个训练样本对该 head 的机制影响。

实验发现：删除 top high\-influence samples 会显著延迟或削弱 induction head / previous\-token head 的形成；重复加入这些样本会加速 head emergence；而随机删除或随机增强几乎没有同样效果。这说明 MDA 找到的样本不是普通“高 loss 数据”，而是真的对特定机制有因果作用。

进一步分析显示，高影响样本通常包含大量 **重复结构**，比如 LaTeX、XML、代码、数据库条目、乱码式重复序列等。这些数据像“机制催化剂”，不断提供 copy / repetition 信号，促进 induction head 学会 pattern completion。作者还发现，这些高影响样本对不同 induction heads 有迁移性，说明它们驱动的是 induction mechanism 本身，而不是某个单独 head 的偶然现象。

更重要的是，作者用数据干预验证了 induction head 和 **in\-context learning（ICL）** 的因果联系：增强 induction head 形成时，ICL score 同步提升；削弱 induction head 时，ICL score 同步下降。这比以前只观察相关性更强，说明 induction head 很可能是 ICL 的重要底层机制之一。

最后，作者提出 **mechanistic data augmentation**：先用小模型 MDA 找到高影响样本，再让 LLM 提取其中的重复结构模式，自动生成合成训练数据。结果显示，这些 synthetic pattern 能跨模型规模加速 induction head 形成，甚至用 14M 模型发现的模式也能有效迁移到 160M。总体上，这篇文章把 mechanistic interpretability 从“解释模型内部有什么”推进到“追踪这些机制由哪些训练数据造成，并用数据主动调控模型内部机制”。




## I. 干预和转移：latent knowledge 能不能跨任务、跨模型、跨模态增强和迁移？

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

### I-002. [Imitating the Truth: Attention-aware Truth-Guided Enhancement for Hallucination Mitigation in Large Vision-Language Models](https://openreview.net/pdf?id=fzZAh18s9G)

**发现问题：**
 现有 LVLM 幻觉缓解方法通常只是粗粒度地增强视觉注意力或抑制文本先验，但作者发现：幻觉并不是简单因为“看图不够”，而是模型在不同层、不同阶段没有复现真实 token 的注意力模式。真实 token 和幻觉 token 在 image attention / text attention 上存在明显差异，而且这种差异是分阶段、分模型变化的。

**Insight：**
 作者的核心 insight 是：**让模型模仿真实 token 的注意力行为，可以减少幻觉。**
 具体来说，真实回答在某些阶段会更关注图像信息，在某些模型中也会更依赖文本上下文。因此，不应该统一增强某一种注意力，而应该根据不同阶段有针对性地调整 image attention 或 text attention，让生成过程更接近真实 token 的内部注意力模式。

**任务：**
 用于 **Large Vision\-Language Models 的 hallucination mitigation**，也就是减少图文模型生成与图像不一致的内容。实验任务包括 **COCO 图像描述、POPE 物体存在判断、MME 幻觉评测**，并在 LLaVA、MiniGPT\-4、mPLUG\-Owl2 等模型上验证。


<a id="i-003"></a>

### I-003. [When Safety Collides: Resolving Multi-Category Harmful Conflicts in Text-to-Image Diffusion via Adaptive Safety Guidance](https://arxiv.org/pdf/2602.20880)

**发现问题：**
 现有文生图安全方法通常把多个有害类别的关键词直接合并，比如 hate、sexual、violence、illegal 等一起用来做 safety guidance。作者发现这种做法不一定更安全，反而会产生 **harmful conflict**：不同有害类别的安全引导方向可能不一致、互相抵消，导致真正需要抑制的有害内容没有被有效压制。

**Insight：**
 安全引导不应该“所有有害类别一起上”，而应该在生成过程中动态判断当前 prompt / denoising state 最接近哪个有害类别，然后只沿着这个最相关类别的方向进行安全修正。也就是说，关键是 **category\-aligned safety guidance**，而不是 multi\-category averaging。

**任务DM safety：**
 用于 Text\-to\-Image diffusion model 的安全生成任务，目标是降低模型生成 sexual content、violence、hate、illegal activity 等有害图像的概率。方法可以插入到已有安全机制中，例如 latent\-space 的 SLD 和 text\-space 的 SAFREE，形成 CASG\+SLD / CASG\+SAFREE。




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

### I-005. [Parameter Importance is Not Static](https://arxiv.org/pdf/2604.14010)

**发现问题：**
 大模型在多任务 SFT 中容易出现任务干扰和灾难性遗忘。已有参数隔离方法会提前找出一批“重要参数”并固定冻结，但作者发现：参数重要性并不是静态的，而是会随着训练过程不断漂移。早期重要的参数后期可能不重要，后期新出现的关键参数又可能没有被保护，导致静态隔离失效。

**Insight：**
 作者提出一个直观想法：参数隔离不应该像“一把固定的锁”，而应该像“一面移动的盾牌”。模型训练到不同阶段，需要保护的关键参数不同。因此，EPI 通过在线梯度信号动态判断哪些参数当前最重要，并周期性更新保护 mask：锁住新出现的关键参数，释放已经过时的参数，从而同时保持稳定性和可塑性。

**任务：**
 用于缓解大语言模型多任务 SFT 中的任务冲突、灾难性遗忘和稳定性\-可塑性矛盾。作者提出 EPI，在训练中用平方梯度 EMA 估计参数重要性，结合层内归一化和动态 top\-p% mask 更新。实验覆盖 LLaMA\-3\-8B、Mistral\-7B、Qwen2\-7B、Gemma\-2\-9B，任务包括 GSM8K、CodeAlpaca、LogiQA、Alpaca 和 UltraChat。结果表明，EPI 相比普通 SFT、多阶段 SFT 和静态隔离都有更好表现。


<a id="i-006"></a>

### I-006. [Next Concept Prediction in Discrete Latent Space Leads to Stronger Language Models](https://arxiv.org/pdf/2602.08984)

**发现问题：**
 现有语言模型主要依赖 **Next Token Prediction**，也就是逐 token 预测下一个词。但作者认为，随着模型变大，单纯预测低层 token 可能不够高效，难以充分利用模型容量，也不利于学习更抽象、更长程的语义信息。

**Insight：**
 作者提出 **Next Concept Prediction（NCP）**：不要只预测下一个 token，而是先把多个 token 聚合成一个“概念”，再在离散 latent space 中预测下一个概念。这样模型相当于在生成 token 前先做更高层的语义规划。核心思想是：**更难、更抽象的预测目标可以迫使模型学习更强的语义表示和长程依赖。** 

**任务：**
 用于 **语言模型预训练与持续预训练**。作者提出的 **ConceptLM** 同时优化 Next Token Prediction 和 Next Concept Prediction，在 GPT\-2、Pythia 上从零训练，并在 Llama\-3\.1\-8B 上做持续预训练。实验覆盖语言建模和下游评测任务，包括 OpenWebText、Pile、WikiText、Lambada、ARC、WinoGrande、PIQA、HellaSwag、SciQ、RACE、MMLU、AGIEval、SQuAD 2\.0 等。




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

### I-009. [ACE-Merging: Data-Free Model Merging with Adaptive Covariance Estimation](https://arxiv.org/pdf/2603.02945)

**发现问题：**
 多个任务模型合并时，不同 expert 之间会互相干扰。尤其是在 **没有原始训练数据** 的 data\-free 场景下，现有方法大多只是直接在参数上做平均、剪枝或分解，缺少对任务差异的建模，所以合并后性能容易下降。

**Insight：**
 作者发现：虽然没有数据，但 **模型微调后的参数变化本身就包含任务信息**。也就是说，可以从每个 expert 的参数更新中估计它对应任务的特征结构，再根据这些结构更合理地合并模型，而不是简单平均。

**任务模型融合：**
 用于 **data\-free model merging**：把多个针对不同任务微调好的模型合成一个统一模型，不需要访问原始训练数据。实验包括视觉分类任务，以及 GPT\-2、RoBERTa、LLaMA\-3 上的语言理解、多语言、代码和数学推理任务。





<a id="i-010"></a>

### I-010. [CAN HETEROGENEOUS LANGUAGE MODELS BE FUSED?](https://arxiv.org/pdf/2604.01674)

**发现问题：**
 现有模型融合大多假设多个 expert 来自同一个 backbone，比如都是 Llama 或都是 Qwen。但现实中有用的专家模型往往来自不同模型家族，例如 Llama、Qwen、Mistral。不同架构之间层数、hidden size、模块结构和表示空间都不一致，直接做参数合并会失效，并且多个异构 expert 还会带来更强的冲突和噪声。

**Insight：**
 作者认为，异构模型不能直接按参数位置合并，而应该先找到不同模型中功能相似的模块，再在 adapter 空间进行知识迁移。同时，为了避免不同来源的 expert 互相干扰，需要在融合前过滤掉不可靠或冲突的信号。简单来说，就是 **先对齐结构，再去除冲突噪声，最后只把有用知识注入目标模型**。

**任务：**
 用于 **heterogeneous LLM fusion**：把来自不同模型家族的 expert adapters 融合到一个目标模型中，得到一个单一 fused adapter。实验主要包括 Llama、Qwen、Mistral 之间的跨架构融合，用在信息抽取任务，如 NER、RE、ET，也测试了 GLUE 上的跨任务泛化能力。


<a id="i-011"></a>

### I-011. [Adopting a Human Developmental Visual Diet Yields Robust and Shape-Based AI Vision](https://www.nature.com/articles/s42256-026-01228-6)

**发现问题：**
 现有 AI 视觉模型和人类视觉仍有明显差距：人类更依赖形状，AI 更依赖纹理；人类对模糊、噪声、遮挡等退化更鲁棒，而 AI 容易受图像退化和对抗攻击影响。作者认为问题不只是模型规模不够，而是 AI 的“视觉成长经历”和人类不同：AI 从一开始就看高清图像，而人类早期视觉是模糊、低对比、弱色彩的。

**Insight：**
 作者提出一个直观想法：让 AI 像婴儿一样“慢慢长大”。也就是在训练早期给模型看低清晰度、低对比、低色彩的图像，随着训练逐渐恢复到成人视觉水平。这个 **Developmental Visual Diet（DVD）** 不是简单加噪声或数据增强，而是按照人类视觉发育轨迹设计的训练课程。这样模型会先学整体形状和全局结构，而不是一开始就过度依赖局部纹理。

**任务：**
 用于训练更接近人类视觉的鲁棒 AI 视觉模型。作者把人类视觉发育中的三条曲线——视觉敏锐度、对比敏感度、色彩敏感度——转化为图像预处理课程，并用于训练 ResNet、AlexNet、VGG、MobileNet、ViT、DeiT 等模型。实验覆盖 mini\-ecoset、ecoset 和 ImageNet\-1K，评测包括 shape\-texture bias、IllusionBench 抽象形状识别、图像退化鲁棒性和黑盒/白盒对抗攻击。结果显示，DVD 显著提升形状偏置、抽象形状识别和鲁棒性，其中对比敏感度发展是最关键因素。


<a id="i-012"></a>

### I-012. [DGS-Net: Distillation-Guided Gradient Surgery for CLIP Fine-Tuning in AI-Generated Image Detection](https://arxiv.org/pdf/2511.13108)

**发现问题：**
 CLIP 本身有很强的通用视觉语义表示，适合做 AI 生成图像检测；但直接用 LoRA 等方式微调 CLIP，容易造成灾难性遗忘。结果是模型虽然更容易区分训练集上的 real/fake，但会破坏 CLIP 原本的表示几何结构，导致跨生成模型泛化变差。

**Insight：**
 作者的核心想法是：CLIP 里的知识不能简单“全保留”或“全删除”，而要在梯度空间里做手术。文本语义中有些方向会干扰伪造检测，需要抑制；冻结 CLIP 图像编码器中有些方向代表可迁移先验，需要保留。因此 DGS\-Net 把梯度分成 harmful 和 beneficial 两类：对 harmful 方向做正交投影去除，对 beneficial 方向做轻量对齐，让模型既学到 fake image artifact，又不丢掉 CLIP 的通用先验。

**任务：**
 用于提升 CLIP 微调在 AI 生成图像检测中的跨域泛化能力。作者提出 **DGS\-Net**，包含两个模块：**Orthogonal Suppression** 用文本分支梯度识别并去除有害语义方向；**Prior Alignment** 用冻结 CLIP 图像分支的有益梯度对齐可迁移先验。实验覆盖 AIGCDetectBench、AIGIBench 和 UniversalFakeDetect，测试 50 种生成模型，包括 GAN、diffusion、Deepfake、DALLE、FLUX、Midjourney、SDXL 等。结果显示，DGS\-Net 在检测准确率、AP、JPEG/blur 鲁棒性和表示几何保持上都优于现有方法。


<a id="i-013"></a>

### I-013. [PsychAdapter: Adapting LLMs to Reflect Traits, Personality, and Mental Health](https://www.nature.com/articles/s44387-026-00071-9) (子刊 npj AI)

**发现问题：**
 现有 LLM 生成的文本通常像“平均人”的语言，缺少个体差异，难以稳定体现不同人格、心理健康状态或人口学特征。单纯靠 prompt 控制人格也比较粗糙，只能使用离散描述，难以精细控制连续心理特质，比如外向性高低、抑郁程度或生活满意度。

**Insight：**
 作者提出一个直观想法：不要只在 prompt 里告诉模型“你很外向/你很抑郁”，而是把心理特质向量直接注入 Transformer 的每一层。PsychAdapter 像一个“心理旋钮”，把 Big Five、抑郁、生活满意度、年龄等连续分数映射到隐藏层空间，让模型在生成每个 token 时都受到这些心理变量影响。

**任务：**
 用于生成能反映指定人格、心理健康状态和人口学特征的文本。作者提出 **PsychAdapter**，在 GPT\-2、Gemma\-2B、LLaMA3 上加入轻量 adapter，将连续心理分数通过层级投影注入 transformer，并结合 LoRA 训练。训练数据来自博客和 Twitter/X，并用心理语言模型给文本估计 Big Five、抑郁、生活满意度和年龄分数。实验显示，专家能以 **87\.3%** 准确率识别 Big Five 特质，以 **96\.7%** 准确率识别抑郁和生活满意度；模型还能控制多维人格组合、细粒度人格水平，并泛化到不同文本域和不同 LLM。


<a id="i-014"></a>

### I-014. [Multilingual Safety Alignment via Self-Distillation](https://arxiv.org/pdf/2605.02971)

**发现问题：**
 LLM 在英文等高资源语言中通常比较安全，但在低资源语言中容易被 jailbreak。已有多语言安全对齐方法通常需要为每种语言准备高质量安全回复数据，成本高、难扩展。作者发现：模型其实已经在高资源语言中具备安全能力，关键问题是如何把这种能力转移到低资源语言。

**Insight：**
 作者提出一个直观想法：让模型“自己教自己”。同一个 LLM 同时扮演 **teacher** 和 **student**：teacher 看到英文 query 和 CoT 指令，用英文进行安全判断，再用目标低资源语言回答；student 只看到低资源语言 query。通过自蒸馏，student 学会把英文中的安全判断能力迁移到低资源语言，而不需要任何人工安全回复数据。

**任务：**
 用于提升 LLM 在多语言 jailbreak 场景下的安全对齐能力。作者提出 **Multilingual Self\-Distillation（MSD）**，包括 **on\-policy MSD** 和 **off\-policy MSD** 两种版本，并设计 **Dual\-Perspective Safety Weighting（DPSW）**，对拒答、风险判断等 safety\-critical tokens 加大蒸馏权重。实验覆盖 Qwen\-2\.5\-7B、Qwen\-3\-8B、LLaMA\-2\-7B、LLaMA\-3\-8B，评测 MultiJail、PKU\-SafeRLHF、MMMLU、MGSM，语言包括英文、中文、阿拉伯语、孟加拉语、斯瓦希里语、爪哇语等。结果显示，MSD 能显著降低多语言攻击成功率，泛化到未见语言，同时基本保持通用能力和数学推理能力。


<a id="i-015"></a>

### I-015. [Manifold Steering Reveals the Shared Geometry of Neural Network Representation and Behavior](https://arxiv.org/pdf/2605.05115)

**发现问题：**
 现有 activation steering 通常默认表示空间是平的，只要找到一个方向并线性相加就能控制行为。但作者发现：很多概念在模型内部不是一条直线，而是弯曲的 manifold。线性 steering 会直接切过这些弯曲结构的内部，导致输出“跳跃”、不自然、甚至崩坏。

**Insight：**
 作者提出一个直观想法：控制模型行为的关键不是“找对方向”，而是“走对路径”。如果模型内部把 weekdays、months、letters、ages 等概念组织成圆环、曲线或曲面，那么 steering 也应该沿着这些几何结构走，而不是走直线。也就是说，activation space 里的几何结构和 behavior space 里的输出分布结构其实是同一个概念空间的两种投影。

**任务：**
 用于验证神经网络内部表示几何是否因果地控制模型行为，并提出更自然的 steering 方法。作者先拟合 **activation manifold** 和 **behavior manifold**，发现二者在 weekdays、months、letters、ages 上近似等距；再比较 **linear steering** 和 **manifold steering**，结果显示 manifold steering 能让输出概率按概念顺序平滑转移，而 linear steering 会出现非相邻概念之间的“teleportation”。实验覆盖 Llama 3\.1 8B 的时间、字母、年龄推理任务，以及 in\-context learning 的 grid / cylinder 图结构任务，并扩展到 Mountain Car 视觉 world model。结果说明：尊重 activation manifold 的干预能产生更自然、更可控的行为轨迹。


<a id="i-016"></a>

### I-016. [Don’t Retrain—Align](https://arxiv.org/pdf/2605.06885)

**发现问题：**
 Diffusion LM 有非顺序生成、双向编辑等优势，但从头训练成本很高。已有 AR→DLM 转换方法通常只是复用 AR 参数，再继续做 denoising training；但作者认为这些方法没有显式保护 AR 模型已经学到的内部表示结构，导致 DLM 仍在重复学习语言表示。

**Insight：**
 作者提出一个直观想法：AR 和 DLM 的区别主要是“生成路径”不同，而不是“语言知识”不同。AR 预训练已经学到了语义和句法表示，DLM 不应该重新学一遍语言，而应该对齐并复用这些表示。也就是说，把 AR 转成 DLM 时，不是 **retrain representation**，而是 **align representation \+ adapt decoding mechanism**。

**任务：**
 用于高效地把 autoregressive LM 转换成 masked diffusion LM。作者提出 **REPR\-ALIGN**：把 AR 模型冻结作为 teacher，把同架构 DLM student 初始化为 AR 权重，只把 causal attention 改成 bidirectional attention；训练时同时优化 masked denoising loss，并用 layer\-wise cosine loss 对齐 DLM 和 frozen AR 的 hidden states。实验基于 Qwen3\-0\.6B、1\.7B、4B，在 Nemotron\-SFT\-Code 上训练，评测 HumanEval、HumanEval\+、MBPP、MBPP\+。结果显示，REPR\-ALIGN 能加速 AR→DLM 转换，在 HumanEval pass@10 上显著提升，低数据场景也有效，并且冻结 embedding / MLP 后还能提升训练吞吐。


<a id="i-017"></a>

### I-017. [Correct When Paired, Wrong When Split](https://github.com/TingchaoFu/DECODE/blob/main/paper.pdf)

**发现问题：**
 现有 MLLM 知识编辑方法通常只看图文配对输入下答案是否改对。但作者发现：模型在 **text\-image paired query** 下能回答新知识，一旦拆成 **text\-only** 或 **image\-only grounding** 查询，就可能回到旧答案。作者称这个现象为 **editing decoupling failure**。

**Insight：**
 作者提出一个直观解释：MLLM 里的同一个实体知识，并不是存在一个统一的“实体知识库”里，而是被分散存进了不同模态通路。图像触发时走一组 visual\-aware neurons，文本触发时走另一组 text\-aware neurons。传统方法只在图文输入上编辑，实际主要改到了视觉/多模态通路，所以文本通路里还保留旧知识，导致“配对时正确，拆开时错误”。

**任务：**
 用于解决多模态大模型知识编辑中的跨模态不一致问题。作者提出 **DECODE**，先根据 text\-only、image\-trigger、standard multimodal 三种查询计算 neuron contribution score，定位 **text neurons** 和 **visual neurons**；再用 two\-stream editing 分别给两组 FFN neurons 加 learnable offsets，并用 target loss 更新目标知识、用 locality loss 保持无关知识不变。实验覆盖 InstructBLIP、LLaVA\-v1\.5、Qwen\-VL，并基于 MMKE 构造 modality\-split 测试集。结果显示，DECODE 能同时提升 text\-only 和 multimodal reliability / generality，并比 FT、SERAC、IKE、FiNE 更好地缓解 editing decoupling failure。


<a id="i-018"></a>

### I-018. [Towards the Explainability of Protein Language Models](https://arxiv.org/pdf/2506.19532) （子刊）

**发现问题：**
 蛋白质语言模型已经能做结构预测、功能预测和蛋白设计，但它们为什么能做对、学到了什么生物规律，仍然像黑盒。作者发现：现有 XAI 方法大多只用来验证模型是否捕捉了已知生物模式，还没有真正充分用于发现新的蛋白质机制。

**Insight：**
 作者提出一个清晰框架：解释蛋白质模型时，可以从四个入口看模型——训练数据、输入序列、模型内部组件、输入输出变化。比如看哪些训练蛋白影响预测，看哪些氨基酸贡献最大，看 attention head / neuron / SAE feature 是否对应生物概念，或者通过突变输入观察输出怎么变。更重要的是，XAI 不应只当“验算器”，还可以成为模型压缩的 **Engineer**、控制生成的 **Coach**，甚至未来帮助人类发现新生物规律的 **Teacher**。

**任务：**
 用于综述蛋白质语言模型的可解释性方法和未来研究方向。文章总结了 influence functions、embedding space analysis、gradient\-based attribution、attention analysis、LRP、neuron activation、SAE、SHAP、LIME、counterfactuals 和 adversarial probing 等方法，并归纳 XAI 在蛋白研究中的五种角色：**Evaluator、Multitasker、Engineer、Coach、Teacher**。作者指出目前主流工作仍停留在 Evaluator 阶段，未来需要更可靠的 benchmark、faithfulness evaluation、人类友好的可视化工具，以及 wet\-lab validation，才能让 XAI 真正从解释模型走向发现蛋白折叠、酶催化和进化规律。




<a id="i-019"></a>

### I-019. [Turning Drift into Constraint: Robust Reasoning Alignment in Non-Stationary Multi-Stream Environments](https://arxiv.org/pdf/2510.04142)

**发现问题：**
 多教师 / 多模型蒸馏通常假设不同 source MLLM 的推理都是有用知识，直接把它们融合给 student 学。但作者发现：不同大模型的推理分布并不稳定，会因为预训练偏差、架构差异和表达风格不同产生 **concept drift**。如果 student 直接模仿这些不一致的推理轨迹，就会把多个老师的偏差一起学进去，导致幻觉、语义矛盾和诊断推理错误。

**Insight：**
 作者的核心想法是：模型之间的分歧不一定是噪声，而可以变成“负约束”。也就是说，不要简单平均多个老师的答案，而是先找出它们共同认可的 **consensus reasoning**，再把彼此冲突、漂移的推理轨迹当作模型应该避免的区域。这样 student 学到的不是某个老师的风格，而是在多个老师分歧中提炼出的稳定推理边界。

**任务：**
 用于在非平稳、多源 MLLM 环境下做鲁棒推理对齐。作者提出 **APO（Autonomous Preference Optimization）**：第一阶段用多个 source MLLM 的推理轨迹做 supervised bootstrapping，让 Qwen2\.5\-VL\-7B student 获得多个老师的能力覆盖；第二阶段生成 consensus trajectory 作为正样本，把原始冲突推理作为 negative constraints，用 multi\-negative Plackett\-Luce preference loss 进行优化。作者还构建 **CXR\-MAX**，包含来自 GPT\-5、Gemini\-2\.5、Claude Sonnet\-4、Qwen\-VL\-Max、Grok\-4、GLM\-4\.5V、Moonshot 等 7 个 MLLM 的 **170,982** 条胸片推理轨迹。实验在 MIMIC\-CXR、MS\-CXR\-T、Open\-I、ChestXray14、CheXpert、ChestXDet10 上验证，结果显示 7B student 在只用 10% 数据且不使用放射科报告训练的情况下，平均准确率超过多个大型 source MLLM 和现有胸片诊断方法。


<a id="i-020"></a>

### I-020. [Orthogonal Model Merging](https://arxiv.org/pdf/2602.05943)

**发现问题：**
 现有 model merging 方法大多直接在欧氏空间里做 task vector 加法或平均，比如把多个 finetuned model 的参数差值加到 base model 上。但作者认为这样会破坏预训练权重原本的几何结构，尤其是 neuron 之间的角度关系 / hyperspherical energy，导致任务之间参数冲突、能力互相干扰和 catastrophic forgetting。

**Insight：**
 作者的核心想法是：模型微调不一定只应该看成“参数加法”，也可以看成对 base weight 做了一种“旋转”。如果多个任务的能力是不同方向的旋转，那么合并时就不应该在平直的欧氏空间里硬加，而应该在 **orthogonal group** 这个流形上合并。这样可以保留权重的几何结构，减少不同任务更新之间的破坏性干扰。

**任务：**
 用于把多个 task\-specific finetuned LLM / MLLM 合并成一个统一模型。作者提出 **OrthoMerge**：对于 OFT 微调模型，先把每个任务的 orthogonal matrix 映射到 Lie algebra `so(d)`，在那里做 **magnitude\-corrected averaging**，避免不同任务方向相互抵消导致更新强度变弱，再用 Cayley transform 映射回 orthogonal group。对于 LoRA / full finetuning 等非 OFT 模型，作者提出 **Orthogonal\-Residual Decoupling**：先通过 Orthogonal Procrustes problem 提取每个专家模型中的 orthogonal component，在流形上合并；剩余 residual component 继续用 TA、TIES、TSV\-M 等传统方法合并。实验覆盖 Llama\-3\.1\-8B、Qwen2\.5\-3B、Llama\-3\.2\-3B 和 Qwen2\.5\-VL\-7B\-Instruct，任务包括数学、代码、科学问答、常识问答、社交推理、多语言、安全、OCR、空间理解和医学多模态 QA。结果显示，OrthoMerge 能提升多任务合并性能，并更好保留 base model 的通用能力。


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







## E. 评估与校准：能不能利用 latent knowledge 控制模型行为，并评估安全性和可靠性？


<a id="e-001"></a>

### E-001. [Self-Distilled Reasoner: On-Policy Self-Distillation for Large Language Models](https://arxiv.org/pdf/2601.18734)

**发现问题：**
 现有提升 LLM 推理能力的方法主要有 SFT、RLVR/GRPO、knowledge distillation，但各有问题：SFT 是 off\-policy，容易和推理时的生成分布不一致；GRPO 依赖最终答案奖励，信号稀疏、采样成本高；on\-policy distillation 虽然有 dense token\-level feedback，但通常需要一个额外的大 teacher model。

**Insight：**
 作者的核心 insight 是：**一个足够强的 LLM 可以在看到标准答案或参考 CoT 后，充当自己的 teacher 来指导 weaker self。**
 也就是说，同一个模型构造两个角色：student 只看问题并生成自己的推理轨迹；teacher 看问题 \+ ground\-truth solution / CoT，然后在 student 自己生成的轨迹上提供 token\-level 分布监督。这样既保留 on\-policy 训练，又不需要外部 teacher。

**任务：**
 用于 **LLM mathematical reasoning post\-training**，目标是在数学推理任务上提升模型能力。作者在 Qwen3\-1\.7B、4B、8B 上实验，使用 OpenThoughts 数学推理数据训练，并在 AIME 2024、AIME 2025、HMMT 2025 上评测。结果显示 OPSD 比 SFT 更好，和 GRPO 相当或更优，但 token efficiency 明显更高。

<a id="e-002"></a>

### E-002. [Language Models (Mostly) Know What They Know](https://arxiv.org/pdf/2207.05221) （有点老）

**发现问题：**
 现有语言模型经常会“答错但很自信”，因此作者关注一个问题：模型是否知道自己什么时候知道、什么时候不知道？也就是模型能不能判断自己的答案是否正确，以及能不能预测自己是否有能力回答某个问题。

**Insight：**
 作者发现：**大模型在合适的提问格式下，通常具备一定的自我评估能力。**
 例如，让模型先生成答案，再问它“这个答案是否正确”，模型给出的 **P\(True\)** 可以较好地区分正确和错误答案；如果给模型看多个候选答案，它的判断会更准。进一步地，训练模型预测 **P\(IK\)**，也就是“我是否知道这个问题的答案”，模型也能学到一定的自我知识，并且在看到相关资料或提示时，P\(IK\) 会合理升高。

**任务：**
 用于 **语言模型的校准、自我评估和自我知识建模**。实验包括多选题校准、True/False 判断、开放式生成答案的自我验证，以及训练模型预测自己是否能答对问题。任务覆盖 **BIG\-Bench、MMLU、TruthfulQA、TriviaQA、Lambada、GSM8k、HumanEval、Arithmetic** 等数据集。




<a id="e-003"></a>

### E-003. [Domain-Filtered Knowledge Graphs from Sparse Autoencoder Features](https://arxiv.org/pdf/2604.23829)

**发现问题：**
 SAE 可以从模型内部提取大量可解释 feature，但这些 feature 通常只是一个“扁平清单”。里面混有很多通用、格式、弱相关特征，真正的领域概念被分散在不同 feature 中，而且 feature 之间缺少关系结构，导致很难看出模型内部到底如何组织某个领域知识。

**Insight：**
 作者的核心想法是：不要只看单个 SAE feature，而是把它们组织成一个“模型内部知识图谱”。先通过对比过滤找出真正属于某个领域的概念 feature，再用图结构连接它们：一张图表示概念在语料中如何共现，另一张图表示概念如何通过 transcoder 在层间流动。这样，SAE feature 就从零散的“词条表”变成了可浏览、可解释的知识地图。

**任务：**
 用于把大规模 SAE feature 转换成领域过滤后的内部知识图谱，帮助分析模型内部知识结构和局部推理机制。作者在生物教材语料上，用 Gemma Scope residual SAEs 和 layer\-20 到 layer\-21 的 transcoder，先通过 contrastive filtering 得到 biology\-specific concept universe，再构建多粒度 co\-occurrence graph 和 transcoder mechanism graph，并自动生成边标签。实验显示，这些图能恢复教材章节和小节结构，也能把一句话中上千个激活 feature 压缩成可读的局部机制图。

<a id="e-004"></a>

### E-004. [LLM DNA: Tracing Model Evolution via Functional Representations](https://openreview.net/pdf?id=UIxHaAqFqQ)

**发现问题：**
 现在开源 LLM 数量非常多，但模型之间到底是不是同源、是否经过微调/蒸馏/改造，很多时候文档并不清楚。已有方法要么依赖具体任务，要么要求固定模型集合，要么受 tokenizer 和架构限制，难以统一分析不同 LLM 的“血缘关系”。

**Insight：**
 作者提出一个直观类比：每个 LLM 都可以有自己的“DNA”。这个 DNA 不是参数本身，而是模型在一组输入上的**功能行为压缩表示**。如果两个模型输出行为相似，它们的 DNA 就接近；如果一个模型由另一个模型微调或蒸馏而来，它的 DNA 也应该保留相似模式。这样就可以像生物进化树一样，追踪 LLM 家族之间的演化关系。

**任务：**
 用于识别 LLM 之间的功能相似性、潜在血缘关系和演化路径。作者提出 **RepTrace**，先给不同 LLM 输入一组 prompts，收集模型回复，再用 sentence embedding 把回复转成语义向量，拼接后用随机高斯投影压缩成低维 **LLM DNA**。实验覆盖 305 个 Hugging Face LLM，包括 Qwen、Llama、Gemma、Pythia、Flan\-T5 等。结果显示，LLM DNA 能检测已知和未记录的模型关系，支持 training\-free model routing，并能构建 LLM phylogenetic tree，反映从 encoder\-decoder 到 decoder\-only、从旧模型到新模型的演化趋势。


<a id="e-005"></a>

### E-005. [Locate, Steer, and Improve: A Practical Survey of Actionable Mechanistic Interpretability in LLMs](https://arxiv.org/pdf/2601.14004)

**发现问题：**
 现有 Mechanistic Interpretability 综述大多把 MI 当作“观察工具”，主要总结模型内部有哪些机制，但缺少一个清晰框架说明：如何先定位关键内部结构，再干预这些结构，最后真正提升模型能力、安全性或效率。也就是说，MI 还没有被系统整理成一套可操作的“模型改造流程”。

**Insight：**
 作者提出一个非常直观的三步框架：**Locate → Steer → Improve**。先找到模型内部真正负责某种行为的对象，比如 residual stream、attention head、FFN neuron、SAE feature 或 circuit；再用不同方式控制它们，比如激活放大/抑制、参数局部优化、steering vector；最后把这种控制用于实际改进模型，比如提升安全性、减少偏见、增强推理、多语言能力、知识编辑，或者加速训练和推理。

**任务：**
 用于系统总结“可行动的机制可解释性”如何从内部分析走向模型干预和优化。文章先定义 LLM 中的核心可解释对象，然后归纳六类定位方法：**Magnitude Analysis、Causal Attribution、Gradient Detection、Probing、Vocabulary Projection、Circuit Discovery**；再总结三类干预方法：**Amplitude Manipulation、Targeted Optimization、Vector Arithmetic**。最后按应用目标整理为三大方向：**Improve Alignment、Improve Capability、Improve Efficiency**，覆盖安全可靠性、公平性、人格角色、多语言、知识管理、逻辑推理、高效训练和高效推理等场景。总体上，这篇综述把 MI 从“看懂模型”推进到“定位、操控并改进模型”。


<a id="e-006"></a>

### E-006. [From Parameter Dynamics to Risk Scoring](https://arxiv.org/pdf/2605.04572)

**发现问题：**
 LLM 安全对微调非常脆弱，甚至用少量看似无害的 benign samples 做 SFT，也可能破坏原来的安全对齐。已有方法多是比较微调前后的参数或表示变化，但忽略了训练过程中的动态轨迹。作者发现：安全退化不是突然发生的，而是参数在微调过程中逐步向 **danger direction** 累积漂移，最终走出安全区域。

**Insight：**
 作者提出一个直观想法：每个训练样本都会把模型参数“推一小步”，关键是这一步更靠近安全方向，还是危险方向。高风险样本并不一定内容有毒，但它诱导的梯度更新会更像 unsafe model 的参数变化。因此，可以通过比较样本更新在 **danger direction** 和 **safety direction** 上的投影差，给每个 benign sample 打一个连续风险分数。

**任务：**
 用于量化微调数据中每个样本对 LLM 安全退化的风险。作者提出 **SQSD**，先构造 safety direction 和 danger direction，再计算单个样本诱导的 LoRA 参数更新，并用
**danger projection − safety projection** 得到样本级风险分数。实验覆盖 Qwen3\-8B、Llama\-3\.1\-8B\-Instruct、Llama\-2\-7B\-Chat，以及 Dolly、Alpaca 数据集；评估包括 CategoricalHarmfulQA、AdvBench、HEx\-PHI。结果显示，SQSD 能稳定区分高风险和低风险样本，并且风险排序可以跨模型架构、模型规模和 LoRA / Full fine\-tuning 迁移。


<a id="e-007"></a>

### E-007. [Learning Uncertainty from Sequential Internal Dispersion in Large Language Models](https://arxiv.org/pdf/2604.15741v1)

**发现问题：**
 现有幻觉检测 / 不确定性估计方法要么依赖多次采样，计算开销大；要么只看最后一个 token 或平均 hidden states，容易丢失序列中的关键信号。作者发现：模型生成错误答案时，不确定性会体现在不同层 hidden states 的“分散程度”变化中，而不是简单满足某种固定的层间变化模式。

**Insight：**
 作者提出一个直观想法：如果模型对某个 token “拿不准”，它内部不同层的表示会更分散、更不稳定。与其只看最后一层或最后一个 token，不如沿着整个生成序列，观察每个 token 在各层 hidden states 中的 dispersion。SIVR 就像在读模型生成过程中的“内心波动曲线”：哪里表示突然发散，哪里就可能对应事实错误或幻觉。

**任务：**
 用于检测 LLM 生成内容是否存在幻觉，并估计回答的不确定性。作者提出 **SIVR**，对每个生成 token 提取跨层 hidden states，并计算三类内部方差信号：**covariance determinant** 表示整体分散程度，**circular variance** 表示方向分歧，**token entropy** 表示输出概率不确定性；再用轻量 Transformer encoder 聚合完整 token 序列，预测回答是否错误。实验覆盖 Llama\-3\.2\-3B、Llama\-3\.1\-8B、Ministral\-8B、Qwen\-3\-4B/14B，任务包括 TriviaQA、SciQ、MedMCQA、MGSM、MATH、MMLU、CommonsenseQA 和 fact\-checking。结果显示，SIVR 相比 logit\-based、sampling\-based 和 hidden\-state probing 方法整体表现更好，并且在 OOD 设置和小训练集下更稳健。




<a id="e-008"></a>

### E-008. [Black-Box Detection of LLM-Generated Text Using Generalized Jensen Shannon Divergence](https://arxiv.org/pdf/2510.07500)

**发现问题：**
 LLM 生成文本越来越接近人类文本，传统检测方法要么需要训练分类器、迁移性差；要么依赖 likelihood / entropy 等全局统计，在黑盒代理模型不匹配时不稳定；还有一些方法需要对每个输入做扰动或重生成，计算成本很高。作者发现：更稳定的信号不在单个 token 的概率大小，而在 token surprisal 的动态变化模式里。

**Insight：**
 作者提出一个直观想法：不要只看一句话“整体像不像 AI 写的”，而要看它的“惊讶节奏”。LLM 生成文本常出现一种 **recovery pattern**：遇到高 surprisal token 后，很快回到低 surprisal、可预测 token。SurpMark 把 token surprisal 离散成几个状态，再观察这些状态如何转移，就像给文本画一条“可预测性心电图”。人类文本和机器文本的转移节奏不同，因此可以用这个动态模式区分二者。

**任务：**
 用于黑盒检测 LLM 生成文本。作者提出 **SurpMark**：先用一个 proxy LM 计算文本 token\-level surprisal，再用 k\-means 把 surprisal 分成若干状态，构建一阶 Markov transition matrix；离线阶段分别构建 human / machine reference transition matrices，在线阶段对测试文本计算 transition matrix，并用 **Generalized Jensen\-Shannon Divergence（GJS）** 比较它更接近 human 还是 machine。实验覆盖 XSum、WritingPrompts、SQuAD、WMT19、HC3、DetectRL、DAIGT、Dolly，生成模型包括 GPT\-2XL、GPT\-J、GPT\-NeoX、OPT、Llama、Gemma、Gemini、GPT\-4\.1\-mini、GPT\-5\-Chat。结果显示 SurpMark 在黑盒、跨域、混合生成器、非英文、改写攻击和低 FPR 场景下都优于或接近强基线，并且不需要每个输入重新生成样本，推理成本更低。


<a id="e-009"></a>

### E-009. [Depression and Anxiety Characterization and Detection with Multimodal Deep Learning](https://www.nature.com/articles/s44220-026-00632-6) (子刊)

**发现问题：**
 抑郁和焦虑很难只靠单一数据判断：文本可能受文化表达影响，生理信号可能把焦虑和普通压力混淆，临床量表和访谈又成本高、难大规模使用。作者总结发现：多模态深度学习虽然能融合文本、音频、视频、生理信号和脑影像，但目前仍受限于数据规模小、模态缺失、数据偏差、隐私限制和临床验证不足。

**Insight：**
 作者的核心观点是：心理疾病不是只藏在一句话、一张脑图或一个生理指标里，而是分散在“脑—行为—环境”的多层信号中。多模态深度学习就像把多个观察窗口合在一起：文本看语言情绪，音频看语速和音调，视频看表情和姿态，EEG/fMRI 看神经活动，问卷和临床数据提供诊断背景。只有把这些信号对齐和融合，才更可能捕捉抑郁和焦虑的真实状态。

**任务：**
 用于综述多模态深度学习在抑郁和焦虑表征、筛查和诊断中的进展。文章总结了 CNN、RNN/LSTM、Transformer、GNN 在不同模态中的作用，并比较 early / intermediate / late fusion 等融合策略；覆盖 DAIC\-WOZ、E\-DAIC、D\-vlog、LMVD、MODMA、REST\-meta\-MDD、MMPsy、ENIGMA 等数据集。作者还总结未来方向：构建更大规模和跨文化数据集，处理缺失模态和数据偏差，利用 federated learning 解决隐私与数据孤岛问题，引入 foundation models / transfer learning / contrastive fusion / explainable AI，并通过临床试验验证模型可靠性。




<a id="e-010"></a>

### E-010. [Restoring Exploration after Post-Training: Latent Exploration Decoding for Large Reasoning Models](https://arxiv.org/pdf/2602.01698)

**发现问题：**
 现在很多推理模型经过 RL post\-training 后，pass@1 变强了，但探索能力反而塌缩了。以前提高 sampling temperature 可以让模型生成更多不同解法，从而提升 pass@n；但作者发现，在 MiMo\-7B\-RL、Qwen3\-Thinking 这类新 LRMs 上，提高 temperature 不但不能提升 pass@n，有时还会降低性能。原因是 RL 后训练把最终层 posterior 压得太尖锐、低熵，模型过早确信某条推理路径，导致采样也采不出真正多样的解法。

**Insight：**
 作者的关键洞察是：探索能力并没有完全消失，而是藏在中间层里。最终层的概率分布已经很“自信”，几乎接近 one\-hot；但中间层 hidden states 解码出来的 latent posterior 仍然保留较高 entropy，说明模型内部还存在多个可能的推理方向。
 所以，与其在最终层强行调 temperature，不如去中间层找还没有完全收敛的候选路径。LED 就像是在模型“最后拍板”之前，回头看看中间层还在犹豫什么，然后选择最有探索价值的分布来采样。

**任务：**
 用于恢复 RL\-post\-trained reasoning model 的测试时探索能力，并提升 pass@1 / pass@n。作者提出 **Latent Exploration Decoding（LED）**：先用 early\-exit 方法把中间层 hidden states 通过 LM head 解码成 latent posteriors；再只保留最终层 top\-k token，避免采到无意义 token；然后从最终层往中间层做 cumulative aggregation，选择 entropy 最大的 depth configuration 作为 exploration posterior；最后根据最终层置信度，在 exploitation 和 exploration 之间自适应切换，并且只在 **DeepThink 阶段**使用探索。实验覆盖 Qwen3\-4B\-Thinking、MiMo\-7B\-RL、Qwen3\-30B\-A3B\-Thinking、DeepSeek\-R1\-Distill\-Llama\-8B、QwQ\-32B，任务包括 AIME2024/2025、GSM8K、MATH\-500、GPQA\-Diamond、LiveCodeBench。结果显示 LED 平均提升 pass@1 和 pass@16，并且几乎不增加生成长度；作为 GRPO rollout 策略时，还能带来更快 reward 增长和更高最终性能。


<a id="e-011"></a>

### E-011. [Information Flow Reveals When to Trust Language Models](https://openreview.net/pdf?id=gJi0Hp7nLI)

**发现问题：**
 LLM 在 RAG 问答里经常会“看起来很自信地猜答案”，但现有不确定性评估方法大多只看输出概率、entropy、多次采样一致性，或者只看检索文档和问题是否相关。作者认为这些方法不够，因为它们没有真正看模型内部是怎么使用 context 的。也就是说，模型回答对不对，不只取决于 context 有没有答案，还取决于模型内部的信息流是否真的从关键 context token 流向了最终答案。

**Insight：**
 作者的核心直觉是：可信回答应该有清晰的信息来源。
 如果模型生成答案时，内部 attention 信息流主要来自 context 中真正相关的 token，那么这个回答更可信；如果信息流很分散，或者重点 token 和外部 relevance 判断对不上，就说明模型可能在猜。
 所以，与其只看最终 logits，不如打开 Transformer 内部，追踪哪些 context token 真正贡献到了最后生成 token。

**任务：**
 用于评估 RAG 场景下 LLM 回答是否可靠，并输出 calibrated confidence。作者提出两个内部信息流指标：**Emergence Order** 和 **Contribution Layout**。前者表示哪些输入 token 更早进入 principal information flow，越早说明越重要；后者统计每个 context token 通过所有 admissible paths 对最终输出的贡献。然后作者提出 **simulatability**，衡量模型内部重要 token 排序和 reranker / Shapley 得到的 relevance layout 是否一致；再提出 **concentration**，衡量贡献是否集中在少数关键 token 上。最后把这些特征和 context relevance score 一起输入 XGBoost calibrator，预测回答可信度。实验在 SQuAD2\.0、HotpotQA、MS MARCO 上进行，模型包括 LLaMA\-3\.2\-3B\-Instruct 和 Gemma\-3\-4B\-it。结果显示该方法在 AUROC、AUPRC、ECE 和相关性指标上优于 PPL、P\(True\)、Regular Entropy、Semantic Entropy、KnowingMore、Utility Ranker 等基线；同时消融实验显示，删掉信息流排名靠前的 context token 会显著破坏原本正确的回答，说明这些内部信息流确实具有因果意义。


<a id="e-012"></a>

### E-012. [Tracing Uncertainty in Language Model “Reasoning”](https://arxiv.org/pdf/2605.07776)

**发现问题：**
 现在很多 LLM 会生成很长的 CoT / reasoning trace，看起来像是在“推理”，但我们并不清楚这些中间 token 什么时候可靠、什么时候已经走偏。已有方法通常把整条 trace 压成一个分数，比如 Self\-Certainty 或最终答案置信度，这会丢掉生成过程中的动态信息。作者发现：正确和错误的 reasoning trace 在表面文本上可能都很像，但它们的 **uncertainty 随时间变化的轨迹** 是不一样的。

**Insight：**
 作者的核心直觉是：不要只看模型最后答了什么，而要看它在“思考过程中”是否越来越确定。
 如果一条 trace 是正确的，模型的不确定性通常会更明显地下降；如果一条 trace 是错误的，不确定性下降得更慢、更不稳定，甚至可能在关键步骤出现异常峰值。
 也就是说，reasoning trace 可以看成一个 **uncertainty time series**：每生成一个 token，就记录一次模型当前的 uncertainty。这个轨迹本身能暴露模型是否正在走向正确答案。

**任务：**
 用于判断 LLM / reasoning model 的推理轨迹最终是否会得到正确答案，并分析错误推理在哪里开始出现。作者在每个 token 位置计算三类 uncertainty：**distributional uncertainty**（整个词表 entropy）、**committal uncertainty**（模型对当前选中 token 是否真的 committed）、**epistemic uncertainty**（基于 gradient norm 估计模型是否熟悉当前状态）。同时区分两条通道：**trace uncertainty** 看模型对下一个生成 token 的不确定性，**answer uncertainty** 看模型对最终答案的不确定性。然后从每条 uncertainty trace 中提取 early / middle / late mean、slope、linearity 等特征，组成 **uncertainty trace profile**，用 Logistic Regression / Gradient Boosting 预测最终答案是否正确。实验覆盖 Llama\-3\.1\-8B、Llama\-3\.2\-1B、Qwen2\.5\-0\.5B、DeepSeek\-R1\-Distill\-Qwen\-1\.5B、Qwen3\-0\.6B，在 GSM8K 和 ProntoQA 上评测。结果显示，该方法最高 AUROC 达到 **0\.807**，优于 Self\-Certainty 和 CRV；只看前几百个 token 也能达到约 **0\.801 AUROC**，说明错误可以在生成早期被检测出来。总体上，这篇文章把 CoT 分析从“看文本内容对不对”推进到“看不确定性动态是否健康”。




<a id="e-013"></a>

### E-013. [Towards Generation-Efficient Uncertainty Estimation in Large Language Models](https://arxiv.org/pdf/2605.06053)

**发现问题：**
 现有 LLM uncertainty estimation 通常要等模型完整生成答案，甚至要采样多次完整回答，才能判断输出是否可靠。这在医疗、金融等高风险场景里成本很高，也太晚了：模型可能已经生成了一大段看似可信但错误的内容。作者发现：评估不确定性不一定需要完整 generation，很多有效信号其实在生成早期的 logits 里就已经出现了。

**Insight：**
 作者的核心直觉是：模型“不可靠”的信号可能集中在少数关键 token 上，而不是均匀分布在整段回答里。
 所以，不需要看完整答案，也不需要平均所有 token；只要在早期 generation 中找到最有信息量的高风险 token，就能估计最终回答是否可能出错。
 更进一步，如果这种 generation\-based uncertainty 可以被学习下来，那么甚至可以在模型还没生成答案之前，只看 prompt 就预测 uncertainty。

**任务：**
 用于降低 LLM 不确定性估计的生成成本，并实现更早的错误检测。作者先提出一个统一框架，把 uncertainty estimation 按成本分成四类：**multi\-generation**、**single\-generation**、**partial\-generation** 和 **input\-only estimation**。在此基础上提出两个方法：
**Logit Magnitude** 用 early\-stopped partial generation 中的 top\-M logits 做 L2 norm，聚合成序列级 uncertainty score；如果连续一段时间 top\-M 高风险 token 不再变化，就提前停止生成。
**MetaUE** 则用 Logit Magnitude 产生的 uncertainty score 作为 pseudo\-label，训练一个 frozen encoder \+ MLP head，让模型只根据输入 prompt 直接预测 uncertainty，不需要生成答案。实验覆盖 COQA、NewsQA、emrQA，模型包括 Qwen3\.5、Gemma4、Llama3 以及 dense / MoE 模型。结果显示，Logit Magnitude 在多数设置下接近或超过 Semantic Entropy、Self\-Consistency、Sequence Entropy、LogTokU、Hidden\-State Score 和 Self\-Certainty，同时只需要部分 token；MetaUE 虽然是 zero\-generation 方法，也能达到接近若干 generation\-based baseline 的效果。总体上，这篇文章说明：LLM uncertainty estimation 不一定要“生成完再判断”，而可以在生成早期甚至生成前完成低成本可靠性预测。




<a id="e-014"></a>

### E-014. [Evaluating the Statistical Realism of LLM-generated Social Science Data](https://www.pnas.org/doi/10.1073/pnas.2538145123) (PNAS)

**发现问题：**
 现在很多人想用 LLM 生成社会科学数据，比如模拟问卷回答、人口样本或人生轨迹。但作者指出：现有评估经常看 individual\-level prediction，也就是模型能不能预测某个人的答案；这不符合社会科学的核心需求。社会科学更关心的是一个样本能不能代表总体，能不能复现真实社会中的分布、相关性和结构关系。作者发现：当前 LLM 生成的数据在 population\-level statistical realism 上明显不足，尤其容易把真实世界的复杂异质性压缩成少数“典型人群”模式。

**Insight：**
 作者的核心观点是：LLM 生成社会科学数据不能只看“单个人像不像”，而要看“整个人群像不像”。
 一个好的 synthetic population 应该像真实 survey sample 一样，能复现总体层面的统计规律，比如收入、教育、婚姻、健康变量的分布，变量之间的相关性，以及人生事件顺序的多样性。
 但当前 LLM 更像是在按刻板印象生成“典型案例”：它知道一些社会常识，比如教育和收入相关、婚姻和生育相关，但会把这些关系生成得过强，同时忽略真实人群中的长尾、随机性和多样人生路径。

**任务：**
 用于评估 LLM 生成社会科学数据是否具有真实的总体统计结构。作者提出 **SSDataBench**，从五类统计模式评估 synthetic social science data：
**Type 1**：单变量分布，比如教育水平、健康状态是否和真实数据一致；
**Type 2**：双变量关联，比如教育和收入、性别和职业之间的关系是否真实；
**Type 3**：多变量预测关系，比如用性别、种族、教育预测收入时，模拟数据里的 R² 是否和真实数据接近；
**Type 4**：人生事件序列分布，比如完成教育、开始工作、结婚、生育的顺序是否多样；
**Type 5**：人生事件序列和协变量的关联，比如不同性别、教育群体的人生路径差异是否真实。

实验使用 4 个纵向数据集和 3 个横截面数据集，覆盖人口、社会经济地位、婚姻、健康、能力和态度六大社会领域，并评估 15 个 LLM。结果显示：多数模型平均 pass rate 低于 0\.5；单变量分布和人生事件序列最难复现；LLM 生成的数据普遍 entropy 更低，说明多样性不足；同时变量关联和回归预测关系经常被夸大，反映出 stereotyped priors。作者还发现，模型越新或越强并不必然带来更好的统计真实性，比如 GPT\-3\.5 到 GPT\-5 没有稳定提升。最后，作者提出改进方向：提供更丰富输入、加入 qualitative context，以及用社会科学 survey data 做 domain\-specific training；初步实验显示，用 CPS\-ASEC 1970 微调 Llama\-3\.1\-8B 后，在 CPS\-ASEC 1980、U\.S\. Census 1980 和 GSS 2018 上的 pass rate 都明显提升。总体上，这篇文章把 LLM 社会模拟评估从“个体预测是否准确”推进到“生成群体是否具有真实统计规律”。




<a id="e-015"></a>

### E-015. [Into the Gray Zone: Domain Contexts Can Blur LLM Safety Boundaries](https://arxiv.org/pdf/2604.15717)

**发现问题：**
 LLM 安全对齐面临一个核心矛盾：同一类知识在不同场景下可能既有帮助也有风险。比如安全研究、化学、医学、网络安全等领域，本来就需要讨论敏感知识；但模型一旦看到“专业领域上下文”，就可能把危险请求误判成合法研究需求。作者发现：**domain context 会模糊模型的安全边界**，让模型进入一种既不像明显 benign、也不像明显 harmful 的 **gray zone**，从而导致拒答判断不稳定。

**Insight：**
 作者提出两个现象：

**Vertical Unlocking**：
 特定领域上下文会选择性放松该领域相关的安全防御。比如化学论文背景更容易放松化学相关危险知识，网络安全论文背景更容易放松攻击相关内容。

**General Unlocking**：
 安全研究上下文更危险，因为 jailbreak / red\-teaming 论文天然会讨论多种风险类别。模型可能把这类上下文理解为“合法安全研究”，于是对不同 harmful categories 都出现更广泛的防御放松。

直观来说，普通 persona 比如“我是研究员”已经容易被现代模型识别为浅层伪装；但如果给模型一个真实论文上下文、多轮讨论方法细节，再把危险请求包装成“论文案例分析”，模型就更容易进入灰区：它不确定自己是在帮助安全研究，还是在协助有害行为。

**任务：**
 用于系统评估 **领域上下文如何削弱 LLM safety boundary**，并提出攻击与防御方案。作者提出 **JARGON**：先用安全研究论文建立合法学术语境，再通过多轮 benign discussion 建立上下文信任，最后把 harmful goal 重写成论文方法中的案例、示例或对比分析请求。系统还会生成多个 query variants，并用 judge 选择最容易成功的版本。

实验在 JailbreakBench 上评估，覆盖 GPT\-5\.2、Claude\-Sonnet\-4\.5、Claude\-Opus\-4\.5、Gemini\-3\-Flash、DeepSeek\-V3\.2、Qwen3\-235B\-A22B\-IT、LLaMA\-4\-Scout\-IT 等模型。结果显示，JARGON 平均 ASR 达到 **99%**，明显高于 PAIR、AmpleGCG、Crescendo、FITD、X\-Teaming 等 baseline。作者进一步做 activation space analysis，发现 JARGON query 的隐藏状态落在 benign 和 harmful 之间的中间区域，也就是 **gray zone**；attention analysis 也显示，经过上下文重写后，模型对敏感 token 的注意力会被稀释，因此更难触发拒答。

防御方面，作者尝试两类方法：
 一是 **policy\-guided safeguard**，让模型在识别到灰区请求时保持有帮助但不给出可操作危险细节；
 二是 **alignment fine\-tuning**，用 JARGON\-style adversarial queries 和安全回答进行微调，使模型学会在学术上下文中区分“可以讨论概念”和“不能输出危险细节”。结果显示，fine\-tuning 能降低 ASR，同时基本保持 MMLU、HellaSwag、GSM8K 等通用能力。总体上，这篇文章说明：LLM 安全问题不只是“能不能识别 harmful query”，更难的是在真实专业语境下判断用户意图和信息边界。





<a id="e-016"></a>

### E-016. [Towards Intrinsic Interpretability of Large Language Models: A Survey of Design Principles and Architectures](https://arxiv.org/pdf/2604.16042)

**发现问题：**
 现在很多 LLM interpretability 工作主要是 **post\-hoc explanation**，也就是模型训练完之后，再用外部工具去解释它，比如 attribution、probing、LogitLens、SAE、causal intervention 等。但作者指出：这些方法本质上是在“事后近似解释”模型，容易存在 **fidelity gap**，也就是解释结果不一定真实对应模型内部计算过程。尤其是 LLM 很复杂，post\-hoc 方法虽然灵活，但很难把局部解释整合成一个稳定、可信的整体机制理解。

**Insight：**
 作者的核心观点是：解释性不一定只能在模型训练后补救，也可以从模型设计阶段就内置进去。
 这就是 **intrinsic interpretability**：让模型本身的结构、计算路径、模块、概念表示或稀疏激活天然可解释。简单说，不是先造一个黑盒再解释它，而是直接造一个“玻璃盒模型”。

论文把 intrinsic interpretability 总结成五类设计原则：

**Functional Transparency**： 让模型计算形式本身可读，比如 GAM、KAN、B\-cos Networks。模型像一个明确的函数或算法，每个部分的作用可以直接看。 

**Concept Alignment**：让中间变量对应人类能理解的概念，比如 Concept Bottleneck Model、Concept Embedding Model、Codebook Features。 

**Representational Decomposability**：把 hidden representation 分解成独立语义子空间，比如 Backpack LM、CoCoMix，让不同语义因素更容易单独查看和干预。 

**Explicit Modularization**：把模型拆成多个专家或模块，比如 MoE。通过 router 可以看到输入走了哪些专家，从而让计算路径更可追踪。 

**Latent Sparsity Induction**：不手动指定模块，而是通过 sparse training、L0 regularization、GLU/SwiGLU 等方式，让模型内部自然形成稀疏、任务相关的子电路。 

**任务：**
 这是一篇 survey，用于系统梳理 **LLM 内生可解释性 / intrinsic interpretability** 的研究框架。作者首先区分 post\-hoc interpretability 和 intrinsic interpretability：前者用外部工具解释已训练模型，后者把可解释组件放在模型计算路径上，修改这些组件会直接改变输出。然后作者按照五类设计原则整理现有方法，并分析每类方法的优缺点、代表架构和 trade\-off。

论文还总结了这个方向的主要挑战：
**第一，如何定义和评估 intrinsic interpretability**，因为稀疏、模块化不一定等于人类真的能理解；
**第二，如何平衡可解释性和表达能力**，因为强约束可能降低性能；
**第三，如何扩展到大规模 LLM**，很多方法目前只在小模型或中等规模模型上验证；
**第四，如何提升训练效率和稳定性**，因为稀疏、routing、模块化会增加优化难度；
**第五，如何和 post\-hoc 方法结合**，用 post\-hoc 工具验证 intrinsic design 是否真的 faithful。

总体上，这篇文章不是提出一个具体新模型，而是把 LLM 可解释性从“训练后解释黑盒”推进到“设计时构建可解释模型”的视角，并给出一个比较清晰的 taxonomy。它适合用来作为 intrinsic interpretability 方向的综述入口。


<a id="e-017"></a>

### E-017. [Assessing the Creativity of Large Language Models: Testing, Limits, and New Frontiers](https://arxiv.org/pdf/2605.13450)

**发现问题：**
 现在很多工作会直接拿人类创造力测试来评估 LLM，比如 DAT、CDAT、PACE、RAT，然后据此说某个模型“更有创造力”。但作者指出：这些测试对 **机器创造力** 是否有效，其实没有被系统验证。更严重的是，一个测试分数高，可能只是因为模型通用能力强，而不是真的更有创造力。比如 PACE 和 creative writing benchmark 相关性很高，但控制 general capability 后，相关性明显下降，说明它很大程度上可能只是能力代理。

**Insight：**
 作者的核心观点是：评估 LLM 创造力不能只看一个 raw correlation，而要区分两个东西：

**Validity：**
 这个创造力测试和目标创造性任务是否相关。
 比如它能不能预测 creative writing、divergent thinking、scientific ideation 的表现。

**Specificity：**
 控制通用能力后，它还能不能预测创造力。
 也就是说，它测到的是不是 general capability 之外的“创造性成分”。

作者发现，不同创造力测试其实只适合预测不同类型的创造力：
**DAT** 更适合预测 creative writing；
**CDAT** 更适合预测 divergent thinking；
 但现有测试都不能可靠预测 **scientific ideation**。这说明“创造力”不是一个单一维度，不能用一个测试概括所有创造性能力。

**任务：**
 用于系统评估自动化创造力测试是否真的能预测 LLM 的创造性表现，并提出新的科学创意评估方法。作者测试了 54 个 instruction\-tuned LLM，覆盖 OpenAI、Anthropic、Google、Meta、Mistral、Qwen、DeepSeek、Cohere、NVIDIA、Microsoft 等模型。评估的创造力测试包括 **DAT、CDAT、PACE、RAT**；目标 benchmark 覆盖三类创造力：
 creative writing，包括 Arena CW、EQ\-Bench CW、Mazur CW；
 divergent thinking，包括 Hivemind、NoveltyBench；
 scientific ideation，包括 LiveIdeaBench。

实验结果显示：DAT 在 creative writing 上最好，CDAT 在 divergent thinking 上最好，但没有任何已有测试能显著预测 scientific ideation。为了解决这个问题，作者提出 **DRAT（Divergent Remote Association Test）**。它结合了 DAT 和 RAT：模型需要生成多个彼此差异很大的词，同时这些词还要能和多个 anchor words 产生隐喻关联。也就是说，DRAT 同时测试 **divergent thinking** 和 **convergent thinking**。

结果显示，DRAT 是第一个能显著预测 scientific ideation 的自动化测试，在 LiveIdeaBench 上达到显著 validity 和 specificity；并且它的效果不能简单由 DAT \+ RAT 的线性组合替代，说明“同时做发散和收敛”比单独测两种能力再相加更有效。总体上，这篇文章把 LLM 创造力评估从“套用人类创造力测试”推进到“验证测试是否真的预测创造性成果，并区分创造力与通用能力”的更严谨框架。
