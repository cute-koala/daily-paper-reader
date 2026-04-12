---
title: "From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture"
title_zh: 从核苷酸到语义：基于联合嵌入预测架构的基因组表征学习
authors: "Wang, C., Qi, Q., Sun, H., Zhuang, Z., He, B., Liu, S., Liao, J., Wang, J."
date: 2026-04-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.02.716255v1.full.pdf"
tags: ["query:q2"]
score: 9.0
evidence: 通过联合嵌入预测架构进行基因组表示学习
tldr: 本研究提出GenoJEPA框架，旨在解决现有基因组基础模型因将DNA视为语言而面临的序列缺乏语义边界、进化噪声多、计算开销大等问题。该方法基于联合嵌入预测架构，结合连续分块与语义对齐技术，将优化重点从局部碱基重建转向潜在空间的语义对齐。在55个下游任务中验证了其强大的表征能力和泛化性，同时降低了参数数量和计算成本；生成的语义向量支持轻量级无GPU分类器达到竞争性准确度，为高效训练和大规模应用基因组基础模型提供了实用途径。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-001.webp\", \"caption\": \"Fig. 3 GenoJEPA achieves competitive performance with end-to-end finetuning. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the overall performance of GenoJEPA and the baselines across all benchmarks. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show the critical difference diagrams for finetuning and probing performance across all benchmarks. Statistical significance is summarized with the Friedman test at p = 0.05 followed by the Nemenyi post-hoc test at p = 0.05 on the task-level representative scores. The average rank and significance are reported from these mean scores. Black horizontal lines indicate no significant difference between methods. (d), (e), and (f) show finetuning performance for each task within the three benchmarks. Blue circles denote the mean score for each task, and red diamonds denote the average performance across all tasks within each benchmark.\", \"page\": 7, \"index\": 1, \"width\": 813, \"height\": 570}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-002.webp\", \"caption\": \"Fig. 5 GenoJEPA exhibits strong few-shot capabilities and feature versatility. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows probing performance for GenoJEPA and the baselines at different training-data scales across all benchmarks. Within each fold, the training and validation sets are stratified at proportions from 10% to 50% for each label while the test set is kept unchanged. Logistic regression with average pooling is used to assess the data efficiency of each method. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show probing performance under different pooling strategies and classifiers across all benchmarks. The boxplots summarize the distribution of representative scores across 55 tasks from all benchmarks. The center line denotes the median. The box limits denote the first and third quartiles. The whiskers denote the full data range.\", \"page\": 10, \"index\": 2, \"width\": 812, \"height\": 428}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-003.webp\", \"caption\": \"Fig. 4 GenoJEPA demonstrates favourable computational and memory efficiency. (a), (c), (e), and (g) report training time in ms, training memory in MB, inference time in ms, and inference memory in MB, respectively, for GenoJEPA and baselines with fewer than 10M parameters across different sequence lengths. (b), (d), (f), and (h) report the same metrics for GenoJEPA and baselines with more than 50M parameters. Experiments are conducted with a batch size of 1 on an A800 80 GB GPU. Each experiment is repeated for 10 epochs, and mean values are reported. In each epoch, the first 10 steps are excluded to remove cold-start effects. Average metrics are then computed over the next 100 steps. Both axes are shown on a logarithmic scale. Vertical dashed lines indicate sequence lengths that exceed model support or require memory beyond GPU capacity.\", \"page\": 8, \"index\": 3, \"width\": 815, \"height\": 574}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-004.webp\", \"caption\": \"Fig. 1 GenoJEPA learns genomic representations via joint-embedding prediction. (a) shows the pretraining framework. The input DNA sequence is split into non-overlapping patches, linearly projected into dense embeddings, and processed by a Transformer encoder. Token embeddings are then averaged to obtain a sequence representation. Following the LeJEPA formulation, the sequence is augmented into multiple local and global views through random cropping. GenoJEPA is optimized with an invariance loss that aligns semantic features across views together with a SIGReg loss that prevents representation collapse. (b) shows the downstream adaptation strategies for genomic tasks such as functional element identification. In resourcelimited settings, the pretrained encoder is frozen and the resulting sequence embeddings are passed to a lightweight task head for probing. In accuracy-sensitive settings, the entire GenoJEPA model is finetuned end to end together with a task head.\", \"page\": 4, \"index\": 4, \"width\": 815, \"height\": 469}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-005.webp\", \"caption\": \"Fig. 2 GenoJEPA maintains highly discriminative features under probing evaluation. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the probing win-loss comparison between GenoJEPA and the baselines across all benchmarks. A paired Wilcoxon signed-rank test at p = 0.05 is applied to the fold-wise test scores as a stability-aware paired comparison. The number of wins, ties, and losses is reported across 55 tasks from three benchmarks. (b) shows probing performance for each benchmark. The average and median performance across all tasks within each benchmark are reported from the representative scores. (c) shows task-level probing performance. On the horizontal axis, blue labels denote the Genomic Benchmarks, red labels denote the GUE Benchmarks, and green labels denote the Nucleotide Transformer Tasks.\", \"page\": 5, \"index\": 5, \"width\": 815, \"height\": 645}]"
motivation: 现有基因组模型通常将DNA视为语言进行处理，但DNA序列缺乏明确语义边界且包含大量进化噪声，导致计算开销大且表征能力有限。
method: 采用连续分块与语义对齐结合的联合嵌入预测架构，将优化重点从局部碱基重建转向潜在空间的语义对齐。
result: 在55个下游任务中表现出强大的表征能力和稳健的泛化性，同时减少了参数数量和计算成本；其生成的语义向量支持轻量级无GPU分类器实现竞争性准确度。
conclusion: 该研究为基因组基础模型的高效训练和广泛应用提供了可行路径。
---

## 摘要
解码基因组序列中编码的调控语法是计算生物学的核心目标。现有大多数基因组基础模型将DNA视为一种语言，并采用自然语言处理的预训练目标。然而，DNA序列缺乏明确的语义边界且包含大量进化噪声。在低维输入空间中进行核苷酸级重建可能增加计算开销，并产生判别能力有限的表征。下游任务通常依赖于昂贵的微调，这限制了许多生物学实验室的实际应用。本文提出GenoJEPA，一种基于联合嵌入预测架构的基因组表征学习框架。GenoJEPA将连续分块与语义对齐相结合，将优化从局部碱基重建转向潜在空间的语义对齐。在55项下游任务中，GenoJEPA展现出强大的表征能力和稳健的泛化性，同时减少了参数量和计算成本。由冻结的GenoJEPA生成的语义向量支持轻量级无GPU分类器实现具有竞争力的准确度。这些结果为高效训练和大规模基因组基础模型的广泛应用提供了一条实用路径。

## Abstract
Decoding the regulatory syntax encoded in genomic sequences is a central objective in computational biology. Most existing genomic foundation models treat DNA as a language and adopt pretraining objectives from natural language processing. DNA sequences, however, lack explicit semantic boundaries and contain substantial evolutionary noise. Nucleotide-level reconstruction in a low-dimensional input space can therefore increase computational overhead and may yield representations with limited discriminative capacity. Downstream tasks often depend on expensive finetuning, which restricts practical use in many biology laboratories. Here we present GenoJEPA, a genomic representation learning framework based on joint-embedding predictive architecture. GenoJEPA combines continuous patching with semantic alignment, shifting the optimization from local base reconstruction to semantic alignment in latent space. Across 55 downstream tasks, GenoJEPA shows strong representational capacity and robust generalization while reducing parameter count and computational cost. The resulting semantic vectors from frozen GenoJEPA support lightweight GPU-free classifiers to achieve competitive accuracy. These results suggest a practical route towards efficient training and broad application of larger-scale genomic foundation models.

---

## 论文详细总结（自动生成）

# 论文总结：从核苷酸到语义：基于联合嵌入预测架构的基因组表征学习 (GenoJEPA)

## 1. 核心问题与整体含义
*   **研究动机与背景**：
    *   **核心问题**：现有基因组基础模型大多将DNA序列视为“语言”，并沿用自然语言处理（NLP）的预训练目标（如掩码语言建模）。然而，DNA序列存在两个关键特性使其区别于自然语言：
        1.  **缺乏明确语义边界**：DNA序列不像单词那样有天然的、离散的语义单元。
        2.  **包含大量进化噪声**：序列中存在大量非功能性的变异，对基于局部重建的目标构成干扰。
    *   **现有方法的局限**：
        *   在低维输入空间进行核苷酸级别的重建计算开销大。
        *   可能产生判别能力有限的表征。
        *   下游任务严重依赖计算成本高昂的端到端微调，限制了其在资源有限的生物学实验室中的实际应用。
    *   **整体目标**：提出一种更高效、更具判别力的基因组表征学习框架，旨在直接从DNA序列中学习高级语义特征，降低对大规模微调的依赖。

## 2. 方法论
*   **核心思想**：采用**联合嵌入预测架构 (Joint-Embedding Predictive Architecture, JEPA)**，将优化重点从传统的“局部碱基重建”转变为“潜在空间的语义对齐”。
*   **关键技术细节**：
    1.  **连续分块 (Continuous Patching)**：将输入的长DNA序列分割成不重叠的片段（patches），然后线性投影为稠密嵌入向量。这避免了在原始核苷酸空间进行操作。
    2.  **多视图增强与语义对齐**：
        *   对同一DNA序列通过随机裁剪生成多个局部和全局视图。
        *   使用一个Transformer编码器处理这些视图，并通过平均池化获得每个视图的序列级表示。
        *   **核心优化目标**是使来自同一原始序列的不同视图在潜在空间中的表示尽可能相似（对齐），而与不同序列的表示尽可能不同。这通过一个不变性损失函数实现。
    3.  **防止表征坍缩**：为了避免所有输入映射到同一个点（表征坍缩），文中引入了SIGReg损失等正则化技术来保持表示的多样性。
    4.  **下游适应策略**：
        *   **探测 (Probing)**：在资源受限场景下，冻结预训练的编码器，仅使用其生成的固定语义向量训练一个轻量级分类器（如逻辑回归）。
        *   **微调 (Finetuning)**：在精度敏感场景下，对整个模型（编码器+任务头）进行端到端的微调。

## 3. 实验设计
*   **评估基准 (Benchmark)**：
    1.  **Genomic Benchmarks**: DNABERT-2论文中使用的基准任务集。
    2.  **GUE Benchmarks**: Genomic Understanding Evaluation基准任务集。
    3.  **Nucleotide Transformer Tasks**: Nucleotide Transformer论文中使用的基准任务集。总计覆盖了55个不同的下游任务，用于全面评估模型的表征能力和泛化性。
*   **对比方法 (Baselines)**：
    *   与多个先进的基因组基础模型进行对比，包括但不限于DNABERT-2、Nucleotide Transformer等。这些基线模型大多基于自监督预训练目标（如MLM）。

## 4. 资源与算力
*   论文中未明确说明预训练GenoJEPA所使用的具体GPU集群规模、型号及总训练时长。这通常是此类预训练模型工作的一个信息缺口。
*   在效率评估实验部分（Fig.4），明确提到是在一块A800 80GB GPU上进行的测试。实验采用批量大小为1，重复10个周期以测量训练/推理时间和内存占用。

## 5. 实验数量与充分性
*   **实验数量充足且设计全面**：
    1.  **主性能评估**：在三大基准集的55个任务上进行了广泛的性能比较（Fig.2, Fig.3）。
    2.  **效率评估**：系统比较了不同参数量模型在不同序列长度下的训练/推理时间和内存消耗（Fig.4）。
    3.  **数据效率与小样本能力评估**：测试了在不同比例训练数据下的探测性能（Fig5a）。
    4.  **特征通用性评估**：探究了不同池化策略和分类器对性能的影响（Fig5b, c）。
    5.  **统计显著性检验**：使用了Friedman检验和Nemenyi事后检验进行多方法比较排名分析；使用Wilcoxon符号秩检验进行配对胜败分析，增强了结论的可信度。
*   **客观性与公平性评价**：
    *   实验采用了10折交叉验证以减少随机性影响，并使用平均测试分数作为代表性结果。
    *   对比了当前主流基线方法，并在统一的评测框架下进行评估。
    *   同时报告了微调和探测两种范式下的结果，提供了全面的性能视角。总体而言，实验设计较为严谨、客观。

##6 .主要结论与发现
1.	强大的表征能力: GenoJEPA在55个下游任务的探测和微调评估中均展现出强大且稳健的性能表现(Fig2, Fig3)。
2	卓越的效率优势: GenoJEPA在保持高性能的同时显著降低了参数数量和计算成本(包括时间和内存)，尤其是在处理长序列时优势明显(Fig4)。
3	出色的数据效率与小样本学习能力: GenoJEPA学习的表示具有高度的可迁移性即使在少量标注数据下也能取得良好效果(Fig5a)。
4	灵活的下游应用:由冻结的GenoJEPA编码器生成的“语义向量”可以直接用于训练轻量级的无GPU分类器(如逻辑回归)并达到具有竞争力的准确度为资源有限场景提供了实用方案。

##7 .优点
*	范式创新:将计算机视觉领域的JEPA思想成功引入基因组学领域实现了从“重建像素/碱基”到“对齐语义”的根本性转变更契合DNA数据的特性.
*	高效实用:显著降低了模型的计算开销和部署门槛提出的“冻结编码器+轻量级分类器”方案极具实用性.
*	评测全面:覆盖了大规模、多样化的下游任务集并进行了深入的数据效率、计算效率和特征通用性分析论证充分.
*	开源潜力:该方法为后续开发更大规模的基因组基础模型提供了一条高效的预训练路径.

##8 .不足与局限
*	算力细节缺失:如前所述缺少对大规模预训练阶段所需算力的详细描述不利于复现和能耗评估.
*	生物学解释性有限:虽然学习到了有效的语义表示但这些高维向量具体对应哪些生物学功能或调控元件尚不明确缺乏可解释性分析.
*	应用范围限制:
      -主要针对人类和其他模式生物的基因组其方法在处理宏基因组或包含高度复杂重复元件的区域时的有效性有待验证.
      -目前专注于序列水平的分类/回归任务对于更复杂的预测任务(如基因结构预测、三维构象预测)的适用性未经验证.
      -未探索在多模态(如结合表观遗传数据)场景下的扩展能力.
      -进化噪声的处理方式相对简单可能无法完全捕捉复杂的进化约束关系.

(完)

## 9. 潜在影响与未来方向
*   **对基因组学领域的影响**：
    *   **预训练范式的转变**：GenoJEPA的成功验证了在基因组学中采用非重建式、基于语义对齐的预训练目标的可行性，可能启发一系列新的模型架构设计，推动领域从模仿NLP向发展更适配生物数据特性的方法演进。
    *   **降低AI应用门槛**：其高效的“冻结编码器+探测”范式，使得高性能基因组AI工具更易于在缺乏大规模GPU集群的普通生物学实验室中部署和应用，有助于促进AI与实验生物学的深度融合。
    *   **作为基础特征提取器**：模型生成的通用、高质量的“语义向量”可作为下游各类分析任务（如变异效应预测、调控元件发现）的强大特征输入，简化分析流程。
*   **未来研究方向**：
    1.  **可解释性探索**：开发方法以理解GenoJEPA学习到的语义空间维度与特定生物学功能（如转录因子结合位点、染色质状态、进化保守性）之间的关联。
    2.  **扩展到更复杂的数据与任务**：将框架应用于宏基因组学数据、跨物种比较基因组学，或拓展至基因表达预测、蛋白质-DNA相互作用等更复杂的回归与生成任务。
    3.  **多模态整合**：探索将序列语义表示与表观基因组学（如ChIP-seq, ATAC-seq）、三维基因组学（Hi-C）或蛋白质结构等多模态数据进行联合嵌入学习。
    4.  **处理进化信息的改进**：设计更精细的机制来显式建模进化过程中的选择压力与中性变异，使模型能更好地区分功能性与非功能性序列变化。
    5.  **更大规模预训练**：基于当前高效架构，在更大规模、更多样化的基因组数据集上进行预训练，以探索其性能上限并获取更通用的表征。

## 10. 总结
本文提出的GenoJEPA是一个创新且高效的基因组表征学习框架。它通过借鉴JEPA思想，将优化核心从传统的核苷酸级重建转变为潜在空间的语义对齐，从而更好地适应了DNA序列缺乏明确语义单元和包含进化噪声的特性。广泛的实验表明，GenoJEPA在涵盖55个任务的多个基准测试中取得了具有竞争力的性能，同时在计算效率、内存占用和数据效率方面展现出显著优势。其提出的轻量级下游适配方案尤其具有实用价值。尽管在预训练算力透明度、生物学可解释性以及应对更复杂生物问题方面存在局限，但该工作为下一代基因组基础模型的发展提供了一个有前景的新方向，有望推动计算生物学工具在实际科研中的普及和应用。

（完）
