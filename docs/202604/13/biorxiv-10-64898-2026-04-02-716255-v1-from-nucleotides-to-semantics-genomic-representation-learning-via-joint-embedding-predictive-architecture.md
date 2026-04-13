---
title: "From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture"
title_zh: 从核苷酸到语义：基于联合嵌入预测架构的基因组表征学习
authors: "Wang, C., Qi, Q., Sun, H., Zhuang, Z., He, B., Liu, S., Liao, J., Wang, J."
date: 2026-04-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.02.716255v1.full.pdf"
tags: ["query:q2"]
score: 9.0
evidence: 通过联合嵌入预测架构 (GenoJEPA) 进行基因组表示学习
tldr: 解码基因组序列中的调控语法是计算生物学的核心目标。现有模型多将DNA视为语言进行预训练，但DNA缺乏明确语义边界且含进化噪声，导致核苷酸级重建计算开销大、表征能力有限。本文提出GenoJEPA框架，基于联合嵌入预测架构，通过结合连续分块与语义对齐，将优化重点从局部碱基重建转向潜在空间语义对齐。该方法在55个下游任务中表现出强大的表征能力和泛化性，同时降低了参数量与计算成本；其生成的冻结语义向量可使轻量级无GPU分类器达到有竞争力的精度。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-001.webp\", \"caption\": \"Fig. 3 GenoJEPA achieves competitive performance with end-to-end finetuning. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the overall performance of GenoJEPA and the baselines across all benchmarks. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show the critical difference diagrams for finetuning and probing performance across all benchmarks. Statistical significance is summarized with the Friedman test at p = 0.05 followed by the Nemenyi post-hoc test at p = 0.05 on the task-level representative scores. The average rank and significance are reported from these mean scores. Black horizontal lines indicate no significant difference between methods. (d), (e), and (f) show finetuning performance for each task within the three benchmarks. Blue circles denote the mean score for each task, and red diamonds denote the average performance across all tasks within each benchmark.\", \"page\": 7, \"index\": 1, \"width\": 813, \"height\": 570}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-002.webp\", \"caption\": \"Fig. 5 GenoJEPA exhibits strong few-shot capabilities and feature versatility. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows probing performance for GenoJEPA and the baselines at different training-data scales across all benchmarks. Within each fold, the training and validation sets are stratified at proportions from 10% to 50% for each label while the test set is kept unchanged. Logistic regression with average pooling is used to assess the data efficiency of each method. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show probing performance under different pooling strategies and classifiers across all benchmarks. The boxplots summarize the distribution of representative scores across 55 tasks from all benchmarks. The center line denotes the median. The box limits denote the first and third quartiles. The whiskers denote the full data range.\", \"page\": 10, \"index\": 2, \"width\": 812, \"height\": 428}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-003.webp\", \"caption\": \"Fig. 4 GenoJEPA demonstrates favourable computational and memory efficiency. (a), (c), (e), and (g) report training time in ms, training memory in MB, inference time in ms, and inference memory in MB, respectively, for GenoJEPA and baselines with fewer than 10M parameters across different sequence lengths. (b), (d), (f), and (h) report the same metrics for GenoJEPA and baselines with more than 50M parameters. Experiments are conducted with a batch size of 1 on an A800 80 GB GPU. Each experiment is repeated for 10 epochs, and mean values are reported. In each epoch, the first 10 steps are excluded to remove cold-start effects. Average metrics are then computed over the next 100 steps. Both axes are shown on a logarithmic scale. Vertical dashed lines indicate sequence lengths that exceed model support or require memory beyond GPU capacity.\", \"page\": 8, \"index\": 3, \"width\": 815, \"height\": 574}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-004.webp\", \"caption\": \"Fig. 1 GenoJEPA learns genomic representations via joint-embedding prediction. (a) shows the pretraining framework. The input DNA sequence is split into non-overlapping patches, linearly projected into dense embeddings, and processed by a Transformer encoder. Token embeddings are then averaged to obtain a sequence representation. Following the LeJEPA formulation, the sequence is augmented into multiple local and global views through random cropping. GenoJEPA is optimized with an invariance loss that aligns semantic features across views together with a SIGReg loss that prevents representation collapse. (b) shows the downstream adaptation strategies for genomic tasks such as functional element identification. In resourcelimited settings, the pretrained encoder is frozen and the resulting sequence embeddings are passed to a lightweight task head for probing. In accuracy-sensitive settings, the entire GenoJEPA model is finetuned end to end together with a task head.\", \"page\": 4, \"index\": 4, \"width\": 815, \"height\": 469}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-005.webp\", \"caption\": \"Fig. 2 GenoJEPA maintains highly discriminative features under probing evaluation. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the probing win-loss comparison between GenoJEPA and the baselines across all benchmarks. A paired Wilcoxon signed-rank test at p = 0.05 is applied to the fold-wise test scores as a stability-aware paired comparison. The number of wins, ties, and losses is reported across 55 tasks from three benchmarks. (b) shows probing performance for each benchmark. The average and median performance across all tasks within each benchmark are reported from the representative scores. (c) shows task-level probing performance. On the horizontal axis, blue labels denote the Genomic Benchmarks, red labels denote the GUE Benchmarks, and green labels denote the Nucleotide Transformer Tasks.\", \"page\": 5, \"index\": 5, \"width\": 815, \"height\": 645}]"
motivation: 现有基因组基础模型通常将DNA视为语言并采用自然语言处理的预训练目标，但DNA缺乏明确的语义边界且包含大量进化噪声，导致计算开销大、表征判别能力有限，且下游任务依赖昂贵的微调。
method: 该方法结合了连续分块与语义对齐，将优化目标从局部碱基重建转向潜在空间的语义对齐。
result: 在55个下游任务中，GenoJEPA展现出强大的表征能力和稳健的泛化性，同时减少了参数量和计算成本；其生成的冻结语义向量支持轻量级无GPU分类器达到有竞争力的准确率。
conclusion: 该研究表明，GenoJEPA为高效训练和大规模基因组基础模型的广泛应用提供了一条实用路径。
---

## 摘要
解码基因组序列中编码的调控语法是计算生物学的核心目标。现有大多数基因组基础模型将DNA视为一种语言，并采用自然语言处理的预训练目标。然而，DNA序列缺乏明确的语义边界且包含大量进化噪声。在低维输入空间中进行核苷酸级重建可能增加计算开销，并产生判别能力有限的表征。下游任务通常依赖于昂贵的微调，这限制了许多生物学实验室的实际应用。本文提出GenoJEPA，一种基于联合嵌入预测架构的基因组表征学习框架。GenoJEPA将连续分块与语义对齐相结合，将优化从局部碱基重建转向潜在空间的语义对齐。在55项下游任务中，GenoJEPA展现出强大的表征能力和稳健的泛化性，同时减少了参数量和计算成本。由冻结的GenoJEPA生成的语义向量支持轻量级无GPU分类器实现具有竞争力的准确率。这些结果为高效训练和大规模基因组基础模型的广泛应用提供了一条实用路径。

## Abstract
Decoding the regulatory syntax encoded in genomic sequences is a central objective in computational biology. Most existing genomic foundation models treat DNA as a language and adopt pretraining objectives from natural language processing. DNA sequences, however, lack explicit semantic boundaries and contain substantial evolutionary noise. Nucleotide-level reconstruction in a low-dimensional input space can therefore increase computational overhead and may yield representations with limited discriminative capacity. Downstream tasks often depend on expensive finetuning, which restricts practical use in many biology laboratories. Here we present GenoJEPA, a genomic representation learning framework based on joint-embedding predictive architecture. GenoJEPA combines continuous patching with semantic alignment, shifting the optimization from local base reconstruction to semantic alignment in latent space. Across 55 downstream tasks, GenoJEPA shows strong representational capacity and robust generalization while reducing parameter count and computational cost. The resulting semantic vectors from frozen GenoJEPA support lightweight GPU-free classifiers to achieve competitive accuracy. These results suggest a practical route towards efficient training and broad application of larger-scale genomic foundation models.

---

## 论文详细总结（自动生成）

# 论文结构化总结：From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture

## 1. 核心问题与整体含义
*   **研究动机**：解码基因组序列中编码的调控语法是计算生物学的核心挑战。现有主流基因组基础模型（如DNABERT-2, NT-v2）大多借鉴自然语言处理范式，将DNA视为语言，采用掩码语言建模或下一词预测等目标进行预训练。
*   **核心问题**：这种类比存在根本性不匹配。DNA序列缺乏明确的语义边界，且包含大量进化噪声（如中性突变）。在低维输入空间进行精确的核苷酸级重建，会迫使模型将大量容量用于拟合与功能无关的噪声，导致学到的表征判别能力有限。这使得下游任务严重依赖昂贵的全参数微调，成为许多计算资源有限的生物学实验室的应用瓶颈。
*   **整体含义**：本文提出了一种新的基因组表征学习范式——**GenoJEPA**。它认为DNA序列在结构上更类似于自然图像（自然产生、低信噪比、无明确边界），因此借鉴计算机视觉中的联合嵌入预测架构，将优化目标从输入空间的局部重建转向潜在空间的语义对齐，旨在学习更具判别力、更易于迁移的冻结表征。

## 2. 方法论
*   **核心思想**：基于LeJEPA框架，通过在高维潜在空间中对齐同一序列的不同增强视图的语义特征，而非重建原始核苷酸序列，来学习稳健且可迁移的基因组表征。
*   **关键技术细节**：
    1.  **连续分块分词化**：
        *   摒弃传统的k-mer或BPE分词方法（易导致词汇表膨胀、对单核苷酸变异敏感）。
        *   将输入DNA序列划分为不重叠的核苷酸片段（`patch size=16`），通过线性投影直接映射为连续的稠密向量。
        *   优点：避免离散词汇表膨胀；压缩序列长度（降至1/16）；在连续空间中保留片段内的生化依赖关系。
    2.  **骨干网络**：基于ModernBERT架构的双向Transformer编码器，采用RoPE位置编码和偏置无关设计。构建了两个版本：
        *   **GenoJEPA-T (轻量版)**：6M参数。
        *   **GenoJEPA-B (基础版)**：52M参数。
    3.  **多视图增强与对齐目标**：
        *   **数据增强**：对每个序列样本应用随机裁剪，生成2个全局视图（裁剪比例65%-80%）和6个局部视图（35%-40%）。
        *   **不变性损失 (L_Invariance)**：将所有视图（全局和局部）的表征向全局视图表征的均值对齐（使用均方误差）。
    4.  **防坍缩正则化 (SIGReg)**：
        *   采用LeJEPA提出的“草图化各向同性高斯正则化”损失 (`L_SIGReg`)。
        *   理论动机：各向同性高斯分布对于未知下游任务的线性或非线性探针是最优的。
        *   实现方式：通过随机投影方向和高散化的经验特征函数匹配，引导潜在特征分布趋向标准高斯分布，无需动量编码器等启发式技巧。
    5.  **总损失函数**: `L_total = (1 - α) L_Invariance + α L_SIGReg` （本研究中 `α = 0.05`）。

## 3. 实验设计
*   **预训练数据**：来自850个代表性物种的多物种基因组语料库（与NT-v2相同），总计约1930亿个核苷酸。
*   **评估基准与任务**：
    1.  Genomic Benchmarks (9个子任务)：跨物种序列分类、调控元件识别等。
    2.  GUE Benchmarks (28个子任务)：转录因子结合位点预测、启动子检测、RNA剪接位点识别等。
    3.  Nucleotide Transformer Tasks (18个子任务)：人类组蛋白修饰、增强子、启动子预测等。
    *   共计55个下游分类任务。主要评估指标为马修斯相关系数(MCC)。
*   **对比基线方法**：
    *   HyenaDNA (7M): Hyena架构，单核苷酸分词，NTP目标。
    *   CaduceusPh (8M): Mamba架构(SSM)，单核苷酸分词，MLM目标。
    *   GROVER (87M): Transformer, BPE分词, MLM目标。
    *   DNABERT-2 (117M): Transformer, BPE分词, MLM目标。
    *   NT-v2 (494M): Transformer, 6-mer分词, MLM目标（与GenoJEPA使用相同预训练语料库）。
*   **评估协议**：
    *   **探针评估(Probing)** ：冻结预训练骨干权重，仅训练一个轻量级分类器（默认逻辑回归+平均池化），直接评估表征质量。这是本文的核心评估方式。
    *   **微调评估(Finetuning)** ：对整个模型进行端到端微调以追求最高精度。

## 4. 资源与算力
文中明确说明了预训练的算力需求：
*   GenoJEPA-T (6M参数)：在单张RTX 3090 GPU上训练100k步耗时约12小时。（批量大小256）
*   GenoJEPA-B (52M参数)：在单张A800 GPU上训练500k步耗时约150小时。（批量大小256）
这体现了该方法在计算上的高效性和可及性。

## 5. 实验数量与充分性
实验非常系统和充分：
1.  **主实验对比**: GenoJEPA-T/B vs.5个基线模型在55个任务上的探针和微调性能全面比较(图2,3)。
2.  **效率分析**:系统测量了不同模型在不同序列长度下的训练/推理时间和内存占用(图4)。
3.  **小样本能力**:测试了在不同比例(10%-50%)标注数据下的探针性能(图5a)。
4.  **特征通用性分析**:比较了不同池化策略(CLS/AVG/MAX)和不同分类器(KNN/LogReg/CatBoost)下的表现(图5b,c)。
5.  **(附录中)大量消融实验**:共23项消融研究(C部分)，涵盖数据增强策略、架构设计超参数(patch大小、滑动步长)、损失函数超参数(SIGReg权重)、优化设置等多个维度。

实验设计客观公平：
*   统一使用10折交叉验证并报告平均测试分数以减少随机性影响；
*   探针评估时对所有模型采用统一的平均池化和逻辑回归流程；
*   微调时为每个基线模型使用其官方推荐的最佳配置；
*   效率测试时统一硬件环境和测试协议。

##6 .主要结论与发现
1.**表征质量优异**:在探针评估中GenoJEPA-B取得了最佳整体性能其平均排名显著优于所有基线包括参数量近10倍于己且在相同语料库上预训练的NT-v这表明潜在空间语义对齐能产生判别力更强的冻结表征;
2.**参数量和计算效率高**:GenoJEPA-B仅用52M参数量就在多项任务上达到或超越了参数量大得多的基线模型的性能;同时其在训练和推理时的内存和时间开销也优于大多数对比模型;
3.**小样本能力强**:仅用10%的训练数据GenoJEPA就能达到其他基线用50%甚至100%数据才能达到的性能表明其学到的表征具有很高的数据效率;
4.**下游应用灵活**:学到的冻结表征能够支持简单的线性分类器取得良好效果降低了资源有限实验室的应用门槛;同时该模型也支持全参数微调以获得最高精度;
5.**理论指导实践**:基于LeJEPA框架的设计避免了传统自监督学习中常用的启发式防坍缩技巧使训练更加稳定和可解释;

##7 .优点
1.**范式创新**:首次将联合嵌入预测架构系统地应用于基因组表示学习挑战了主流NLP类比范式提出了更符合DNA本质的图像类比新思路;
2.**实用性强**:明确以“提供高质量冻结表征降低下游应用门槛”为目标其轻量级版本和小样本能力对资源有限的生物医学研究具有重要现实意义;
3.**实验全面系统**:覆盖了55个多样化的下游任务进行了详尽的性能效率和消融分析论证非常扎实;
4.**开源透明**:论文承诺将公开所有预处理代码训练代码和预处理后的数据集;

##8 .不足与局限
1.**上下文长度限制**:预训练使用的最大序列长度为4096bp这虽然覆盖了许多基因水平任务但不足以建模更长范围的依赖关系例如拓扑关联域边界识别作者指出这是未来扩展的方向;
2.**模型规模有限:**最大的GenoJEPA-B仅52M参数量尚未探索更大规模模型的缩放规律及其可能带来的性能提升;
3.**特定任务的局限性:**尽管整体表现优异但在某些特定任务上例如Hac表现仍不佳且个别任务如人类调控元件分类HyenaDNA表现更好表明没有一种架构在所有场景下都最优;
4.**生物学解释性:**论文侧重于工程性能和实用性对于学到的“语义”特征具体对应哪些生物学模式或基序缺乏深入的归因分析和可视化;

完

## 9. 潜在影响与未来方向
*   **对基因组基础模型领域的影响**：
    *   **范式转移**：挑战了将DNA视为“语言”的NLP类比主流，论证了将其视为“图像”的CV类比在表征学习上的优势，可能启发更多基于对比学习、特征对齐等非自回归目标的新模型。
    *   **效率优先**：证明了通过改进预训练目标，可以在更小的模型规模和更低的计算成本下获得卓越的冻结表征性能，为在资源受限环境中部署基因组AI模型提供了可行路径。
    *   **评估标准**：强调了“探针评估”（冻结表征质量）作为核心评估指标的重要性，推动领域不仅关注微调后的峰值性能，更关注模型学到的本质、可迁移的生物学知识。
*   **对生物医学研究的潜在价值**：
    *   **降低应用门槛**：高质量的冻结表征使得生物学家无需大量计算资源进行微调，即可利用预训练模型作为特征提取器，快速构建各种预测工具（如变异效应预测、调控元件发现）。
    *   **促进发现**：学到的稳健、语义化表征可能有助于识别新的功能模式或揭示序列-功能映射中未被充分认识的原则。
*   **未来研究方向**：
    1.  **扩展上下文长度**：开发能处理更长序列（如>100k bp）的版本，以研究染色质结构、长程调控等生物学问题。
    2.  **探索模型缩放**：将GenoJEPA框架扩展到百亿甚至千亿参数规模，研究其缩放规律与性能收益。
    3.  **融入多模态信息**：将序列表征与表观基因组学（如染色质可及性、组蛋白修饰）、3D结构或蛋白质结合数据相结合，进行多模态联合嵌入学习。
    4.  **增强可解释性**：开发工具对学到的潜在特征进行归因分析，可视化其对应的序列模式或生物学功能，建立从“语义特征”到具体生物学机制的桥梁。
    5.  **任务特定优化**：虽然追求通用表征，但可以探索针对特定重要任务（如罕见病致病突变解读）的轻量级适配策略。

## 10. 总结
本文提出的GenoJEPA是一个创新且实用的基因组表示学习框架。它通过借鉴计算机视觉中的联合嵌入预测架构（JEPA），成功地将优化焦点从精确的核苷酸重建转移到潜在空间的语义对齐。这种方法更契合DNA序列高噪声、无明确语义单元的特性。实验表明，GenoJEPA能以小得多的模型规模和计算成本，学习到判别力更强、数据效率更高、更易于迁移的冻结DNA序列表征。这项工作不仅为基因组基础模型提供了一种高效的新范式，也为计算资源有限的生物医学研究者利用最先进的AI模型提供了便利。其核心贡献在于实现了从“学习重建序列”到“学习理解功能”的理念转变。

（完）
