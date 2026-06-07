# D. 发现与探测 / Discovery & Probing

探讨模型内部 latent knowledge 的形成规律、空间分布、层级机制与表里状态差异。

[← Back to README](README.md)

## Paper Overview

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

---

## D. 发现与探测：探讨模型内部 LK 的形成规律、空间分布以及表里状态差异

<a id="d-001"></a>

<a id="d-001"></a>

### D-001. [How Do Transformers Learn to Associate Tokens](https://openreview.net/pdf?id=A4Us8jxVGq)

**发现问题：**
 Transformer 能学到词之间的语义关联，比如 “bird” 和 “flew”、“fish” 和 “pond”，但我们并不清楚这些关联是如何在训练过程中形成的。已有理论分析往往依赖合成数据、简化结构或非标准训练方式，和真实 LLM 训练差距较大。

**Insight：**
 作者提出一个直观解释：Transformer 早期训练的梯度主导项，已经决定了模型如何开始建立 token 关联。作者发现，模型权重可以由三类简单统计函数组合而成：bigram mapping 捕捉相邻词关系，interchangeability mapping 捕捉功能相似词，context mapping 捕捉长距离上下文关系。也就是说，Transformer 一开始并不是随机地学语义，而是在用语料统计逐步搭建语义关联网络。

**任务：**
 用于解释 Transformer 如何从自然语言数据中学习 token 之间的语义关联。作者通过梯度 leading\-term 分析，推导 output matrix、value matrix、query\-key matrix 和 positional encoding 的闭式近似表达。实验在 TinyStories 上训练 3\-layer attention\-only Transformer，并在 Pythia\-1\.4B 与 OpenWebText / FineWeb 上验证。结果表明，理论刻画的权重结构与真实模型学习到的权重高度一致，并能解释不同层和 attention heads 如何逐步形成语义关联。


<a id="d-002"></a>

<a id="d-002"></a>

### D-002. [What Do Language Models Learn and When? The Implicit Curriculum Hypothesis](https://arxiv.org/pdf/2604.08510)

**发现问题：**
 现有 scaling law 主要告诉我们模型整体 loss 会如何下降，但不能解释模型在预训练过程中**具体什么时候学会了哪些能力**。例如 GSM8k 性能变差时，很难判断问题出在数学能力、语言理解，还是多步推理能力上。

**Insight：**
 作者提出 **Implicit Curriculum Hypothesis**：语言模型预训练并不是随机地学会能力，而是遵循一种隐式课程。简单能力通常先出现，复杂组合能力通常后出现；而且这种能力出现顺序在不同模型家族、不同规模、不同数据混合下都比较稳定。进一步地，相似任务在模型内部表示中也更接近，因此可以用任务表示来预测某些任务的学习轨迹。

**任务：**
 用于 **分析语言模型预训练过程中的能力涌现顺序与训练动态**。作者设计了 91 个简单任务和组合任务，包括复制、大小写转换、形态变化、翻译、事实抽取、指代消解、逻辑推理和数学任务，并在 Pythia、OLMo、LLM360 等多个模型家族的中间 checkpoint 上跟踪这些能力什么时候出现。


<a id="d-003"></a>

<a id="d-003"></a>

### D-003. [Transformer layers as painters](https://ojs.aaai.org/index.php/AAAI/article/view/34708)

**发现问题：**
 Transformer 的每一层结构相同，但我们并不清楚每一层到底是否都不可替代、层顺序是否严格重要。作者发现：底层和最后几层比较特殊，但大量中间层表现出明显相似性，说明中间层可能共享某种表示空间。

**Insight：**
 作者提出一个直观类比：Transformer 中间层像一组“画家”，都在同一张画布上逐步添加信息。不同层不是完全冗余的，但它们能理解相似的中间表示，所以模型对跳过中间层、交换中间层顺序、甚至并行运行中间层都有一定鲁棒性。也就是说，**中间层共享表示空间，但执行的是不同功能。** 

**任务：**
 用于 **分析 Transformer 层的功能、鲁棒性和推理加速潜力**。作者在冻结模型上测试不同执行策略，包括跳层、重复中间层、反转层顺序、随机层顺序、并行层和循环并行层。实验覆盖 Llama2、BERT\-Large，并补充 Mistral\-7B、Pythia\-6\.9B，评测任务包括 LAMBADA、ARC、GSM8K、HellaSwag、WinoGrande 和 GLUE。


<a id="d-004"></a>

<a id="d-004"></a>

### D-004. [LLM Safety From Within](https://arxiv.org/pdf/2604.18519)

**发现问题：**
 现有 LLM 安全检测模型通常只看最后一层表示，或者通过生成 “safe/unsafe” 来做分类。但作者发现，安全相关信息并不只存在于最后一层，而是分布在模型的多个中间层中。只依赖最后一层会浪费大量内部安全信号，也会带来更高的推理开销。

**Insight：**
 作者提出一个直观想法：LLM 内部其实已经有很多“安全神经元”，它们能反映文本是否有害。与其重新训练一个完整 guard model，不如直接从模型内部各层找出这些安全相关神经元，再把不同层的信息加权聚合起来，用一个轻量分类器判断 harmful / safe。

**任务：**
 用于检测用户输入和模型回复中的有害内容。作者提出 SIREN，先用线性探针在每一层识别 safety neurons，再根据各层验证集表现进行自适应加权聚合，最后训练轻量 MLP 分类器。实验覆盖 Qwen3、Llama3 系列 backbone，以及 ToxicChat、OpenAIModeration、Aegis、WildGuard、SafeRLHF、BeaverTails 等安全检测数据集。结果表明，SIREN 比现有 guard models 表现更好，参数更少，并且能泛化到 reasoning traces 和 streaming detection 场景。




<a id="d-005"></a>

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

<a id="d-007"></a>

### D-007. [Convergent Evolution: How Different Language Models Learn Similar Number Representations](https://arxiv.org/pdf/2604.20817)

**发现问题：**
 很多语言模型都会学到数字 token 的周期性表示，比如在 Fourier 频域中出现 **T=2、5、10** 的周期峰值。但作者发现：有 Fourier spike 不代表模型真的学会了可用的数字结构。比如 LSTM 和原始 token 频率分布也有明显周期峰值，但无法用线性 probe 解码 `n mod T`。

**Insight：**
 作者提出一个两层理解：数字表示有 **spectral convergence** 和 **geometric convergence**。前者只是频域上看起来有周期结构，后者才表示数字按 `mod T` 在几何空间中可分。换句话说，Fourier spike 像“看起来有规律的影子”，但 linear probe 能分出 `mod T` 才说明模型真的形成了功能性数字表示。

**任务：**
 用于分析不同模型如何学习数字表示，以及哪些因素决定数字表示是否真正可用。作者比较 Transformer、Mamba、Gated DeltaNet、LSTM、GloVe、FastText 和原始 token 分布，并通过 Fourier spectrum 与 mod\-T linear probing 区分 spectral / geometric convergence。实验还控制数据、架构、优化器和 tokenizer，发现自然语言中的数字\-文本共现、数字间交互、上下文长度，以及多 token 加法任务都会影响几何可分的数字表示形成。


<a id="d-008"></a>

<a id="d-008"></a>

### D-008. [Task-Driven Subspace Decomposition for Knowledge Sharing and Isolation in LoRA-based Continual Learning](https://arxiv.org/pdf/2603.00191)

**发现问题：**
 LoRA\-based continual learning 通常通过“隔离新任务更新空间”来避免遗忘，比如把新任务放到旧任务的 null space 中。但作者发现：这种做法过度强调隔离，忽略了任务之间可共享的知识；而且旧任务的 null space 不一定对新任务有效，可能只是“安全但没用”的空间，导致新任务也学不好。

**Insight：**
 作者提出一个直观想法：LoRA 的 down\-projection 像一个“门”，决定模型能学习输入特征中的哪些方向。与其只找不影响旧任务的方向，不如把空间分成两类：一类是 **general subspace**，旧任务和新任务都强激活，用来共享知识；另一类是 **isolated subspace**，新任务强激活、旧任务弱激活，用来学习新任务特有知识。这样既能转移共享知识，又能隔离任务冲突。

**任务：**
 用于解决 LoRA 连续学习中的灾难性遗忘和稳定性\-可塑性冲突。作者提出 **LoDA**，先根据 projection energy 分解出 general / isolated 两个 LoRA 子空间，固定 down\-projection，只训练 up\-projection；再用 **Gradient\-Aligned Optimization（GAO）** 提升梯度一致性；训练后对 general branch 做 closed\-form recalibration，再合并 LoRA 到 backbone。实验覆盖 ImageNetR、ImageNetA、CIFAR100、CUB、DomainNet，并在 ViT、CLIP、DINO、iBOT 等 backbone 上验证，结果优于现有 PEFT\-based continual learning 方法。


<a id="d-009"></a>

<a id="d-009"></a>

### D-009. [Last-Layer-Centric Feature Recombination](https://arxiv.org/pdf/2604.26454)

**发现问题：**
 现有基于 DINO / ViT 的单目深度估计通常会均匀选取几个中间层做多尺度特征，默认 3D 几何信息在各层中均匀分布。但作者发现并不是这样：DINOv3 的 3D 几何知识主要集中在更深层，尤其最后几层的深度可预测性更强，也更能反映样本之间的几何差异。

**Insight：**
 作者提出一个直观想法：最后一层应该作为“几何锚点”，而不是只把它当作普通多尺度特征之一。中间层不是越多越好，而是要选择和最后一层最互补的层。于是 LFR 用最后一层作为主表示，再挑选与它相似度最低的中间层进行重组，让模型既保留最后一层强 3D 几何信息，又补充中间层的互补细节。

**任务：**
 用于提升 DINOv3 在单目深度估计中的 3D 几何迁移能力。作者提出 **Last\-Layer\-Centric Feature Recombination（LFR）**，插入在 DINOv3 backbone 和 DPT decoder 之间：先用 minimal\-similarity 策略选择互补中间层，再通过轻量 linear adapter 与最后一层特征融合，最后进行多层加权深度预测。实验覆盖 NYU\-Depth v2、KITTI，并在 SUN RGB\-D 和 Argoverse 上做 zero\-shot 测试。结果显示，LFR 能稳定提升 DINOv3 的深度估计精度和跨数据集泛化能力。


<a id="d-010"></a>

<a id="d-010"></a>

### D-010. [Beyond Outliers: A Data-Free Layer-wise Mixed-Precision Quantization Approach Driven by Numerical and Structural Dual-Sensitivity](https://arxiv.org/pdf/2603.17354)

**发现问题：**
 现有层级混合精度量化方法通常只看权重 outlier、误差或熵等单一数值指标，并且把同一层里的所有模块一视同仁。但作者发现：有些层虽然数值 outlier 不明显，量化后仍会严重掉点，因为它们的结构表达能力很关键。也就是说，层敏感性不只来自“数值异常”，还来自“结构功能”。

**Insight：**
 作者提出一个直观想法：量化时不能只看哪一层“数值更极端”，还要看这一层在模型里“干什么”。他们把 Transformer 层拆成两类角色：**Detector** 负责检测模式，比如 QK、FFN input；**Writer** 负责把信息写回 residual stream，比如 OV、FFN output。NSDS 同时评估每个组件的 **Numerical Vulnerability** 和 **Structural Expressiveness**，再合成层级敏感性分数，决定哪些层保留更高 bit。

**任务：**
 用于在无校准数据的情况下做 LLM 层级混合精度量化。作者提出 **NSDS**，先用机制视角分解每层的 Detector / Writer，再用 excess kurtosis 衡量数值脆弱性，用 SVD 谱能量、谱熵和角色感知重加权衡量结构表达性，最后通过 **MAD\-Sigmoid \+ Soft\-OR** 聚合成层敏感性分数，并将高敏感层分配 4\-bit、低敏感层分配 2\-bit。实验覆盖 Llama\-3\.1\-8B、Qwen2\.5\-7B、Llama\-2\-13B、Qwen2\.5\-14B，任务包括 ARC\-C、HellaSwag、PIQA、BoolQ、WinoGrande、TruthfulQA、WikiText\-2 和 C4。结果显示，NSDS 在不同 bit budget、不同模型规模和不同 PTQ 后端上都优于或接近现有方法。


<a id="d-011"></a>

<a id="d-011"></a>

### D-011. [Large Language Models are Universal Reasoners for Visual Generation](https://arxiv.org/pdf/2605.04040)

**发现问题：**
 现有文生图模型即使使用同一个 LLM 同时做理解和生成，也经常出现“理解强、生成弱”的问题：模型生成时会弄错数量、位置关系、物理常识等，但让它检查自己生成的图时，却能准确发现这些错误。作者把这个现象称为 **understanding\-generation gap**。

**Insight：**
 作者提出一个直观想法：不要只把 LLM 当作 text encoder，而要把它当作“视觉生成的通用推理器”。LLM 先根据 prompt 生成一个粗糙的视觉草图，再自己检查这个草图哪里不符合 prompt，最后把 **prompt \+ draft \+ evaluation** 一起交给 diffusion model。这样，draft 提供场景布局，evaluation 提供“哪里需要改”的纠错信号，让生成过程不再只依赖单一文本 embedding。

**任务：**
 用于提升文生图模型对复杂 prompt 的语义一致性和组合约束满足能力。作者提出 **UniReasoner**，采用 **Draft–Evaluate–Diffuse** 三阶段流程：先用 LLM 生成离散视觉 token 草图，再让同一个 LLM 对草图进行自我评估，指出缺失物体、错误数量、错误属性或空间关系，最后用冻结的 SANA diffusion backbone 在三重条件下生成最终图像。实验在 GenEval 和 DPG\-Bench 上验证，UniReasoner 在相同 diffusion generator 下将 GenEval 从 **0\.79 提升到 0\.88**，DPG\-Bench 从 **84\.50 提升到 86\.30**，尤其提升 Counting、Position 和 Attribute Binding。


<a id="d-012"></a>

<a id="d-012"></a>

### D-012. [The Cylindrical Representation Hypothesis for Language Model Steering](https://arxiv.org/pdf/2605.01844)

**发现问题：**
 现有 activation steering 通常基于 **Linear Representation Hypothesis**，认为概念可以用一个全局线性方向控制。但作者发现：真实模型中概念方向并不完全正交，不同概念会相互重叠，所以同一个 steering vector 在不同样本上效果很不稳定。有些样本能成功激活目标概念，有些样本却失败或输出崩坏。

**Insight：**
 作者提出一个直观几何解释：模型表示不是简单的一条“概念直线”，而更像围绕样本形成的“圆柱结构”。圆柱的 **central axis** 负责把表示推向目标概念；周围的 **normal plane** 决定这个推动是否容易成功。normal plane 里又有一些 **sensitive sectors**，进入这些区域会促进概念激活；进入其他区域则可能抑制、延迟甚至破坏 steering。因此，steering 不稳定不是随机噪声，而是因为每个样本都有自己的局部几何结构。

**任务：**
 用于解释和预测 LLM activation steering 为什么在不同样本上表现不稳定。作者提出 **Cylindrical Representation Hypothesis（CRH）**，将 steering vector 分解为 axis component、normal\-plane component 和 residual component，并分析不同部分对概念激活和输出崩坏的影响。实验覆盖 Gemma\-2B\-IT、LLaMA2\-7B\-Chat，测试 100 个 text/code/math 概念，并比较 DiffMean、PCA、Mean\-Centering、Probe\-based steering 等方法。结果显示，normal\-plane component 越强，目标概念越早出现，但输出也越容易崩坏；同时，sensitive sector 无法仅由相似的 difference vector 稳定预测，解释了 steering 的样本级不可预测性。


<a id="d-013"></a>

<a id="d-013"></a>

### D-013. [Disentangling Mathematical Reasoning in LLMs](https://arxiv.org/pdf/2604.15842v1)

**发现问题：**
 LLM 能做一些简单算术，但我们并不清楚它到底是在“背答案”、做模式匹配，还是在内部真的执行某种计算过程。作者发现：模型很早就能识别这是一个数学任务，但正确答案并不是早期就出现，而是在最后几层才被生成出来。

**Insight：**
 作者提出一个直观解释：算术推理像是模型内部的一场“分工合作”。**Attention** 负责把输入里的关键信息搬到最后一个 token 上，比如操作数和运算符；**MLP** 负责在这些信息基础上逐步聚合、变换，最后生成答案。会算术的模型有清晰分工，不会算术的模型这种分工不明显。

**任务：**
 用于分析 LLM 做数学推理时的内部机制。作者使用 **early decoding / logit lens**，在每一层 attention 和 MLP 后把 residual stream 解码成中间预测，观察模型什么时候识别任务、什么时候传播操作数和运算符、什么时候生成正确结果。实验比较 GPT\-NeoX\-20B 和 GPT\-2 XL，在加法、减法、两操作数和三操作数任务上验证。结果显示，GPT\-NeoX\-20B 中 attention 会在中间层传播 operand/operator，MLP 在后期逐步形成答案；而 GPT\-2 XL 缺少这种 attention\-MLP 分工，因此算术能力很差。


<a id="d-014"></a>

<a id="d-014"></a>

### D-014. [Learning a Generative Meta-Model of LLM Activations](https://arxiv.org/pdf/2602.06964)

**发现问题：**
 现有激活分析方法，比如 PCA、SAE、线性 steering，通常假设模型内部表示具有线性或稀疏结构。但作者发现：这些假设可能太强，干预时容易把 activation 推到模型真实分布之外，导致输出不流畅或崩坏。因此，仅靠线性方向或稀疏特征，可能无法准确刻画 LLM activation manifold。

**Insight：**
 作者提出一个直观想法：与其手工假设 activation 是线性的、稀疏的，不如直接训练一个“activation 世界模型”。也就是用 diffusion model 学习 LLM 内部 residual stream activation 的真实分布。这个模型像一个 **activation prior**：当 steering 把表示推歪后，它可以把 activation 拉回自然流形，同时尽量保留想要注入的语义。

**任务：**
 用于学习 LLM activation 的生成式表示模型，并辅助解释和干预。作者提出 **Generative Latent Prior（GLP）**，在 10 亿个 residual stream activations 上训练 diffusion meta\-model，覆盖 Llama1B 和 Llama8B。GLP 可用于两类任务：一是 **on\-manifold steering**，提升 sentiment steering、SAE feature steering、persona elicitation 的概念控制与流畅性平衡；二是作为 feature encoder，用 **meta\-neurons** 做 1\-D probing，在 113 个二分类概念任务上优于 SAE、raw layer output 和 raw MLP neurons。实验还显示，GLP 的 diffusion loss 随 compute 平滑下降，并能预测 steering 和 probing 的下游效果。


<a id="d-015"></a>

<a id="d-015"></a>

### D-015. [Vision Transformers Need More Than Registers](https://arxiv.org/pdf/2602.22394)

**发现问题：**
 ViT 在 dense vision 任务中经常出现奇怪 artifacts，比如背景区域反而和 CLS token 更相似，导致定位、分割、开放词汇检测表现差。已有方法认为问题来自 high\-norm tokens，并用 register tokens 缓解；但作者发现：register 只能消除 high\-norm 现象，不能解决根本问题。真正原因是 ViT 学会了用背景 patch 作为捷径来表达全局语义。

**Insight：**
 作者提出一个直观解释：ViT 的 CLS token 有点“偷懒”。因为训练监督通常只有图像级标签或图文级对齐，没有 patch 级监督；再加上全局 attention 能让前景信息扩散到背景，CLS token 就会从大量背景 patch 中聚合语义，而不是只看真正的物体。也就是说，背景 patch 变成了“语义捷径”，模型分类能对，但 dense feature 会错位。

**任务：**
 用于分析并缓解 ViT 中的 dense\-feature artifacts。作者提出 **Patch Score** 衡量 patch 与 CLS token 的相似度，并用 **Point\-in\-Box（PiB）** 判断最高分 patch 是否落在前景框内；分析发现 ViT 的高分 patch 更常落在背景，且这种偏差从训练早期就出现。为解决该问题，作者提出 **LaSt\-ViT / LazyStrike**：用频域 low\-pass filtering 计算每个 patch 的稳定性，再按 channel\-wise Top\-K 选择稳定 patch 聚合到 CLS token，减少背景 shortcut。实验覆盖 label\-supervised、text\-supervised 和 self\-supervised ViT，在 ImageNet、VOC、COCO、ADE20K、Cityscapes、LVIS 等 12 个 benchmark 上验证，提升 object discovery、semantic segmentation、open\-vocabulary detection 和 instance segmentation。


<a id="d-016"></a>

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

<a id="d-017"></a>

### D-017. [Rethinking RL for LLM Reasoning: It’s Sparse Policy Selection, Not Capability Learning](https://arxiv.org/pdf/2605.06241)

**发现问题：**
 大家通常认为 RL 能让 LLM 学到新的推理能力，但作者发现：RL 可能并没有真正教会模型新的 reasoning strategy，而只是把 base model 本来就会的正确路径概率提高了。也就是说，base model 的采样空间里已经有正确解，RL 主要是在关键分叉点帮模型“选对路”。

**Insight：**
 作者的核心洞察是：RL 对推理的改变非常稀疏。它不是大规模改写模型行为，而只是在少数 **high\-entropy decision points** 上重新排序 token 概率。论文发现，RL 只影响大约 **1–3%** 的 token 位置，而且被 RL 提升的 token 基本都已经在 base model 的 top\-5 候选里。换句话说，RL 不是“创造新能力”，而是在模型犹豫的时候，把原本第二、第三可能的正确分支提上来。

**任务：**
 用于重新理解 RL 在 LLM 数学推理中的作用，并提出低成本替代方法。作者通过 token\-level analysis 比较 base model 和 RL model，发现 RL 的有效修改集中在高熵位置；oracle 实验证明只修正这些少数 token 就能恢复大部分甚至全部 RL 提升；同时 KL\-LoRA 实验证明这种修正可以被极小 adapter 表示。基于此，作者提出 **REASONMAXXER**：不用 RL，只从 base model 生成少量 rollouts，筛选那些有对有错的题目，在高熵 token 上做 advantage\-weighted contrastive loss，其他位置用 KL anchor 保持 base model 行为。实验覆盖 Qwen2\.5、Qwen3、DeepSeek\-R1\-Distill、Mistral 等模型，以及 MATH\-500、GSM8K、AMC、AIME、Minerva、OlympiadBench。结果显示，REASONMAXXER 用几十道题、几分钟单卡训练，就能匹配或超过完整 RL，训练成本降低约三个数量级。



<a id="d-018"></a>

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
