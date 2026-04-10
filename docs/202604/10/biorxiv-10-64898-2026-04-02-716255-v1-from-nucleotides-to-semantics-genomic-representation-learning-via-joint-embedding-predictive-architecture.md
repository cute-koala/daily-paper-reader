---
title: "From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture"
title_zh: 从核苷酸到语义：通过联合嵌入预测架构进行基因组表示学习
authors: "Wang, C., Qi, Q., Sun, H., Zhuang, Z., He, B., Liu, S., Liao, J., Wang, J."
date: 2026-04-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.02.716255v1.full.pdf"
tags: ["query:q2"]
score: 9.0
evidence: 通过联合嵌入预测架构进行基因组表示学习
tldr: 解码基因组序列中的调控语法是计算生物学的核心目标。现有模型多将DNA视为语言进行预训练，但DNA缺乏明确语义边界且含进化噪声，导致核苷酸级重建计算开销大、表征判别力有限且下游任务依赖昂贵微调。本研究提出GenoJEPA框架，基于联合嵌入预测架构，结合连续分块与语义对齐，将优化重点从局部碱基重建转向潜在空间语义对齐。在55个下游任务中表现出强大表征能力和稳健泛化性，同时降低参数量和计算成本；其冻结语义向量支持轻量级无GPU分类器取得有竞争力的准确率。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-001.webp\", \"caption\": \"Fig. 3 GenoJEPA achieves competitive performance with end-to-end finetuning. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the overall performance of GenoJEPA and the baselines across all benchmarks. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show the critical difference diagrams for finetuning and probing performance across all benchmarks. Statistical significance is summarized with the Friedman test at p = 0.05 followed by the Nemenyi post-hoc test at p = 0.05 on the task-level representative scores. The average rank and significance are reported from these mean scores. Black horizontal lines indicate no significant difference between methods. (d), (e), and (f) show finetuning performance for each task within the three benchmarks. Blue circles denote the mean score for each task, and red diamonds denote the average performance across all tasks within each benchmark.\", \"page\": 7, \"index\": 1, \"width\": 813, \"height\": 570}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-002.webp\", \"caption\": \"Fig. 5 GenoJEPA exhibits strong few-shot capabilities and feature versatility. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows probing performance for GenoJEPA and the baselines at different training-data scales across all benchmarks. Within each fold, the training and validation sets are stratified at proportions from 10% to 50% for each label while the test set is kept unchanged. Logistic regression with average pooling is used to assess the data efficiency of each method. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show probing performance under different pooling strategies and classifiers across all benchmarks. The boxplots summarize the distribution of representative scores across 55 tasks from all benchmarks. The center line denotes the median. The box limits denote the first and third quartiles. The whiskers denote the full data range.\", \"page\": 10, \"index\": 2, \"width\": 812, \"height\": 428}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-003.webp\", \"caption\": \"Fig. 4 GenoJEPA demonstrates favourable computational and memory efficiency. (a), (c), (e), and (g) report training time in ms, training memory in MB, inference time in ms, and inference memory in MB, respectively, for GenoJEPA and baselines with fewer than 10M parameters across different sequence lengths. (b), (d), (f), and (h) report the same metrics for GenoJEPA and baselines with more than 50M parameters. Experiments are conducted with a batch size of 1 on an A800 80 GB GPU. Each experiment is repeated for 10 epochs, and mean values are reported. In each epoch, the first 10 steps are excluded to remove cold-start effects. Average metrics are then computed over the next 100 steps. Both axes are shown on a logarithmic scale. Vertical dashed lines indicate sequence lengths that exceed model support or require memory beyond GPU capacity.\", \"page\": 8, \"index\": 3, \"width\": 815, \"height\": 574}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-004.webp\", \"caption\": \"Fig. 1 GenoJEPA learns genomic representations via joint-embedding prediction. (a) shows the pretraining framework. The input DNA sequence is split into non-overlapping patches, linearly projected into dense embeddings, and processed by a Transformer encoder. Token embeddings are then averaged to obtain a sequence representation. Following the LeJEPA formulation, the sequence is augmented into multiple local and global views through random cropping. GenoJEPA is optimized with an invariance loss that aligns semantic features across views together with a SIGReg loss that prevents representation collapse. (b) shows the downstream adaptation strategies for genomic tasks such as functional element identification. In resourcelimited settings, the pretrained encoder is frozen and the resulting sequence embeddings are passed to a lightweight task head for probing. In accuracy-sensitive settings, the entire GenoJEPA model is finetuned end to end together with a task head.\", \"page\": 4, \"index\": 4, \"width\": 815, \"height\": 469}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-005.webp\", \"caption\": \"Fig. 2 GenoJEPA maintains highly discriminative features under probing evaluation. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the probing win-loss comparison between GenoJEPA and the baselines across all benchmarks. A paired Wilcoxon signed-rank test at p = 0.05 is applied to the fold-wise test scores as a stability-aware paired comparison. The number of wins, ties, and losses is reported across 55 tasks from three benchmarks. (b) shows probing performance for each benchmark. The average and median performance across all tasks within each benchmark are reported from the representative scores. (c) shows task-level probing performance. On the horizontal axis, blue labels denote the Genomic Benchmarks, red labels denote the GUE Benchmarks, and green labels denote the Nucleotide Transformer Tasks.\", \"page\": 5, \"index\": 5, \"width\": 815, \"height\": 645}]"
motivation: 现有基因组基础模型通常将DNA视为语言并采用自然语言处理的预训练目标，但DNA缺乏明确语义边界且包含大量进化噪声，导致计算开销大、表征判别能力有限且下游任务依赖昂贵的微调。
method: 该方法基于联合嵌入预测架构，结合连续分块与语义对齐，将优化目标从局部碱基重建转向潜在空间的语义对齐。
result: 在55个下游任务中，GenoJEPA展现出强大的表征能力和稳健的泛化性，同时减少了参数数量和计算成本；其生成的冻结语义向量支持轻量级无GPU分类器达到有竞争力的准确率。
conclusion: 该研究表明，GenoJEPA为高效训练和大规模基因组基础模型的广泛应用提供了一条实用途径。
---

## 摘要
解码基因组序列中编码的调控语法是计算生物学的核心目标。现有的大多数基因组基础模型将DNA视为一种语言，并采用自然语言处理的预训练目标。然而，DNA序列缺乏明确的语义边界，并且包含大量的进化噪声。在低维输入空间中进行核苷酸级别的重建因此会增加计算开销，并可能产生判别能力有限的表示。下游任务通常依赖于昂贵的微调，这限制了许多生物学实验室的实际应用。在此，我们提出了GenoJEPA，一个基于联合嵌入预测架构的基因组表示学习框架。GenoJEPA将连续分块与语义对齐相结合，将优化目标从局部碱基重建转移到潜在空间的语义对齐上。在55个下游任务中，GenoJEPA展现出强大的表示能力和稳健的泛化能力，同时减少了参数数量和计算成本。来自冻结的GenoJEPA生成的语义向量支持轻量级的无GPU分类器达到有竞争力的准确度。这些结果为更大规模基因组基础模型的高效训练和广泛应用指明了一条实用路径。

## Abstract
Decoding the regulatory syntax encoded in genomic sequences is a central objective in computational biology. Most existing genomic foundation models treat DNA as a language and adopt pretraining objectives from natural language processing. DNA sequences, however, lack explicit semantic boundaries and contain substantial evolutionary noise. Nucleotide-level reconstruction in a low-dimensional input space can therefore increase computational overhead and may yield representations with limited discriminative capacity. Downstream tasks often depend on expensive finetuning, which restricts practical use in many biology laboratories. Here we present GenoJEPA, a genomic representation learning framework based on joint-embedding predictive architecture. GenoJEPA combines continuous patching with semantic alignment, shifting the optimization from local base reconstruction to semantic alignment in latent space. Across 55 downstream tasks, GenoJEPA shows strong representational capacity and robust generalization while reducing parameter count and computational cost. The resulting semantic vectors from frozen GenoJEPA support lightweight GPU-free classifiers to achieve competitive accuracy. These results suggest a practical route towards efficient training and broad application of larger-scale genomic foundation models.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将对这篇题为《From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture》的论文进行结构化、深入且客观的总结。

# 论文总结：GenoJEPA——基于联合嵌入预测架构的基因组表示学习

## 1. 核心问题与整体含义
*   **研究动机**：解码基因组序列中蕴含的调控“语法”是计算生物学的核心目标。当前主流的基因组基础模型（如DNABERT-2, NT-v2）大多借鉴自然语言处理范式，将DNA视为“语言”，采用掩码语言建模或下一词预测等目标进行预训练。
*   **核心问题**：这种类比存在根本性缺陷。DNA序列缺乏明确的语义边界（如单词），且包含大量与功能无关的进化噪声。迫使模型在低维输入空间精确重建每个核苷酸，会使其将大量计算容量浪费在拟合噪声上，导致学到的表示判别力有限。此外，下游任务严重依赖昂贵的全参数微调，这在计算资源有限的生物学实验室中构成了实际应用瓶颈。
*   **整体含义**：本文提出了一种新的基因组表示学习范式。作者认为DNA序列在结构上更类似于自然图像（由自然过程产生、低信噪比、无明确边界），因此引入计算机视觉领域的**联合嵌入预测架构**来替代传统的重建式目标。其核心思想是放弃对原始核苷酸序列的重建，转而学习在潜在高维空间中对不同数据增强视图进行语义对齐，从而过滤噪声、提取更具生物学意义的特征。

## 2. 方法论
*   **核心框架**：GenoJEPA (Genomic Joint-Embedding Predictive Architecture)。
*   **关键技术细节**：
    1.  **连续分块 (Continuous Patching)**：
        *   替代传统的k-mer或BPE分词。将输入DNA序列划分为不重叠的核苷酸片段（如16bp为一个patch）。
        *   通过一个可学习的嵌入层和线性投影，将每个patch映射为一个连续的稠密向量。
        *   **优势**：避免了离散词汇表膨胀问题；保留了patch内的生化依赖关系；显著压缩了序列长度（降至1/P），降低了后续Transformer的计算开销。
    2.  **骨干网络 (Backbone)**：
        *   基于ModernBERT架构的双向Transformer编码器。
        *   采用了RoPE位置编码、预归一化、无偏置设计等现代改进。
        *   提供了两个规模版本：轻量版 GenoJEPA-T (6M参数) 和基础版 GenoJEPA-B (52M参数)。
    3.  **预训练目标 - LeJEPA范式**：
        *   **多视图生成**：对同一DNA序列应用随机裁剪，生成多个“全局视图”（裁剪65%-80%）和“局部视图”（裁剪35%-40%）。
        *   **语义对齐损失 (Invariance Loss)**：将所有视图（包括全局和局部）的潜在表示向所有全局视图表示的平均值对齐（使用均方误差）。这鼓励模型学习对裁剪不变的语义特征。
        *   **防坍缩正则化 (SIGReg Loss)**：采用LeJEPA提出的“草图化各向同性高斯正则化”。该损失通过匹配经验特征函数，引导潜在特征的分布趋向于各向同性高斯分布，从而防止所有表示坍缩为同一向量，无需动量编码器等启发式技巧。
        *   **总损失**：`L_total = (1 - α) * L_Invariance + α * L_SIGReg` （α=0.05）。
    4.  **下游适配策略**：
        *   **探测 (Probing)**：冻结预训练骨干，仅使用提取的序列表示（通常为平均池化）训练一个轻量级分类器（如逻辑回归）。用于评估表征质量本身。
        *   **微调 (Finetuning)**：对整个模型（骨干+任务头）进行端到端微调。用于追求最高任务精度。

## 3. 实验设计
*   **预训练数据**：来自850个代表性物种的多物种基因组语料库（约1930亿核苷酸），与NT-v2使用的语料相同。
*   **评估基准与任务**：
    *   三个广泛使用的基准测试集共包含55个子任务：
        1.  Genomic Benchmarks: 跨物种序列分类、调控元件识别等（9个任务）。
        2.  GUE Benchmarks: 转录因子结合位点预测、启动子检测、RNA剪接位点识别等（28个任务）。
        3.  Nucleotide Transformer Tasks: 人类基因组组蛋白修饰、增强子/启动子检测等（18个任务）。
*   **对比基线方法**：
    *   涵盖了不同分词策略和架构的代表性基因组基础模型：
        *   HyenaDNA (7M): Hyena算子，单核苷酸分词，NTP目标。
        *   CaduceusPh (8M): Mamba架构(SSM)，单核苷酸分词，MLM目标。
        *   GROVER (87M): Transformer, BPE分词, MLM目标。
        *   DNABERT-2 (117M): Transformer, BPE分词, MLM目标。
        *   NT-v2 (494M): Transformer, 6-mer分词, MLM目标。（与GenoJEPA使用相同预训练数据）
*   **主要评估指标**：马修斯相关系数 ，因其能很好地处理类别不平衡问题。

## 4. 资源与算力
文中明确说明了预训练的算力需求：
*   GenoJEPA-T （6M参数）：在单张RTX 3090 （24GB）GPU上训练10万步，耗时约12小时。
*   GenoJEPA-B （52M参数）：在单张A800 （80GB）GPU上训练50万步，耗时约150小时。
这种设置强调了其设计的“实用性”，旨在使中等规模实验室能够负担得起模型的训练。

## 5. 实验数量与充分性
实验非常系统和全面：
1.  **主实验对比充分性高**: 
    - `探测评估` ：在所有55个任务上对比了所有基线模型的结果（见表S28），并进行了配对Wilcoxon检验和Friedman-Nemenyi检验以评估统计显著性。
    - `微调评估` ：同样在所有55个任务上进行对比（见表S29），并报告了最佳超参数配置下的结果。

2. `效率分析` ：系统测量了不同序列长度下各模型的训练/推理时间和内存占用。

3. `数据效率分析` ：进行了少样本探测实验（10%-50%的训练数据比例）。

4. `表征通用性分析` ：比较了不同池化策略和不同分类器下的探测性能。

5. `广泛的消融研究` ：在附录C中报告了23项消融实验和分析表格(S4-S25)，涵盖了数据增强策略、架构设计选择、损失函数超参数等多个方面。

总体而言，实验设计严谨、覆盖全面、对比公平。作者统一了探测评估协议以直接比较表征质量；使用了相同的多物种数据集作为NT-v2的直接对照；效率测试遵循了公开协议；消融实验详尽地探索了关键设计决策的影响。这为结论提供了强有力的支持。

## 6.主要结论与发现
1. GenoJEPA学到的冻结表征具有极强的判别力。在探测评估中，
GenoJEPA-B以仅52M的参数量超越了参数量近10倍于它的NT-v2以及所有其他基线模型，
表明其预训练目标能产生更优的表征几何结构。

2.GenoJEPA在下游微调中也表现出色，
GenoJEPA-B的平均性能优于NT-v2，
而轻量级的GenoJEPA-T也超越了参数量相近或更大的多个基线，
证明了该框架在不同规模下的有效性。

3.GenoJEPA具有优异的计算和内存效率。得益于连续分块带来的序列压缩，
其在大多数测试序列长度下的运行时和内存占用均优于传统大Transformer基线；
甚至在与理论复杂度更低的CaduceusPh和HyenaDNA比较时，
在实际运行中也显示出稳定性和效率优势。

4.GenoJEPA具备很强的数据效率和表征通用性。其在少样本设置下表现稳健；
平均池化是其表征的最佳聚合方式；简单的线性分类器即可在其表征上取得优异性能，
表明其特征空间具有良好的线性可分性。

##7 .优点
1.**范式创新**: 
首次将联合嵌入预测架构系统地应用于基因组表示学习，
成功地将优化焦点从低维噪声重建转移到高维语义对齐，
为解决DNA序列的低信噪比特性提供了新思路。

2.**实用性强**: 
强调“冻结骨干+轻量级分类器”的应用模式，
极大降低了资源有限实验室使用先进基础模型的门槛；
同时公开的训练成本也显示了其可及性。

3.**技术集成巧妙**: 
将计算机视觉中的连续分块策略适配到基因组领域，
有效解决了传统分词方法的冗余和对突变敏感的问题；
采用理论驱动的LeJEPA框架避免了启发式防坍缩技巧带来的超参敏感性。

4.**评测体系完备**: 
不仅关注最终精度，
还系统性地评测了表征质量、
计算效率和数据效率等多个维度，
为后续研究提供了全面的评价基准和方法论参考。


##8 .不足与局限
1.**上下文长度限制**: 
当前预训练的上下文窗口为4096 bp,
这适用于基因级别的任务但不足以捕捉更长范围的染色质相互作用或拓扑关联域边界等依赖关系。


2.**模型规模有限**: 
最大的模型仅52M参数,
虽然初步验证了小模型的优越性,
但未探索更大规模下该范式的扩展规律和潜力上限。


3.**特定任务的性能差异**: 
尽管整体表现优异,
但在某些特定任务上仍有其他专用架构表现更好例如HyenaDNA在某些人类调控元件分类任务上的表现),
表明没有一种架构在所有场景下都是最优的。


4.**生物解释性不足**: 
论文主要聚焦于方法性能和工程实用性,
对于Geno J EPA学到的具体生物学模式例如它如何捕捉特定的顺式调控元件组合或进化保守模式)
缺乏深入的定性和可解释性分析。


5.**应用场景限制**: 
目前主要针对分类任务进行评估,
对于生成式或其他更复杂的基因组分析任务的适用性尚未验证。


---
(完)

好的，我将从您提供的总结中断处继续，补充论文的讨论、未来工作以及最终的总体评价部分。

## 9. 讨论与未来方向
论文在讨论部分进一步阐释了其工作的意义和潜在影响：
1.  **范式转变的验证**：作者认为，GenoJEPA的成功验证了将DNA序列视为“自然信号”（如图像）而非“语言”进行建模的有效性。JEPA框架通过迫使模型学习对数据增强（如裁剪）不变的语义特征，自然地过滤了进化噪声和随机突变，从而提取出更稳健、更具功能意义的表示。
2.  **效率与性能的平衡**：GenoJEPA展示了在显著降低模型参数量的情况下实现更优性能的可能性。这挑战了基因组基础模型领域“越大越好”的普遍假设，强调了预训练目标设计的重要性。其高效率特性为在个人工作站或小型集群上训练和使用强大的基因组模型铺平了道路。
3.  **对下游应用的启示**：论文提倡将“冻结骨干+轻量级适配器”作为基因组基础模型的主要应用范式。这不仅能降低计算成本，还能促进模型的标准化和可重复性研究，因为评估的重点从复杂的微调技巧转移到了表征质量本身。

**提出的未来研究方向包括**：
*   **扩展上下文长度**：探索更长的序列建模能力（如>100k bp），以处理增强子-启动子远程互作等需要长程依赖的任务。
*   **整合多模态信息**：将JEPA框架扩展到多模态场景，例如联合学习DNA序列、染色质可及性（ATAC-seq）、组蛋白修饰（ChIP-seq）等多组学数据的对齐表示。
*   **探索生成能力**：研究基于JEPA学习到的表示进行可控序列生成的可能性，例如设计具有特定调控功能的合成DNA元件。
*   **深入的可解释性分析**：使用归因方法或探针分析来理解模型究竟学习了哪些生物学模式和规则。

## 10. 总体评价
本文是一项高质量、创新性强的研究工作。其主要贡献在于：
1.  **概念创新**：成功地将计算机视觉中的联合嵌入预测架构引入基因组学领域，为解决该领域数据信噪比低、缺乏明确语义单元的核心挑战提供了一个新颖且有力的解决方案。
2.  **方法实用**：所提出的GenoJEPA框架不仅在多个基准测试上取得了领先或极具竞争力的性能，更重要的是其设计充分考虑了实际生物医学研究的资源限制，在模型大小、训练成本和部署便捷性之间取得了出色的平衡。
3.  **实验扎实**：评测体系全面、对比公平、消融研究详尽，为结论提供了坚实的经验支持，并为后续研究树立了严谨的评估标准。

尽管存在上下文长度有限、生物可解释性有待深入等局限，但这些更多是受当前工作范围所限而非根本缺陷。本文为基因组表示学习开辟了一条有别于NLP类比的新路径，具有很强的启发性和实际应用价值。它预示着一个可能的发展趋势：即通过借鉴更适合数据本质特性的机器学习范式（如图像/信号处理），而非生硬套用最热门的NLP技术，来推动计算生物学基础模型的进步。

---
（完）
