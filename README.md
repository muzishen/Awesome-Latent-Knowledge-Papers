# Awesome Latent Knowledge Papers
A curated reading list on latent knowledge in large models, organized into three bilingual themes.
## Topics
| Topic | File | Scope |
|---|---|---|
| D. 发现与探测 / Discovery & Probing | [discovery_probing.md](discovery_probing.md) | 23 papers |
| I. 干预和转移 / Intervention & Transfer | [intervention_transfer.md](intervention_transfer.md) | 26 papers |
| E. 评估与校准 / Evaluation & Calibration | [evaluation_calibration.md](evaluation_calibration.md) | 17 papers |

## Paper Overview

### D. 发现与探测 / Discovery & Probing

| ID | Paper | Year | Venue | Notes |
|---|---|---:|---|---|
| D-001 | [How Do Transformers Learn to Associate Tokens](discovery_probing.md#d-001) | 2026 | ICLR 2026 | Token 关联形成 |
| D-002 | [What Do Language Models Learn and When? The Implicit Curriculum Hypothesis](discovery_probing.md#d-002) | 2026 | arXiv preprint | 能力隐式课程 |
| D-003 | [Transformer layers as painters](discovery_probing.md#d-003) | 2025 | AAAI | 层顺序鲁棒性 |
| D-004 | [LLM Safety From Within](discovery_probing.md#d-004) | 2026 | arXiv preprint | 内部安全神经元 |
| D-005 | [LLMs Encode Harmfulness and Refusal Separately](discovery_probing.md#d-005) | 2025 | arXiv preprint | 有害性与拒绝分离 |
| D-006 | [What do your logits know?](discovery_probing.md#d-006) | 2026 | arXiv preprint | Logits 信息泄露 |
| D-007 | [Convergent Evolution: How Different Language Models Learn Similar Number Representations](discovery_probing.md#d-007) | 2026 | arXiv preprint | 数字表示几何 |
| D-008 | [Task-Driven Subspace Decomposition for Knowledge Sharing and Isolation in LoRA-based Continual Learning](discovery_probing.md#d-008) | 2026 | ICML 2026 | LoRA 子空间分解 |
| D-009 | [Last-Layer-Centric Feature Recombination](discovery_probing.md#d-009) | 2026 | arXiv preprint | 最后层几何锚点 |
| D-010 | [Beyond Outliers: A Data-Free Layer-wise Mixed-Precision Quantization Approach Driven by Numerical and Structural Dual-Sensitivity](discovery_probing.md#d-010) | 2026 | arXiv preprint | 结构感知量化 |
| D-011 | [Large Language Models are Universal Reasoners for Visual Generation](discovery_probing.md#d-011) | 2026 | arXiv preprint | LLM 引导视觉生成 |
| D-012 | [The Cylindrical Representation Hypothesis for Language Model Steering](discovery_probing.md#d-012) | 2026 | arXiv preprint | 圆柱表示 steering |
| D-013 | [Disentangling Mathematical Reasoning in LLMs](discovery_probing.md#d-013) | 2026 | arXiv preprint | 数学推理分工 |
| D-014 | [Learning a Generative Meta-Model of LLM Activations](discovery_probing.md#d-014) | 2026 | arXiv preprint | 激活流形先验 |
| D-015 | [Vision Transformers Need More Than Registers](discovery_probing.md#d-015) | 2026 | arXiv preprint | ViT 背景捷径 |
| D-016 | [What Happens Inside Agent Memory? Circuit Analysis from Emergence to Diagnosis](discovery_probing.md#d-016) | 2026 | arXiv preprint | Agent 记忆电路 |
| D-017 | [Rethinking RL for LLM Reasoning: It’s Sparse Policy Selection, Not Capability Learning](discovery_probing.md#d-017) | 2026 | arXiv preprint | RL 稀疏策略选择 |
| D-018 | [A Single Neuron Is Sufficient to Bypass Safety Alignment in Large Language Models](discovery_probing.md#d-018) | 2026 | arXiv preprint | 单神经元安全绕过 |
| D-019 | [Compute Optimal Tokenization](discovery_probing.md#d-019) | 2026 | arXiv preprint | 字节级 scaling |
| D-020 | [The Truth Lies Somewhere in the Middle (of the Generated Tokens)](discovery_probing.md#d-020) | 2026 | arXiv preprint | 生成 token 表示 |
| D-021 | [Reasoning Emerges from Constrained Inference Manifolds in Large Language Models](discovery_probing.md#d-021) | 2026 | arXiv preprint | 推理流形健康度 |
| D-022 | [When Looking Is Not Enough: Visual Attention Structure Reveals Hallucination in MLLMs](discovery_probing.md#d-022) | 2026 | arXiv preprint | 视觉注意力幻觉 |
| D-023 | [Mechanistic Data Attribution: Tracing the Training Origins of Interpretable LLM Units](discovery_probing.md#d-023) | 2026 | arXiv preprint | 训练数据到电路 |
| D-024 | [The Geometry of Concepts: Sparse Autoencoder Feature Structure](discovery_probing.md#d-024) | 2025 | Entropy | SAE 概念几何 |

### I. 干预和转移 / Intervention & Transfer

| ID | Paper | Year | Venue | Notes |
|---|---|---:|---|---|
| I-001 | [MILR: Improving Multimodal Image Generation via Test-Time Latent Reasoning](intervention_transfer.md#i-001) | 2025 | arXiv preprint | 测试时 latent reasoning |
| I-002 | [Imitating the Truth: Attention-aware Truth-Guided Enhancement for Hallucination Mitigation in Large Vision-Language Models](intervention_transfer.md#i-002) | 2026 | ICLR 2026 | 真实注意力模仿 |
| I-003 | [When Safety Collides: Resolving Multi-Category Harmful Conflicts in Text-to-Image Diffusion via Adaptive Safety Guidance](intervention_transfer.md#i-003) | 2026 | arXiv preprint | 自适应安全引导 |
| I-004 | [Towards Identification and Intervention of Safety-Critical Parameters in Large Language Models](intervention_transfer.md#i-004) | 2026 | arXiv preprint | 安全关键参数 |
| I-005 | [Parameter Importance is Not Static](intervention_transfer.md#i-005) | 2026 | arXiv preprint | 动态参数重要性 |
| I-006 | [Next Concept Prediction in Discrete Latent Space Leads to Stronger Language Models](intervention_transfer.md#i-006) | 2026 | arXiv preprint | 下一个概念预测 |
| I-007 | [DINOv3 Beats Specialized Detectors: A Simple Foundation Model Baseline for Image Forensics](intervention_transfer.md#i-007) | 2026 | arXiv preprint | DINOv3 图像鉴伪 |
| I-008 | [Vision Banana](intervention_transfer.md#i-008) | 2026 | arXiv preprint | 生成式视觉理解 |
| I-009 | [ACE-Merging: Data-Free Model Merging with Adaptive Covariance Estimation](intervention_transfer.md#i-009) | 2026 | arXiv preprint | 无数据模型合并 |
| I-010 | [CAN HETEROGENEOUS LANGUAGE MODELS BE FUSED?](intervention_transfer.md#i-010) | 2026 | arXiv preprint | 异构模型融合 |
| I-011 | [Adopting a Human Developmental Visual Diet Yields Robust and Shape-Based AI Vision](intervention_transfer.md#i-011) | 2026 | Nature Machine Intelligence | 发育式视觉训练 |
| I-012 | [DGS-Net: Distillation-Guided Gradient Surgery for CLIP Fine-Tuning in AI-Generated Image Detection](intervention_transfer.md#i-012) | 2025 | arXiv preprint | CLIP 梯度手术 |
| I-013 | [PsychAdapter: Adapting LLMs to Reflect Traits, Personality, and Mental Health](intervention_transfer.md#i-013) | 2026 | npj Artificial Intelligence | 人格特质适配器 |
| I-014 | [Multilingual Safety Alignment via Self-Distillation](intervention_transfer.md#i-014) | 2026 | arXiv preprint | 多语言安全迁移 |
| I-015 | [Manifold Steering Reveals the Shared Geometry of Neural Network Representation and Behavior](intervention_transfer.md#i-015) | 2026 | arXiv preprint | 流形 steering |
| I-016 | [Don’t Retrain—Align](intervention_transfer.md#i-016) | 2026 | arXiv preprint | AR 到扩散对齐 |
| I-017 | [Correct When Paired, Wrong When Split](intervention_transfer.md#i-017) | TBD | GitHub PDF | 跨模态知识编辑 |
| I-018 | [Towards the Explainability of Protein Language Models](intervention_transfer.md#i-018) | 2025 | arXiv preprint | 蛋白 LM 可解释性 |
| I-019 | [Turning Drift into Constraint: Robust Reasoning Alignment in Non-Stationary Multi-Stream Environments](intervention_transfer.md#i-019) | 2025 | arXiv preprint | 共识推理对齐 |
| I-020 | [Orthogonal Model Merging](intervention_transfer.md#i-020) | 2026 | arXiv preprint | 正交模型合并 |
| I-021 | [EVA: Editing for Versatile Alignment against Jailbreaks](intervention_transfer.md#i-021) | TBD | TBD | Jailbreak 防御编辑 |
| I-022 | [ASGUARD: Activation-Scaling Guard to Mitigate Targeted Jailbreaking Attack](intervention_transfer.md#i-022) | 2025 | arXiv preprint | 激活缩放防御 |
| I-023 | [Evaluating and Steering Modality Preferences in Multi-modal LLMs](intervention_transfer.md#i-023) | 2025 | arXiv preprint | 模态偏好 steering |
| I-024 | [Toward Stable Value Alignment: Introducing Independent Modules for Consistent Value Guidance](intervention_transfer.md#i-024) | 2026 | arXiv preprint | 独立价值模块 |
| I-025 | [A Study on Hidden Layer Distillation for Large Language Model Pre-Training](intervention_transfer.md#i-025) | 2026 | arXiv preprint | 隐藏层蒸馏 |
| I-026 | [Model Spec Midtraining: Improving How Alignment Training Generalizes](intervention_transfer.md#i-026) | 2026 | arXiv preprint | Model Spec 中训练 |

### E. 评估与校准 / Evaluation & Calibration

| ID | Paper | Year | Venue | Notes |
|---|---|---:|---|---|
| E-001 | [Self-Distilled Reasoner: On-Policy Self-Distillation for Large Language Models](evaluation_calibration.md#e-001) | 2026 | arXiv preprint | 自蒸馏推理 |
| E-002 | [Language Models (Mostly) Know What They Know](evaluation_calibration.md#e-002) | 2022 | arXiv preprint | 自我知识校准 |
| E-003 | [Domain-Filtered Knowledge Graphs from Sparse Autoencoder Features](evaluation_calibration.md#e-003) | 2026 | arXiv preprint | SAE 知识图谱 |
| E-004 | [LLM DNA: Tracing Model Evolution via Functional Representations](evaluation_calibration.md#e-004) | 2026 | ICLR 2026 Oral | 模型功能 DNA |
| E-005 | [Locate, Steer, and Improve: A Practical Survey of Actionable Mechanistic Interpretability in LLMs](evaluation_calibration.md#e-005) | 2026 | arXiv preprint | 可行动 MI 综述 |
| E-006 | [From Parameter Dynamics to Risk Scoring](evaluation_calibration.md#e-006) | 2026 | arXiv preprint | 微调风险评分 |
| E-007 | [Learning Uncertainty from Sequential Internal Dispersion in Large Language Models](evaluation_calibration.md#e-007) | 2026 | arXiv preprint | 隐藏状态不确定性 |
| E-008 | [Black-Box Detection of LLM-Generated Text Using Generalized Jensen Shannon Divergence](evaluation_calibration.md#e-008) | 2025 | arXiv preprint | Surprisal 转移检测 |
| E-009 | [Depression and Anxiety Characterization and Detection with Multimodal Deep Learning](evaluation_calibration.md#e-009) | 2026 | Nature Mental Health | 多模态心理健康综述 |
| E-010 | [Restoring Exploration after Post-Training: Latent Exploration Decoding for Large Reasoning Models](evaluation_calibration.md#e-010) | 2026 | arXiv preprint | latent 探索解码 |
| E-011 | [Information Flow Reveals When to Trust Language Models](evaluation_calibration.md#e-011) | TBD | OpenReview | 信息流可信度 |
| E-012 | [Tracing Uncertainty in Language Model “Reasoning”](evaluation_calibration.md#e-012) | 2026 | arXiv preprint | 推理不确定性轨迹 |
| E-013 | [Towards Generation-Efficient Uncertainty Estimation in Large Language Models](evaluation_calibration.md#e-013) | 2026 | arXiv preprint | 早期不确定性估计 |
| E-014 | [Evaluating the Statistical Realism of LLM-generated Social Science Data](evaluation_calibration.md#e-014) | 2026 | PNAS | 社会数据统计真实性 |
| E-015 | [Into the Gray Zone: Domain Contexts Can Blur LLM Safety Boundaries](evaluation_calibration.md#e-015) | 2026 | arXiv preprint | 安全灰区上下文 |
| E-016 | [Towards Intrinsic Interpretability of Large Language Models: A Survey of Design Principles and Architectures](evaluation_calibration.md#e-016) | 2026 | arXiv preprint | 内生可解释性综述 |
| E-017 | [Assessing the Creativity of Large Language Models: Testing, Limits, and New Frontiers](evaluation_calibration.md#e-017) | 2026 | arXiv preprint | 创造力评估有效性 |
