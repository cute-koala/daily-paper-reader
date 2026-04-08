---
title: "From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture"
title_zh: 从核苷酸到语义：基于联合嵌入预测架构的基因组表征学习
authors: "Wang, C., Qi, Q., Sun, H., Zhuang, Z., He, B., Liu, S., Liao, J., Wang, J."
date: 2026-04-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.02.716255v1.full.pdf"
tags: ["query:q2"]
score: 10.0
evidence: 通过联合嵌入预测架构进行基因组表示学习
tldr: 本研究提出GenoJEPA框架，旨在解决现有基因组基础模型因将DNA视为语言处理而面临的挑战（如缺乏语义边界和进化噪声）。该方法基于联合嵌入预测架构，结合连续分块与语义对齐，优化重点从核苷酸级重建转向潜在空间语义对齐。结果表明其在多项下游任务中具有强大表示能力和泛化性，同时降低了计算开销和参数数量，为高效训练和应用大规模基因组模型提供了实用途径。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-001.webp\", \"caption\": \"Fig. 3 GenoJEPA achieves competitive performance with end-to-end finetuning. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the overall performance of GenoJEPA and the baselines across all benchmarks. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show the critical difference diagrams for finetuning and probing performance across all benchmarks. Statistical significance is summarized with the Friedman test at p = 0.05 followed by the Nemenyi post-hoc test at p = 0.05 on the task-level representative scores. The average rank and significance are reported from these mean scores. Black horizontal lines indicate no significant difference between methods. (d), (e), and (f) show finetuning performance for each task within the three benchmarks. Blue circles denote the mean score for each task, and red diamonds denote the average performance across all tasks within each benchmark.\", \"page\": 7, \"index\": 1, \"width\": 813, \"height\": 570}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-002.webp\", \"caption\": \"Fig. 5 GenoJEPA exhibits strong few-shot capabilities and feature versatility. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows probing performance for GenoJEPA and the baselines at different training-data scales across all benchmarks. Within each fold, the training and validation sets are stratified at proportions from 10% to 50% for each label while the test set is kept unchanged. Logistic regression with average pooling is used to assess the data efficiency of each method. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show probing performance under different pooling strategies and classifiers across all benchmarks. The boxplots summarize the distribution of representative scores across 55 tasks from all benchmarks. The center line denotes the median. The box limits denote the first and third quartiles. The whiskers denote the full data range.\", \"page\": 10, \"index\": 2, \"width\": 812, \"height\": 428}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-003.webp\", \"caption\": \"Fig. 4 GenoJEPA demonstrates favourable computational and memory efficiency. (a), (c), (e), and (g) report training time in ms, training memory in MB, inference time in ms, and inference memory in MB, respectively, for GenoJEPA and baselines with fewer than 10M parameters across different sequence lengths. (b), (d), (f), and (h) report the same metrics for GenoJEPA and baselines with more than 50M parameters. Experiments are conducted with a batch size of 1 on an A800 80 GB GPU. Each experiment is repeated for 10 epochs, and mean values are reported. In each epoch, the first 10 steps are excluded to remove cold-start effects. Average metrics are then computed over the next 100 steps. Both axes are shown on a logarithmic scale. Vertical dashed lines indicate sequence lengths that exceed model support or require memory beyond GPU capacity.\", \"page\": 8, \"index\": 3, \"width\": 815, \"height\": 574}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-004.webp\", \"caption\": \"Fig. 1 GenoJEPA learns genomic representations via joint-embedding prediction. (a) shows the pretraining framework. The input DNA sequence is split into non-overlapping patches, linearly projected into dense embeddings, and processed by a Transformer encoder. Token embeddings are then averaged to obtain a sequence representation. Following the LeJEPA formulation, the sequence is augmented into multiple local and global views through random cropping. GenoJEPA is optimized with an invariance loss that aligns semantic features across views together with a SIGReg loss that prevents representation collapse. (b) shows the downstream adaptation strategies for genomic tasks such as functional element identification. In resourcelimited settings, the pretrained encoder is frozen and the resulting sequence embeddings are passed to a lightweight task head for probing. In accuracy-sensitive settings, the entire GenoJEPA model is finetuned end to end together with a task head.\", \"page\": 4, \"index\": 4, \"width\": 815, \"height\": 469}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-005.webp\", \"caption\": \"Fig. 2 GenoJEPA maintains highly discriminative features under probing evaluation. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the probing win-loss comparison between GenoJEPA and the baselines across all benchmarks. A paired Wilcoxon signed-rank test at p = 0.05 is applied to the fold-wise test scores as a stability-aware paired comparison. The number of wins, ties, and losses is reported across 55 tasks from three benchmarks. (b) shows probing performance for each benchmark. The average and median performance across all tasks within each benchmark are reported from the representative scores. (c) shows task-level probing performance. On the horizontal axis, blue labels denote the Genomic Benchmarks, red labels denote the GUE Benchmarks, and green labels denote the Nucleotide Transformer Tasks.\", \"page\": 5, \"index\": 5, \"width\": 815, \"height\": 645}]"
motivation: 现有基因组模型通常将DNA视为语言进行处理，但DNA序列缺乏明确的语义边界且包含大量进化噪声，导致计算开销大且表示能力有限。
method: 采用连续分块与语义对齐相结合的方法，将优化重点从局部碱基重建转向潜在空间的语义对齐。
result: 在55个下游任务中表现出强大的表示能力和稳健的泛化能力，同时减少了参数数量和计算成本。
conclusion: 该研究为基因组基础模型的高效训练和广泛应用提供了可行路径。
---

## 摘要
解码基因组序列中编码的调控语法是计算生物学的核心目标。现有大多数基因组基础模型将DNA视为一种语言，并采用自然语言处理的预训练目标。然而，DNA序列缺乏明确的语义边界且包含大量进化噪声。在低维输入空间中进行核苷酸级重建可能增加计算开销，并产生判别能力有限的表征。下游任务通常依赖于昂贵的微调，这限制了许多生物学实验室的实际应用。本文提出GenoJEPA，一种基于联合嵌入预测架构的基因组表征学习框架。GenoJEPA将连续分块与语义对齐相结合，将优化从局部碱基重建转向潜在空间的语义对齐。在55项下游任务中，GenoJEPA展现出强大的表征能力和稳健的泛化性，同时减少了参数量和计算成本。由冻结的GenoJEPA生成的语义向量支持轻量级无GPU分类器实现具有竞争力的准确度。这些结果为高效训练和大规模基因组基础模型的广泛应用提供了一条实用路径。

## Abstract
Decoding the regulatory syntax encoded in genomic sequences is a central objective in computational biology. Most existing genomic foundation models treat DNA as a language and adopt pretraining objectives from natural language processing. DNA sequences, however, lack explicit semantic boundaries and contain substantial evolutionary noise. Nucleotide-level reconstruction in a low-dimensional input space can therefore increase computational overhead and may yield representations with limited discriminative capacity. Downstream tasks often depend on expensive finetuning, which restricts practical use in many biology laboratories. Here we present GenoJEPA, a genomic representation learning framework based on joint-embedding predictive architecture. GenoJEPA combines continuous patching with semantic alignment, shifting the optimization from local base reconstruction to semantic alignment in latent space. Across 55 downstream tasks, GenoJEPA shows strong representational capacity and robust generalization while reducing parameter count and computational cost. The resulting semantic vectors from frozen GenoJEPA support lightweight GPU-free classifiers to achieve competitive accuracy. These results suggest a practical route towards efficient training and broad application of larger-scale genomic foundation models.

---

## 论文详细总结（自动生成）

# 论文结构化总结：从核苷酸到语义：基于联合嵌入预测架构的基因组表征学习

## 1. 核心问题与整体含义
*   **研究动机**：解码基因组序列中编码的调控语法是计算生物学的核心挑战。现有主流基因组基础模型（如DNABERT-2、NT-v2）大多借鉴自然语言处理范式，将DNA视为“语言”，采用掩码语言建模或下一词预测等目标进行预训练。
*   **核心问题**：
    *   **类比不当**：DNA序列与人类语言存在本质差异。DNA缺乏明确的语义边界，且包含大量中性进化噪声，信息密度较低，更像自然图像而非文本。
    *   **目标偏差**：基于核苷酸级重建的预训练目标（如MLM）会迫使模型拟合高频、低信噪比的局部细节（噪声），而非学习高层语义特征，导致生成的表征判别能力有限。
    *   **应用瓶颈**：上述问题使得下游任务严重依赖昂贵的全参数微调，这对计算资源有限的生物学实验室构成了实际应用障碍。
*   **整体含义**：本研究旨在提出一种新的基因组表征学习框架，通过改变预训练目标（从重建转向语义对齐）和输入表示方式（连续分块），学习更具判别力且无需微调即可直接使用的通用特征，从而降低基因组基础模型的训练和应用门槛。

## 2. 方法论
*   **核心思想**：借鉴计算机视觉中的联合嵌入预测架构，将优化重点从低维输入空间的核苷酸级重建，转向高维潜在空间中的语义对齐。
*   **关键技术细节**：
    1.  **连续分块 (Continuous Patching)**：
        *   替代传统的k-mer或BPE分词。将输入DNA序列划分为不重叠的核苷酸片段（如16bp）。
        *   通过线性投影将每个片段映射为连续的稠密向量。这避免了离散词汇表膨胀，保留了片段内的生化依赖关系，并有效压缩了序列长度。
    2.  **骨干网络 (Backbone)**：
        *   基于ModernBERT架构的Transformer编码器。
        *   包含两个版本：轻量版GenoJEPA-T (6M参数) 和基础版GenoJEPA-B (52M参数)。
    3.  **多视图增强与对齐 (Multi-view Augmentation & Alignment)**：
        *   对同一序列应用随机裁剪生成多个视图（2个全局视图 + 6个局部视图）。
        *   采用LeJEPA框架的目标函数进行优化：
            *   **不变性损失 (L_Invariance)**：将所有视图的表征向全局视图表征的平均值对齐（使用均方误差）。
            *   **SIGReg损失 (L_SIGReg)**：一种理论驱动的正则化项，通过匹配经验特征函数引导潜在特征趋向各向同性高斯分布，防止表征坍缩。避免了传统对比学习中常用的动量编码器、停止梯度等启发式设计。
        *   总损失为二者的加权和：`L_total = (1 - α) L_Invariance + α L_SIGReg` （α=0.05）。
    4.  **下游适应策略**：
        *   **探测评估 (Probing)**：冻结预训练骨干网络，仅使用轻量级分类器（如逻辑回归）在提取的特征上进行训练。用于直接评估表征质量。
        *   **微调评估 (Finetuning)**：对整个模型进行端到端微调以适应特定任务。

## 3. 实验设计
*   **预训练数据**：
    *   来自850个代表性物种的多物种基因组语料库（与NT-v2相同），总计约1930亿个核苷酸。
*   **评估基准与任务**：
    *   在三个广泛使用的基准上进行全面评估，共涵盖55个子任务：
        1.  Genomic Benchmarks: 9个任务（如编码区/基因间区分类、增强子/启动子识别）。
        2.  GUE Benchmarks: 28个任务（如转录因子结合位点预测、启动子检测、组蛋白修饰预测）。
        3.  Nucleotide Transformer Tasks: 18个任务（聚焦人类基因组的染色质图谱、调控元件和RNA剪接）。
*   **对比基线方法**：
    *   涵盖了不同分词策略和架构的代表性模型：
        *   HyenaDNA (7M, NTP, Hyena算子)
        *   CaduceusPh (8M, MLM, Mamba架构)
        *   GROVER (87M, MLM, BPE分词)
        *   DNABERT-2 (117M, MLM, BPE分词)
        *   NT-v2 (494M, MLM, k-mer分词) ——关键对比对象，使用相同预训练数据但参数量大近10倍。

## 4. 资源与算力
*   **预训练算力消耗明确说明**：
    *   GenoJEPA-T (6M): 单张RTX3090 GPU上训练约12小时完成10万步。
    *   GenoJEPA-B (52M): 单张A800 GPU上训练约150小时完成50万步。
*   **效率分析实验环境**: A800 GPU上进行。

## 5. 实验数量与充分性
*   **实验数量充足且系统化**:
    1.  **主实验**: 
        - `探测评估`(Probing)：55个任务的性能对比及统计显著性检验(Wilcoxon/Friedman-Nemenyi)。
        - `微调评估`(Finetuning)：55个任务的性能对比及排名分析。
    2.  `效率分析`: 
        系统测量了不同序列长度下各模型的训练/推理时间和内存占用。
    3. `少样本能力`: 
        在10%-50%的训练数据比例下评估数据效率。
    4. `特征通用性分析`: 
        比较了不同池化策略(CLS/AVG/MAX)和不同分类器(KNN/Logistic Regression/CatBoost)下的表现。
    5. `消融研究`:
        附录中包含了23项详细的消融实验(C节)，覆盖了数据增强策略(物种多样性、裁剪范围)、架构设计(分块大小、嵌入维度)、目标函数超参数(SIGReg权重)、优化设置等多个方面。这些实验基于GenoJEPA-T进行验证了关键设计选择的合理性。

*	客观性与公平性:
	-	使用了统一的评价协议:所有模型在同一数据集划分上进行10折交叉验证;主要使用马修斯相关系数(MCC)作为指标以应对类别不平衡;探测时统一使用平均池化和逻辑回归分类器以公平比较表征本身质量;微调时则遵循各基线官方推荐的最佳实践以展示其上限性能.
	-	基线选择全面:覆盖了当前主流的不同技术路线.
	-	统计检验严谨:使用了配对Wilcoxon符号秩检验和Friedman-Nemenyi检验来支持性能比较的结论.

##6．主要结论与发现
1．强大的冻结表征能力:在探测评估中GenoJEPA-B在多数任务上超越了所有基线包括参数量大近10倍且在相同数据上预训练的NT-v2表明其学习的表征具有优异的线性可分性和泛化能力无需微调即可用于下游任务.
2．高效的参数利用:GenoJEPA-B仅用52M参数在微调和探测上的平均表现均优于或媲美参数量大得多的基线(NT-v2494MDNABERT-2117MGOVER87M).轻量版GenoJEPA-T也表现出色.
3．优越的计算效率:得益于连续分块带来的序列压缩以及相对紧凑的架构GenoJEPA在运行时和内存占用上优于传统Transformer基线甚至在多数测试长度范围内比一些理论上复杂度更低的次二次复杂度架构更高效稳定.
4．出色的数据效率:在少样本设置下GenoJEPA仅用少量标注数据就能达到接近其他模型使用全部数据的性能.
5．特征的通用性与鲁棒性:在不同池化策略和分类器下GenoJEPA的表征均能保持稳定的高性能表明其特征空间具有良好的几何特性.

##7．优点
1．创新性地将视觉领域的联合嵌入预测思想引入基因组建模成功地将学习焦点从噪声重建转移到语义对齐为解决DNA序列低信噪比问题提供了新思路.
2．提出的连续分块策略巧妙地将图像处理中的补丁概念应用于DNA有效平衡了局部信息保留计算效率和对抗突变扰动的鲁棒性.
3．强调并系统验证了冻结表征的重要性为资源有限的生物实验室提供了即插即用的解决方案降低了应用门槛.
4．实验设计非常全面不仅关注最终精度还深入分析了计算效率数据效率和特征特性评价维度丰富结论支撑有力.

##8．不足与局限
1．序列长度限制:预训练最大长度为4096bp这适用于大多数基因水平任务但对于需要更长程依赖的分析例如拓扑关联域边界识别尚显不足作者指出这是未来扩展的方向.
2．模型规模有限:最大的模型仅52M参数对于探索基因组基础模型的缩放规律以及更大规模可能带来的性能提升尚未涉及.
3．生物学解释性有限:虽然展示了强大的预测性能但论文未深入探讨模型究竟学到了哪些具体的生物学模式或调控语法对学到的语义特征缺乏可解释性分析.
4．特定任务的局限性:尽管整体表现优异但在某些特定任务上其他专门化架构仍可能具有优势例如文中提到HyenaDNA在人类调控元件分类上表现良好.

(完)

好的，我们继续从第8点“不足与局限”之后开始，补充论文的其他重要部分和整体结论。

---

## 9. 未来工作方向
*   **扩展序列长度**：探索更长的上下文窗口（>4096bp），以捕捉长程调控相互作用（如增强子-启动子环、拓扑关联域边界）。
*   **模型缩放定律**：系统地研究模型规模（参数量）、数据量与性能之间的关系，探索基因组基础模型的“涌现”能力。
*   **多模态整合**：将DNA序列表征与表观基因组学（如染色质可及性、组蛋白修饰）、三维基因组结构等多模态数据进行联合嵌入学习，构建更全面的基因调控模型。
*   **可解释性与生物学发现**：开发工具对模型学习到的语义特征进行解释，识别关键的调控基序或语法规则，直接推动生物学机制的理解。
*   **架构创新**：进一步优化连续分块与联合嵌入预测框架，可能引入更高效的注意力机制或状态空间模型。

## 10. 总结与最终评价
本研究提出了一种名为GenoJEPA的基因组表征学习新范式。其核心贡献在于：
1.  **范式转变**：通过引入联合嵌入预测架构（JEPA），将预训练目标从传统的、易受噪声干扰的“核苷酸重建”转变为旨在捕获高层语义一致性的“特征对齐”。
2.  **方法创新**：设计了“连续分块”策略作为输入表示，有效压缩序列、保留局部生化依赖关系，并与JEPA框架自然契合。
3.  **实用价值突出**：生成的冻结表征在大量下游任务上展现出卓越的线性可分性和通用性，使得资源有限的用户无需微调即可获得强大性能，显著降低了基因组基础模型的应用门槛。
4.  **效率卓越**：在参数效率、计算效率和数据效率方面均显著优于现有主流基线，证明了新范式的优越性。

尽管在超长序列建模和可解释性方面存在局限，但GenoJEPA为基因组基础模型的研发提供了一个坚实的新起点。它成功地将计算机视觉中的自监督学习思想创造性地应用于基因组学，其强调“即插即用”表征的设计理念对推动计算生物学工具的实际落地具有重要启示意义。

（完）
