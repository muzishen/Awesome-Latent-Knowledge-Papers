# E. 评估与校准 / Evaluation & Calibration

整理如何利用 latent knowledge 评估模型可靠性、安全性、不确定性、幻觉与行为边界。

[← Back to README](README.md)

## Paper Overview

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
| E-018 | [Extracting Training Data from Diffusion Language Models via Infilling](#e-018) | 2026 | arXiv preprint | DLM 训练数据抽取评估 |

---

## E. 评估与校准：能不能利用 latent knowledge 控制模型行为，并评估安全性和可靠性？


<a id="e-001"></a>

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

<a id="e-003"></a>

### E-003. [Domain-Filtered Knowledge Graphs from Sparse Autoencoder Features](https://arxiv.org/pdf/2604.23829)

**发现问题：**
 SAE 可以从模型内部提取大量可解释 feature，但这些 feature 通常只是一个“扁平清单”。里面混有很多通用、格式、弱相关特征，真正的领域概念被分散在不同 feature 中，而且 feature 之间缺少关系结构，导致很难看出模型内部到底如何组织某个领域知识。

**Insight：**
 作者的核心想法是：不要只看单个 SAE feature，而是把它们组织成一个“模型内部知识图谱”。先通过对比过滤找出真正属于某个领域的概念 feature，再用图结构连接它们：一张图表示概念在语料中如何共现，另一张图表示概念如何通过 transcoder 在层间流动。这样，SAE feature 就从零散的“词条表”变成了可浏览、可解释的知识地图。

**任务：**
 用于把大规模 SAE feature 转换成领域过滤后的内部知识图谱，帮助分析模型内部知识结构和局部推理机制。作者在生物教材语料上，用 Gemma Scope residual SAEs 和 layer\-20 到 layer\-21 的 transcoder，先通过 contrastive filtering 得到 biology\-specific concept universe，再构建多粒度 co\-occurrence graph 和 transcoder mechanism graph，并自动生成边标签。实验显示，这些图能恢复教材章节和小节结构，也能把一句话中上千个激活 feature 压缩成可读的局部机制图。

<a id="e-004"></a>

<a id="e-004"></a>

### E-004. [LLM DNA: Tracing Model Evolution via Functional Representations](https://openreview.net/pdf?id=UIxHaAqFqQ)

**发现问题：**
 现在开源 LLM 数量非常多，但模型之间到底是不是同源、是否经过微调/蒸馏/改造，很多时候文档并不清楚。已有方法要么依赖具体任务，要么要求固定模型集合，要么受 tokenizer 和架构限制，难以统一分析不同 LLM 的“血缘关系”。

**Insight：**
 作者提出一个直观类比：每个 LLM 都可以有自己的“DNA”。这个 DNA 不是参数本身，而是模型在一组输入上的**功能行为压缩表示**。如果两个模型输出行为相似，它们的 DNA 就接近；如果一个模型由另一个模型微调或蒸馏而来，它的 DNA 也应该保留相似模式。这样就可以像生物进化树一样，追踪 LLM 家族之间的演化关系。

**任务：**
 用于识别 LLM 之间的功能相似性、潜在血缘关系和演化路径。作者提出 **RepTrace**，先给不同 LLM 输入一组 prompts，收集模型回复，再用 sentence embedding 把回复转成语义向量，拼接后用随机高斯投影压缩成低维 **LLM DNA**。实验覆盖 305 个 Hugging Face LLM，包括 Qwen、Llama、Gemma、Pythia、Flan\-T5 等。结果显示，LLM DNA 能检测已知和未记录的模型关系，支持 training\-free model routing，并能构建 LLM phylogenetic tree，反映从 encoder\-decoder 到 decoder\-only、从旧模型到新模型的演化趋势。


<a id="e-005"></a>

<a id="e-005"></a>

### E-005. [Locate, Steer, and Improve: A Practical Survey of Actionable Mechanistic Interpretability in LLMs](https://arxiv.org/pdf/2601.14004)

**发现问题：**
 现有 Mechanistic Interpretability 综述大多把 MI 当作“观察工具”，主要总结模型内部有哪些机制，但缺少一个清晰框架说明：如何先定位关键内部结构，再干预这些结构，最后真正提升模型能力、安全性或效率。也就是说，MI 还没有被系统整理成一套可操作的“模型改造流程”。

**Insight：**
 作者提出一个非常直观的三步框架：**Locate → Steer → Improve**。先找到模型内部真正负责某种行为的对象，比如 residual stream、attention head、FFN neuron、SAE feature 或 circuit；再用不同方式控制它们，比如激活放大/抑制、参数局部优化、steering vector；最后把这种控制用于实际改进模型，比如提升安全性、减少偏见、增强推理、多语言能力、知识编辑，或者加速训练和推理。

**任务：**
 用于系统总结“可行动的机制可解释性”如何从内部分析走向模型干预和优化。文章先定义 LLM 中的核心可解释对象，然后归纳六类定位方法：**Magnitude Analysis、Causal Attribution、Gradient Detection、Probing、Vocabulary Projection、Circuit Discovery**；再总结三类干预方法：**Amplitude Manipulation、Targeted Optimization、Vector Arithmetic**。最后按应用目标整理为三大方向：**Improve Alignment、Improve Capability、Improve Efficiency**，覆盖安全可靠性、公平性、人格角色、多语言、知识管理、逻辑推理、高效训练和高效推理等场景。总体上，这篇综述把 MI 从“看懂模型”推进到“定位、操控并改进模型”。


<a id="e-006"></a>

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

<a id="e-007"></a>

### E-007. [Learning Uncertainty from Sequential Internal Dispersion in Large Language Models](https://arxiv.org/pdf/2604.15741v1)

**发现问题：**
 现有幻觉检测 / 不确定性估计方法要么依赖多次采样，计算开销大；要么只看最后一个 token 或平均 hidden states，容易丢失序列中的关键信号。作者发现：模型生成错误答案时，不确定性会体现在不同层 hidden states 的“分散程度”变化中，而不是简单满足某种固定的层间变化模式。

**Insight：**
 作者提出一个直观想法：如果模型对某个 token “拿不准”，它内部不同层的表示会更分散、更不稳定。与其只看最后一层或最后一个 token，不如沿着整个生成序列，观察每个 token 在各层 hidden states 中的 dispersion。SIVR 就像在读模型生成过程中的“内心波动曲线”：哪里表示突然发散，哪里就可能对应事实错误或幻觉。

**任务：**
 用于检测 LLM 生成内容是否存在幻觉，并估计回答的不确定性。作者提出 **SIVR**，对每个生成 token 提取跨层 hidden states，并计算三类内部方差信号：**covariance determinant** 表示整体分散程度，**circular variance** 表示方向分歧，**token entropy** 表示输出概率不确定性；再用轻量 Transformer encoder 聚合完整 token 序列，预测回答是否错误。实验覆盖 Llama\-3\.2\-3B、Llama\-3\.1\-8B、Ministral\-8B、Qwen\-3\-4B/14B，任务包括 TriviaQA、SciQ、MedMCQA、MGSM、MATH、MMLU、CommonsenseQA 和 fact\-checking。结果显示，SIVR 相比 logit\-based、sampling\-based 和 hidden\-state probing 方法整体表现更好，并且在 OOD 设置和小训练集下更稳健。




<a id="e-008"></a>

<a id="e-008"></a>

### E-008. [Black-Box Detection of LLM-Generated Text Using Generalized Jensen Shannon Divergence](https://arxiv.org/pdf/2510.07500)

**发现问题：**
 LLM 生成文本越来越接近人类文本，传统检测方法要么需要训练分类器、迁移性差；要么依赖 likelihood / entropy 等全局统计，在黑盒代理模型不匹配时不稳定；还有一些方法需要对每个输入做扰动或重生成，计算成本很高。作者发现：更稳定的信号不在单个 token 的概率大小，而在 token surprisal 的动态变化模式里。

**Insight：**
 作者提出一个直观想法：不要只看一句话“整体像不像 AI 写的”，而要看它的“惊讶节奏”。LLM 生成文本常出现一种 **recovery pattern**：遇到高 surprisal token 后，很快回到低 surprisal、可预测 token。SurpMark 把 token surprisal 离散成几个状态，再观察这些状态如何转移，就像给文本画一条“可预测性心电图”。人类文本和机器文本的转移节奏不同，因此可以用这个动态模式区分二者。

**任务：**
 用于黑盒检测 LLM 生成文本。作者提出 **SurpMark**：先用一个 proxy LM 计算文本 token\-level surprisal，再用 k\-means 把 surprisal 分成若干状态，构建一阶 Markov transition matrix；离线阶段分别构建 human / machine reference transition matrices，在线阶段对测试文本计算 transition matrix，并用 **Generalized Jensen\-Shannon Divergence（GJS）** 比较它更接近 human 还是 machine。实验覆盖 XSum、WritingPrompts、SQuAD、WMT19、HC3、DetectRL、DAIGT、Dolly，生成模型包括 GPT\-2XL、GPT\-J、GPT\-NeoX、OPT、Llama、Gemma、Gemini、GPT\-4\.1\-mini、GPT\-5\-Chat。结果显示 SurpMark 在黑盒、跨域、混合生成器、非英文、改写攻击和低 FPR 场景下都优于或接近强基线，并且不需要每个输入重新生成样本，推理成本更低。


<a id="e-009"></a>

<a id="e-009"></a>

### E-009. [Depression and Anxiety Characterization and Detection with Multimodal Deep Learning](https://www.nature.com/articles/s44220-026-00632-6) (子刊)

**发现问题：**
 抑郁和焦虑很难只靠单一数据判断：文本可能受文化表达影响，生理信号可能把焦虑和普通压力混淆，临床量表和访谈又成本高、难大规模使用。作者总结发现：多模态深度学习虽然能融合文本、音频、视频、生理信号和脑影像，但目前仍受限于数据规模小、模态缺失、数据偏差、隐私限制和临床验证不足。

**Insight：**
 作者的核心观点是：心理疾病不是只藏在一句话、一张脑图或一个生理指标里，而是分散在“脑—行为—环境”的多层信号中。多模态深度学习就像把多个观察窗口合在一起：文本看语言情绪，音频看语速和音调，视频看表情和姿态，EEG/fMRI 看神经活动，问卷和临床数据提供诊断背景。只有把这些信号对齐和融合，才更可能捕捉抑郁和焦虑的真实状态。

**任务：**
 用于综述多模态深度学习在抑郁和焦虑表征、筛查和诊断中的进展。文章总结了 CNN、RNN/LSTM、Transformer、GNN 在不同模态中的作用，并比较 early / intermediate / late fusion 等融合策略；覆盖 DAIC\-WOZ、E\-DAIC、D\-vlog、LMVD、MODMA、REST\-meta\-MDD、MMPsy、ENIGMA 等数据集。作者还总结未来方向：构建更大规模和跨文化数据集，处理缺失模态和数据偏差，利用 federated learning 解决隐私与数据孤岛问题，引入 foundation models / transfer learning / contrastive fusion / explainable AI，并通过临床试验验证模型可靠性。




<a id="e-010"></a>

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


<a id="e-018"></a>

### E-018. [Extracting Training Data from Diffusion Language Models via Infilling](https://arxiv.org/pdf/2605.24173)

**发现问题：**
 现有训练数据抽取研究主要沿用自回归语言模型的 prefix-conditioned extraction：给模型一段前缀，看它是否续写出训练样本。但扩散语言模型不是严格从左到右生成，而是可以在任意位置对 masked tokens 去噪和补全。因此，只用前缀探测 DLM 的记忆泄露风险，会系统性低估它们通过中间、边缘、随机位置或敏感实体补全而泄露训练数据的能力。

**Insight：**
 论文的核心 insight 是：评估 DLM 记忆与数据泄露，必须匹配它的双向补全归纳偏置。作者提出 **infilling extraction**，把训练样本中的任意位置按 binary mask 遮掉，让 DLM 根据未遮掉的上下文重构被遮部分；如果重构回原训练序列，就视为抽取成功。这个协议包含 prefix-only probing，但比它更一般。实验显示，mask geometry 本身决定可抽取性：edge-conditioned masks 最多能比 prefix-conditioned masks 多抽取约 3 倍的逐字训练序列；双向上下文还打开了自回归模型不具备的泄露通道，例如从 response 反推 user prompt，或在已有脱敏文本的情况下补回被遮盖的邮箱等 PII。

**任务：**
 这篇论文用于系统评估扩散语言模型的训练数据泄露与隐私风险。作者在 LLaDA-8B 和 Dream-7B 上，覆盖 five extraction modes、full fine-tuning / LoRA / SFT 三种训练暴露方式，以及 MIMIR Pile、Enron email、Tulu3 三类语料，分别测试逐字泄露、PII 补全和 instruction tuning 场景下的 prompt/response 泄露。结果表明，DLM 的泄露风险不能只靠传统前缀抽取来判断；解码步数、semi-autoregressive block size、temperature、remasking strategy 等推理参数会显著影响抽取表现，而后续 SFT 也不能完全消除先前训练阶段形成的记忆。小红书来源是二手分享，已按 arXiv 公开论文页信息为准收录。
