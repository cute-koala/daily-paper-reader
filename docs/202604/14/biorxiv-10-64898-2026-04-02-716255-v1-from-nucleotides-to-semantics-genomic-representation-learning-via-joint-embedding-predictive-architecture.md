---
title: "From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture"
title_zh: 从核苷酸到语义：基于联合嵌入预测架构的基因组表征学习
authors: "Wang, C., Qi, Q., Sun, H., Zhuang, Z., He, B., Liu, S., Liao, J., Wang, J."
date: 2026-04-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.02.716255v1.full.pdf"
tags: ["query:q2"]
score: 10.0
evidence: 基于联合嵌入预测架构的基因组表示学习框架
tldr: 解码基因组序列中的调控语法是计算生物学的核心目标。现有模型多将DNA视为语言进行预训练，但DNA缺乏明确语义边界且含进化噪声，导致核苷酸级重建计算开销大、表征判别力有限。本文提出GenoJEPA框架，基于联合嵌入预测架构，结合连续分块与语义对齐，将优化重点从局部碱基重建转向潜在空间语义对齐。该方法在55个下游任务中表现出强大表征能力和稳健泛化性，同时降低参数量与计算成本；其冻结语义向量支持轻量级无GPU分类器取得有竞争力的精度。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-001.webp\", \"caption\": \"Fig. 3 GenoJEPA achieves competitive performance with end-to-end finetuning. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the overall performance of GenoJEPA and the baselines across all benchmarks. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show the critical difference diagrams for finetuning and probing performance across all benchmarks. Statistical significance is summarized with the Friedman test at p = 0.05 followed by the Nemenyi post-hoc test at p = 0.05 on the task-level representative scores. The average rank and significance are reported from these mean scores. Black horizontal lines indicate no significant difference between methods. (d), (e), and (f) show finetuning performance for each task within the three benchmarks. Blue circles denote the mean score for each task, and red diamonds denote the average performance across all tasks within each benchmark.\", \"page\": 7, \"index\": 1, \"width\": 813, \"height\": 570}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-002.webp\", \"caption\": \"Fig. 5 GenoJEPA exhibits strong few-shot capabilities and feature versatility. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows probing performance for GenoJEPA and the baselines at different training-data scales across all benchmarks. Within each fold, the training and validation sets are stratified at proportions from 10% to 50% for each label while the test set is kept unchanged. Logistic regression with average pooling is used to assess the data efficiency of each method. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show probing performance under different pooling strategies and classifiers across all benchmarks. The boxplots summarize the distribution of representative scores across 55 tasks from all benchmarks. The center line denotes the median. The box limits denote the first and third quartiles. The whiskers denote the full data range.\", \"page\": 10, \"index\": 2, \"width\": 812, \"height\": 428}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-003.webp\", \"caption\": \"Fig. 4 GenoJEPA demonstrates favourable computational and memory efficiency. (a), (c), (e), and (g) report training time in ms, training memory in MB, inference time in ms, and inference memory in MB, respectively, for GenoJEPA and baselines with fewer than 10M parameters across different sequence lengths. (b), (d), (f), and (h) report the same metrics for GenoJEPA and baselines with more than 50M parameters. Experiments are conducted with a batch size of 1 on an A800 80 GB GPU. Each experiment is repeated for 10 epochs, and mean values are reported. In each epoch, the first 10 steps are excluded to remove cold-start effects. Average metrics are then computed over the next 100 steps. Both axes are shown on a logarithmic scale. Vertical dashed lines indicate sequence lengths that exceed model support or require memory beyond GPU capacity.\", \"page\": 8, \"index\": 3, \"width\": 815, \"height\": 574}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-004.webp\", \"caption\": \"Fig. 1 GenoJEPA learns genomic representations via joint-embedding prediction. (a) shows the pretraining framework. The input DNA sequence is split into non-overlapping patches, linearly projected into dense embeddings, and processed by a Transformer encoder. Token embeddings are then averaged to obtain a sequence representation. Following the LeJEPA formulation, the sequence is augmented into multiple local and global views through random cropping. GenoJEPA is optimized with an invariance loss that aligns semantic features across views together with a SIGReg loss that prevents representation collapse. (b) shows the downstream adaptation strategies for genomic tasks such as functional element identification. In resourcelimited settings, the pretrained encoder is frozen and the resulting sequence embeddings are passed to a lightweight task head for probing. In accuracy-sensitive settings, the entire GenoJEPA model is finetuned end to end together with a task head.\", \"page\": 4, \"index\": 4, \"width\": 815, \"height\": 469}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-005.webp\", \"caption\": \"Fig. 2 GenoJEPA maintains highly discriminative features under probing evaluation. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the probing win-loss comparison between GenoJEPA and the baselines across all benchmarks. A paired Wilcoxon signed-rank test at p = 0.05 is applied to the fold-wise test scores as a stability-aware paired comparison. The number of wins, ties, and losses is reported across 55 tasks from three benchmarks. (b) shows probing performance for each benchmark. The average and median performance across all tasks within each benchmark are reported from the representative scores. (c) shows task-level probing performance. On the horizontal axis, blue labels denote the Genomic Benchmarks, red labels denote the GUE Benchmarks, and green labels denote the Nucleotide Transformer Tasks.\", \"page\": 5, \"index\": 5, \"width\": 815, \"height\": 645}]"
motivation: 现有基因组基础模型大多将DNA视为语言并采用自然语言处理的预训练目标，但DNA序列缺乏明确的语义边界且包含大量进化噪声，导致计算开销大、判别能力有限，且下游任务依赖昂贵的微调。
method: 该方法基于联合嵌入预测架构，结合连续分块与语义对齐，将优化目标从局部碱基重建转向潜在空间的语义对齐。
result: 在55个下游任务中，GenoJEPA展现出强大的表征能力和稳健的泛化性，同时减少了参数数量和计算成本；其生成的冻结语义向量支持轻量级无GPU分类器达到有竞争力的准确率。
conclusion: 该研究表明，GenoJEPA为高效训练和大规模基因组基础模型的广泛应用提供了一条实用路径。
---

## 摘要
解码基因组序列中编码的调控语法是计算生物学的核心目标。现有大多数基因组基础模型将DNA视为一种语言，并采用自然语言处理的预训练目标。然而，DNA序列缺乏明确的语义边界且包含大量进化噪声。在低维输入空间中进行核苷酸级重建可能增加计算开销，并产生判别能力有限的表征。下游任务通常依赖于昂贵的微调，这限制了许多生物学实验室的实际应用。本文提出GenoJEPA，一种基于联合嵌入预测架构的基因组表征学习框架。GenoJEPA将连续分块与语义对齐相结合，将优化从局部碱基重建转向潜在空间的语义对齐。在55项下游任务中，GenoJEPA展现出强大的表征能力和稳健的泛化性，同时减少了参数量和计算成本。由冻结的GenoJEPA生成的语义向量支持轻量级无GPU分类器实现具有竞争力的准确度。这些结果为高效训练和大规模基因组基础模型的广泛应用提供了一条实用路径。

## Abstract
Decoding the regulatory syntax encoded in genomic sequences is a central objective in computational biology. Most existing genomic foundation models treat DNA as a language and adopt pretraining objectives from natural language processing. DNA sequences, however, lack explicit semantic boundaries and contain substantial evolutionary noise. Nucleotide-level reconstruction in a low-dimensional input space can therefore increase computational overhead and may yield representations with limited discriminative capacity. Downstream tasks often depend on expensive finetuning, which restricts practical use in many biology laboratories. Here we present GenoJEPA, a genomic representation learning framework based on joint-embedding predictive architecture. GenoJEPA combines continuous patching with semantic alignment, shifting the optimization from local base reconstruction to semantic alignment in latent space. Across 55 downstream tasks, GenoJEPA shows strong representational capacity and robust generalization while reducing parameter count and computational cost. The resulting semantic vectors from frozen GenoJEPA support lightweight GPU-free classifiers to achieve competitive accuracy. These results suggest a practical route towards efficient training and broad application of larger-scale genomic foundation models.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将对这篇题为《From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture》的预印本论文进行结构化、深入且客观的总结。

# 论文总结：GenoJEPA——基于联合嵌入预测架构的基因组表征学习

## 1. 核心问题与整体含义
*   **研究背景**：解码基因组序列中的调控语法是计算生物学的核心挑战。当前主流的基因组基础模型（如DNABERT-2、NT-v2）大多借鉴自然语言处理范式，将DNA视为“语言”，采用掩码语言建模或下一词预测等目标进行预训练。
*   **核心问题**：
    *   **类比不当**：DNA序列与人类语言存在本质差异。DNA缺乏明确的语义边界（如单词），且包含大量中性进化噪声，信息密度较低，更像自然图像。
    *   **目标偏差**：基于核苷酸级重建的预训练目标（如MLM）会迫使模型拟合高频率但功能相关性低的局部细节和噪声，可能导致学到的表征判别能力有限。
    *   **应用瓶颈**：上述模型学到的“冻结”表征质量不高，下游任务严重依赖对整个模型进行昂贵的全参数微调，这在计算资源有限的生物学实验室中构成了实际应用障碍。
*   **整体含义**：本文提出了一种新的基因组表征学习范式（GenoJEPA），旨在通过改变预训练目标（从重建输入转向对齐语义）和输入表示方式（连续分块），学习到更具判别力、更易于迁移的基因组语义特征，从而降低下游应用的计算门槛。

## 2. 方法论
*   **核心思想**：将计算机视觉中成功的**联合嵌入预测架构 (JEPA)** ，特别是其理论改进版本 **LeJEPA** ，应用于基因组序列建模。其核心是放弃在低维输入空间（核苷酸序列）的重建，改为在高维潜在空间中对齐不同数据增强视图的语义特征。
*   **关键技术细节**：
    1.  **连续分块 (Continuous Patching)**：
        *   替代传统的k-mer或BPE分词。将原始DNA序列划分为不重叠的固定长度片段（如16个核苷酸为一个“块”）。
        *   每个块内的核苷酸通过一个可学习的嵌入层映射为连续的稠密向量，再通过线性投影得到块的表示。这避免了离散词汇表膨胀，保留了块内的生化依赖关系，并显著压缩了序列长度。
    2.  **骨干网络 (Backbone)**：采用基于ModernBERT的双向Transformer编码器，使用RoPE位置编码。设计了两个规模版本：轻量版 GenoJEPA-T (6M参数) 和基础版 GenoJEPA-B (52M参数)。
    3.  **多视图与损失函数 (Multi-view & Loss)**：
        *   **数据增强**：对同一序列进行随机裁剪，生成多个“全局视图”（裁剪比例65%-80%）和“局部视图”（35%-40%）。
        *   **不变性损失 (L_Invariance)**：将所有视图（全局和局部）的表征向所有全局视图表征的均值对齐（使用均方误差）。
        *   **防坍缩正则化 (SIGReg Loss, L_SIGReg)**：采用LeJEPA提出的“草图化各向同性高斯正则化”。该损失通过匹配经验特征函数，引导潜在空间中的特征分布趋向于各向同性高斯分布，从而防止所有表征坍缩为同一向量，无需动量编码器等启发式设计。
        *   **总损失**: `L_total = (1 - α) * L_Invariance + α * L_SIGReg` （α=0.05）。

## 3. 实验设计
*   **预训练数据**：来自850个代表性物种的多物种基因组语料库（约1930亿核苷酸），与Nucleotide Transformer-v2使用的语料相同。
*   **评估基准与任务**：
    *   在三个广泛使用的基准上进行评估，共涵盖55项下游任务：
        1.  Genomic Benchmarks: 跨物种序列分类、调控元件识别等9项任务。
        2.  GUE Benchmarks: 转录因子结合位点预测、启动子检测、RNA剪接位点识别等28项任务。
        3.  Nucleotide Transformer Tasks: 人类表观遗传标记预测、增强子检测等18项任务。
*   **评估协议**：
    *   **探测评估 (Probing)**：冻结预训练骨干权重，仅使用逻辑回归等轻量级分类器在提取的特征上进行训练。用于直接评估预训练表征的质量。
    *   **微调评估 (Finetuning)**：对整个模型进行端到端微调。用于评估模型适应特定任务后的上限性能。
    *   **主要指标**: Matthews相关系数 ，适用于类别不平衡的数据集。
*   **对比基线**: HyenaDNA, CaduceusPh, GROVER, DNABERT-2, NT-v2。这些基线覆盖了不同的分词策略（单核苷酸、BPE、k-mer）、骨干架构（Transformer, Hyena, Mamba）和参数量级。

## 4. 资源与算力
文中明确说明了预训练的算力需求：
*   GenoJEPA-T (6M参数): 在单张RTX 3090 (24GB) GPU上训练10万步，耗时约12小时。
*   GenoJEPA-B (52M参数): 在单张A800 (80GB) GPU上训练50万步，耗时约150小时。

## 5. 实验数量与充分性
实验设计非常全面和系统：
*   **主实验**: 
    - Probing vs Finetuning性能对比（55个任务）。
    - Win/Loss统计显著性分析（配对Wilcoxon检验）。
    - Friedman-Nemenyi检验排名分析。
*   **效率分析**: 
    -系统地测量了不同序列长度下的训练/推理时间和内存占用。
*   **特性分析**: 
    -少样本学习能力（10%-50%标注数据比例）。
    -不同池化策略(CLS, Avg, Max)的影响。
    -不同分类器(KNN, LogReg, CatBoost)的影响。
*   **[附录]消融实验**: 
    多达23组消融实验分析了关键设计选择的影响:
    1.数据增强(多物种vs单物种、裁剪尺度/数量、随机突变/反向互补)。
    2.架构设计(分块大小/步长、嵌入维度、池化策略、投影头设计)。
    3.目标函数(对齐准则、SIGReg超参数)。
    4.优化设置(学习率、权重衰减)。

总体而言，实验数量充足且设计严谨。采用了统一的评估协议（尤其是Probing），减少了因微调策略不同带来的偏差；对比了当前最具代表性的基线；并通过详尽的消融研究验证了各个组件的有效性。

##6 .主要结论与发现
1.	强大的冻结表征能力: GenoJEPA学到的冻结表征质量显著优于基线模型。GenoJEPA-B在Probing评估中平均MCC最高(0 .589)，且以仅52M参数量击败了参数量近10倍(494M)、使用相同数据预训练的NT-v2 。
2	高效的参数与计算效率: GenoJEPA以更少的参数实现了竞争甚至更优的性能 。在计算效率上 ，其连续分块策略带来了稳定的内存和时间开销 ，在实际测试的大多数序列长度范围内 ，优于许多理论复杂度更低的新兴架构(HyenaDNA , CaduceusPh)。
3	优秀的数据效率:在少样本设置下 ，GenoJEMA仅用10%的训练数据即可达到其他基线使用50%甚至100%数据时的性能水平 。
4	灵活的下游适配:无论是资源受限场景下的轻量级探测 ，还是精度敏感场景下的全参数微调 ，GenoJE PA均能提供有竞争力的解决方案 。其冻结特征支持简单的线性分类器取得良好效果 。

##7 .优点
1	范式创新:首次将LeJE PA这一理论驱动的自监督学习范式系统性地引入基因组表示学习领域 ，为克服NLP类比局限提供了新思路 。
2	实用导向:整个工作围绕降低实际应用门槛展开 。强调冻结表征的质量 、计算效率和少样本能力 ，直接回应了生物学实验室资源有限的核心痛点 。
3	实验扎实:评测基准全面 、对比基线有代表性 、分析维度多(性能 、效率 、数据需求 、鲁棒性)。附录中大量的消融实验增强了结论的可信度 。
4	方法简洁有效:结合连续分块和潜在空间对齐的核心思想清晰 ，且最终模型架构相对简洁 ，没有引入过多复杂的启发式模块 。

##8 .不足与局限
1	序列长度限制:预训练使用的最大序列长度为4096 bp ，这虽然覆盖了许多基因水平的任务 ，但对于需要更长程依赖的分析(如拓扑关联域边界识别)可能不足 。作者指出这是未来扩展的方向 。
2	模型规模有限:最大的GenoJE PA-B仅有52M参数 。尽管在小规模上证明了有效性 ，但更大规模模型的缩放规律及其潜力尚未探索 。文中提及这是未来工作 。
3	任务类型偏向性:评测主要集中在分类任务上(调控元件识别 、表观标记预测等)。对于生成式任务或需要更精细位置信息的任务(如变异效应预测)的性能尚未验证 。
4	理论继承性而非原创性:**论文的核心理论框架(L eJE PA )是继承自先前工作[23]。本文的主要贡献在于将该框架成功适配并验证于基因组领域 ，而非提出全新的理论基础 。

**(完)**

好的，我将从您提供的“（完）”之前继续，对论文的讨论、未来工作、以及整体评价进行补充总结。

## 9. 讨论与未来方向
*   **范式有效性的解释**：论文深入讨论了GenoJEPA成功的原因。核心在于其预训练目标与基因组数据的特性更匹配：
    1.  **对齐语义而非重建噪声**：JEPA的目标是学习对数据增强不变的语义特征，这迫使模型忽略序列中的随机突变和中性进化噪声，专注于捕捉功能相关的保守模式。
    2.  **连续分块捕获局部依赖**：连续分块将离散的核苷酸序列转化为连续的“视觉块”，允许模型学习块内复杂的生化相互作用（如二核苷酸频率、短模体），而无需像k-mer或BPE那样枚举所有可能性。
    3.  **正则化防止过拟合**：SIGReg损失有效防止了表征坍缩，确保了潜在空间的丰富性和判别力。
*   **与NLP范式的对比**：作者明确指出，基于重建（MLM）的NLP范式可能不是基因组建模的最佳选择。基因组更像一个“低信噪比”的信号处理问题，而JEPA的对比/对齐思想更擅长从中提取稳健的特征。
*   **明确的未来工作**：
    1.  **扩展序列长度**：开发能够处理更长序列（如>10k bp）的版本，以研究长程调控和染色质结构。
    2.  **扩大模型规模**：探索更大参数量（如百亿级）的GenoJEPA模型，研究其涌现能力和缩放规律。
    3.  **拓展任务类型**：将模型应用于生成任务（如调控序列设计）、回归任务（如表达量预测）以及需要单核苷酸精度的任务（如遗传变异解读）。
    4.  **整合多模态信息**：将DNA序列表征与表观基因组学、3D结构等多模态数据结合，构建更全面的基因组理解模型。

## 10. 整体评价与意义
*   **学术价值**：
    *   **提供了新的方法论视角**：成功地将计算机视觉中先进的表示学习范式迁移到基因组学，挑战了当前占主导地位的“DNA-as-Language”类比，为领域发展提供了新的技术路径。
    *   **强调了目标函数的重要性**：清晰地论证了预训练目标的设计比模型架构或分词策略更能决定所学表征的质量，这一见解具有普适性。
    *   **设立了实用的评估标准**：大力倡导并实践以“冻结表征质量”和“探测评估”作为核心评测指标，推动领域关注模型的实际可用性和迁移效率。
*   **应用潜力**：
    *   **降低了AI在基因组学中的应用门槛**：轻量级模型、高效的冻结特征和优秀的数据效率，使得资源有限的生物学实验室能够更容易地部署和使用先进的深度学习模型进行发现研究。
    *   **为功能基因组学提供强大工具**：所学习的高质量、语义化的DNA片段表示，可用于改进调控元件发现、非编码变异解释、跨物种保守性分析等众多任务。
*   **局限性重申与客观定位**：
    *   本文是一项出色的“工程化创新”和“领域适配”研究。它没有提出全新的基础理论框架（LeJEPA），但通过精心的设计、系统的实验和深入的分析，证明了该框架在解决基因组学核心挑战上的巨大优势和潜力。
    *   其实验结果扎实，结论令人信服。所提出的GenoJEPA作为一个强大、高效且用户友好的基础模型，有望成为计算生物学工具箱中的一个重要新工具。

## 总结
本文《From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture》是一篇高质量的研究工作。它敏锐地指出了当前基因组基础模型的局限性，并创新性地引入了LeJEPA框架与连续分块策略来应对这些挑战。通过全面、严谨的实验证明，GenoJEPA能够学习到判别力更强、更易于迁移的基因组语义表征，同时在参数效率、计算效率和数据效率方面表现优异。这项工作不仅为基因组表示学习提供了一个新的强基线模型，更重要的是为整个领域思考“如何为DNA数据设计合适的自监督学习目标”提供了宝贵的范例和启示。

（完）
