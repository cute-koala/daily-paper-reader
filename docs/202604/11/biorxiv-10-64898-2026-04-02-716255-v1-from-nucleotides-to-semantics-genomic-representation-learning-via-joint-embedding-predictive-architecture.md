---
title: "From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture"
title_zh: 从核苷酸到语义：基于联合嵌入预测架构的基因组表征学习
authors: "Wang, C., Qi, Q., Sun, H., Zhuang, Z., He, B., Liu, S., Liao, J., Wang, J."
date: 2026-04-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.02.716255v1.full.pdf"
tags: ["query:q2"]
score: 10.0
evidence: 通过联合嵌入预测架构进行基因组表示学习
tldr: 本研究提出GenoJEPA框架，旨在解决现有基因组基础模型因将DNA视为语言而面临的序列缺乏明确语义边界、包含进化噪声、计算开销大且表征能力有限的问题。该方法基于联合嵌入预测架构，结合连续分块与语义对齐技术，将优化重点从局部碱基重建转向潜在空间的语义对齐。结果表明，GenoJEPA在多项下游任务中展现出强大的表征能力和泛化性，同时降低了参数数量和计算成本，其生成的语义向量支持轻量级分类器实现高效应用。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-001.webp\", \"caption\": \"Fig. 3 GenoJEPA achieves competitive performance with end-to-end finetuning. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the overall performance of GenoJEPA and the baselines across all benchmarks. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show the critical difference diagrams for finetuning and probing performance across all benchmarks. Statistical significance is summarized with the Friedman test at p = 0.05 followed by the Nemenyi post-hoc test at p = 0.05 on the task-level representative scores. The average rank and significance are reported from these mean scores. Black horizontal lines indicate no significant difference between methods. (d), (e), and (f) show finetuning performance for each task within the three benchmarks. Blue circles denote the mean score for each task, and red diamonds denote the average performance across all tasks within each benchmark.\", \"page\": 7, \"index\": 1, \"width\": 813, \"height\": 570}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-002.webp\", \"caption\": \"Fig. 5 GenoJEPA exhibits strong few-shot capabilities and feature versatility. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows probing performance for GenoJEPA and the baselines at different training-data scales across all benchmarks. Within each fold, the training and validation sets are stratified at proportions from 10% to 50% for each label while the test set is kept unchanged. Logistic regression with average pooling is used to assess the data efficiency of each method. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show probing performance under different pooling strategies and classifiers across all benchmarks. The boxplots summarize the distribution of representative scores across 55 tasks from all benchmarks. The center line denotes the median. The box limits denote the first and third quartiles. The whiskers denote the full data range.\", \"page\": 10, \"index\": 2, \"width\": 812, \"height\": 428}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-003.webp\", \"caption\": \"Fig. 4 GenoJEPA demonstrates favourable computational and memory efficiency. (a), (c), (e), and (g) report training time in ms, training memory in MB, inference time in ms, and inference memory in MB, respectively, for GenoJEPA and baselines with fewer than 10M parameters across different sequence lengths. (b), (d), (f), and (h) report the same metrics for GenoJEPA and baselines with more than 50M parameters. Experiments are conducted with a batch size of 1 on an A800 80 GB GPU. Each experiment is repeated for 10 epochs, and mean values are reported. In each epoch, the first 10 steps are excluded to remove cold-start effects. Average metrics are then computed over the next 100 steps. Both axes are shown on a logarithmic scale. Vertical dashed lines indicate sequence lengths that exceed model support or require memory beyond GPU capacity.\", \"page\": 8, \"index\": 3, \"width\": 815, \"height\": 574}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-004.webp\", \"caption\": \"Fig. 1 GenoJEPA learns genomic representations via joint-embedding prediction. (a) shows the pretraining framework. The input DNA sequence is split into non-overlapping patches, linearly projected into dense embeddings, and processed by a Transformer encoder. Token embeddings are then averaged to obtain a sequence representation. Following the LeJEPA formulation, the sequence is augmented into multiple local and global views through random cropping. GenoJEPA is optimized with an invariance loss that aligns semantic features across views together with a SIGReg loss that prevents representation collapse. (b) shows the downstream adaptation strategies for genomic tasks such as functional element identification. In resourcelimited settings, the pretrained encoder is frozen and the resulting sequence embeddings are passed to a lightweight task head for probing. In accuracy-sensitive settings, the entire GenoJEPA model is finetuned end to end together with a task head.\", \"page\": 4, \"index\": 4, \"width\": 815, \"height\": 469}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-005.webp\", \"caption\": \"Fig. 2 GenoJEPA maintains highly discriminative features under probing evaluation. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the probing win-loss comparison between GenoJEPA and the baselines across all benchmarks. A paired Wilcoxon signed-rank test at p = 0.05 is applied to the fold-wise test scores as a stability-aware paired comparison. The number of wins, ties, and losses is reported across 55 tasks from three benchmarks. (b) shows probing performance for each benchmark. The average and median performance across all tasks within each benchmark are reported from the representative scores. (c) shows task-level probing performance. On the horizontal axis, blue labels denote the Genomic Benchmarks, red labels denote the GUE Benchmarks, and green labels denote the Nucleotide Transformer Tasks.\", \"page\": 5, \"index\": 5, \"width\": 815, \"height\": 645}]"
motivation: 现有基因组模型通常将DNA视为语言并采用自然语言处理的预训练目标，但DNA序列缺乏明确的语义边界且包含大量进化噪声，导致计算开销大且表征能力有限。
method: 采用连续分块与语义对齐相结合的方法，将优化重点从局部碱基重建转向潜在空间的语义对齐。
result: 在55个下游任务中表现出强大的表征能力和稳健的泛化性，同时减少了参数数量和计算成本；其生成的语义向量支持轻量级无GPU分类器实现有竞争力的准确性。
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
*   **研究动机**：解码基因组序列中蕴含的调控语法是计算生物学的核心目标。现有主流基因组基础模型（如DNABERT-2、NT-v2）大多借鉴自然语言处理范式，将DNA视为“语言”，采用掩码语言建模或下一词预测等预训练目标。然而，DNA序列与人类语言存在本质差异：
    *   **缺乏明确语义边界**：DNA序列更像自然图像，由自然过程产生，没有预先定义的词汇或句法。
    *   **高进化噪声**：序列中包含大量中性突变和冗余信息，信噪比较低。
*   **核心问题**：在低维输入空间进行精确的核苷酸级重建（如MLM），会迫使模型将大量容量用于拟合与调控功能相关性有限的进化噪声，导致学到的表征判别能力有限。这使得下游任务严重依赖昂贵的全参数微调，成为许多计算资源有限的生物学实验室应用此类模型的瓶颈。
*   **整体含义**：本研究旨在提出一种新的基因组表征学习范式，通过借鉴计算机视觉中的联合嵌入预测架构思想，将优化重点从低维输入空间的局部重建转向高维潜在空间的语义对齐，以期获得更具判别性、更易于迁移且计算高效的基因组表征。

## 2. 方法论
*   **核心思想**：提出 **GenoJEPA**框架，其核心是将LeJEPA（一种理论驱动的联合嵌入预测架构）应用于基因组序列建模。
    *   **目标转变**：从“重建输入”转变为“在潜在空间对齐语义”。模型学习将同一序列的不同增强视图（全局和局部）的表征对齐到一个共同的语义中心（全局视图表征的均值），从而捕获对局部噪声鲁棒的高层语义信息。
    *   **防坍缩机制**：采用理论驱动的Sketched Isotropic Gaussian Regularization损失来防止所有表征坍缩为常数向量。该损失通过匹配经验特征函数，引导潜在特征分布趋向于各向同性的高斯分布。
*   **关键技术细节**：
    1.  **连续分块化**：
        *   摒弃传统的k-mer或BPE分词。将输入DNA序列划分为不重叠的核苷酸片段（如16bp），通过线性投影直接映射为连续的稠密向量。
        *   **优势**：避免离散词汇表膨胀；保留片段内的生化依赖关系；有效压缩序列长度以降低计算成本；对单核苷酸变异更鲁棒。
    2.  **骨干网络**：基于ModernBERT的双向Transformer编码器，采用RoPE位置编码、无偏置设计等优化。
    3.  **多视图增强策略**：
        *   对每个训练样本生成多个视图（2个全局视图+6个局部视图），通过随机裁剪实现。全局视图裁剪比例较大以捕获长程依赖，局部视图比例较小以关注精细模式。
    4.  **损失函数**：
        *   总损失 `L_total = (1 - α) L_Invariance + α L_SIGReg`。
        *   `L_Invariance`（不变性损失）：使用均方误差将所有视图的投影后表征`z_v`拉向全局视图表征的均值锚点`z_global`。
        *   `L_SIGReg`（防坍缩正则化）：通过在一系列随机投影方向上匹配经验特征函数与标准高斯分布的特征函数，确保特征分布的多样性和各向同性。

## 3. 实验设计
*   **预训练数据**：
    *   使用来自850个代表性物种的多物种基因组语料库（源自Nucleotide Transformer研究），总计约1930亿个核苷酸。涵盖细菌、真菌、无脊椎动物、脊椎动物等主要分类群。
*   **评估基准与任务 (55项)**：
    1.  Genomic Benchmarks (9项)：跨物种序列分类、增强子/启动子/开放染色质区域识别等。
    2.  GUE Benchmarks (28项)：转录因子结合位点预测、启动子检测、RNA剪接位点识别、组蛋白修饰状态分类等（涵盖人、小鼠、酵母、病毒）。
    3.  Nucleotide Transformer Tasks (18项)：专注于人类基因组的染色质图谱分析、调控元件检测和RNA剪接任务。
*   **对比基线方法 (覆盖不同分词策略与架构)**：
    *   HyenaDNA (7M)：基于Hyena算子，单核苷酸分词，自回归预训练。
    *   CaduceusPh (8M)：基于Mamba SSM架构，单核苷酸分词，MLM预训练。
    *   GROVER (87M)：Transformer编码器+BPE分词，MLM预训练于人类基因组。
    *   DNABERT-2 (117M)：Transformer编码器+BPE分词+ALiBi位置编码，MLM预训练于135个物种。
    *   NT-v2 (494M)：Transformer编码器+6-mer分词+RoPE位置编码，MLM预训练于850个物种语料库（与GenoJEPA相同）。
*   **评估协议**：
    *   **探测评估(Probing)**：冻结所有预训练骨干参数，仅在线性分类器上训练。用于直接评估预训练表征的质量和可迁移性。主要使用平均池化和逻辑回归分类器。这是本文的重点评估方式之一。
    *   **微调评估(Finetuning)**：对整个模型进行端到端微调以适应下游任务。用于评估模型在充足适应下的性能上限。

## 4. 资源与算力
文中明确说明了两种规模模型的预训练算力需求：
*   GenoJEPA-T (**轻量版**, ~6M参数)：
    *   硬件：单张RTX 3090 GPU (24GB)。
    *   时长：100,000步约12小时完成预训练。
*   GenoJEPA-B (**基础版**, ~52M参数)：
    *   硬件：单张A800 GPU (80GB)。
    -时长:500,000步约150小时完成预培训。

##5 .实验数量与充分性
本文进行了非常全面且系统的实验分析:
-主实验数量:在55项下游任务上对7种模型(包括两个版本的GenoJEPA)进行了探测和微调两种模式的评估.
-消融与分析实验:附录中包含了23项消融研究(使用GenoJEPA-T),涵盖了:
数据增强(物种多样性,裁剪尺度,数量,随机突变,反向互补).
架构设计(分块大小,滑动步长,嵌入策略,池化策略,投影头设计).
目标函数(不变性准则,SIGReg超参数如切片数,积分域).
优化设置(学习率,权重衰减).
下游适应(不同池化策略对微调的影响).
-公平性与客观性:
统一了探测评估协议:所有模型使用相同的平均池化和逻辑回归分类器进行评估.
使用了跨验证并报告平均值和标准差.
采用了适合类别不平衡任务的马修斯相关系数作为主要评价指标.
进行了统计显著性检验(Wilcoxon符号秩检验,Friedman检验及Nemenyi事后检验).
效率分析时统一了测试环境(A800 GPU,batch size=1),并以原始核苷酸长度作为衡量标准.

##6 .主要结论与发现
1.**强大的冻结表征能力**:在探测评估中,**GenoJEPA-B**(52M)在55项任务上的平均表现超过了所有基线包括参数量近10倍于它的NT-v2.GenoJEPA-T(6 M)也表现出色甚至优于参数量大得多的基线这表明其学到的表征具有出色的线性可分性和可迁移性无需微调即可支持轻量级GPU-free分类器取得有竞争力的结果.
2.**高效的端到端性能**:在全参数微调模式下,**GenoJEPA-B仍然取得了最佳的平均排名表现优于NT-v2**.这表明其初始权重也为下游优化提供了良好的起点.
3.**卓越的计算与内存效率**:相比传统大Transformer基线和一些新兴的长序列架构(CaduceusPh HyenaDNA),GenoJEPA在广泛的序列长度范围内表现出更低的运行时内存占用和更稳定的内存增长曲线尤其在中等长度范围内优势明显.
4.**出色的数据效率与小样本能力**:在小样本探测实验中仅使用10%的训练数据即可达到其他基线使用50%甚至100%数据时的性能水平表明其对标注数据的依赖性较低.
5.**特征通用性强**:在不同池化策略(Avg Max CLS)和不同分类器(KNN Logistic Regression CatBoost)下 GenoJEPA学到的特征都保持了良好的判别能力.

##7 .优点
1.**范式创新**:首次将理论驱动的联合嵌入预测架构系统地应用于基因组表示学习成功地将优化焦点从噪声敏感的重建转移到高层语义对齐为解决DNA序列高噪声低信噪比问题提供了新思路.
2.**实用性强**:强调并证明了"冻结骨干+轻量级分类器"工作流程的可行性这极大地降低了资源有限实验室应用先进基础模型的门槛.
3.**全面的评估体系**:不仅比较最终精度还系统评估了计算效率内存占用和数据效率等多维度指标为实际部署提供了详实参考.
4.**深入细致的消融分析**:附录中大量的消融实验为理解各个组件的作用以及超参数选择提供了充分依据增强了研究的可信度.

##8 .不足与局限
1.**上下文长度限制**:当前模型的预训练上下文窗口为4096 bp这足以覆盖大多数基因水平任务但对于需要更长程依赖的分析例如拓扑关联域边界识别尚显不足尽管论文指出其效率优势为扩展上下文长度提供了基础但未实际验证.
2.**模型规模有限**:最大的模型仅52 M参数虽然在小规模上证明了方法的有效性但"缩放定律"在大规模下的表现以及更大模型能否带来进一步的性能飞跃尚未探索这与当前动辄数十亿参数的LLMs趋势形成对比但也可能是出于实用性和可复现性的考虑.
3.**特定任务的局限性**:尽管整体表现优异但在某些特定任务上例如H4ac预测其他基线可能表现更好这表明没有一种架构在所有场景下都是最优的 Geno J EPA的优势在于其综合平衡的性能谱系而非绝对统治力.

**(完)**

好的，我们继续从第8点“不足与局限”之后开始补全。

---

## 9. 未来展望
1.  **扩展上下文长度**：当前模型专注于基因水平的调控语法（~4k bp）。未来的工作可以探索将GenoJEPA范式扩展到更长的序列窗口（如100k bp甚至更长），以捕获染色质空间组织等更高层级的基因组“篇章结构”。论文中展示的卓越计算效率为此提供了可行性基础。
2.  **多模态整合**：当前的表征学习仅基于序列信息。一个重要的方向是将表观基因组学数据（如染色质可及性、组蛋白修饰）作为额外的“视图”或监督信号融入联合嵌入预测框架，构建能够统一理解序列语法与表观语境的更强大模型。
3.  **解码生物学机制**：GenoJEPA学习到的语义空间具有良好几何特性。未来可深入研究该空间的结构，例如通过探查特定方向是否对应明确的生物学功能（如转录因子结合偏好），从而不仅提供预测工具，也增进对调控代码本身的理解。
4.  **迈向生成模型**：联合嵌入预测架构本质上是判别式的。如何将其思想与生成式建模结合，开发能够遵循语义约束（如给定增强子活性）生成或编辑DNA序列的模型，是一个充满前景的挑战。

## 10. 总结
本研究提出的GenoJEPA框架，通过将计算机视觉中的联合嵌入预测架构创新性地应用于基因组序列分析，成功地将表征学习的优化目标从“精确重建噪声细节”转变为“对齐高层语义”。这种范式转换带来了多重优势：
*   **性能上**：其学习到的冻结表征在线性探测评估中超越了包括参数量大10倍的基线在内的多种主流方法，展现出卓越的可迁移性和判别力。
*   **效率上**：在推理速度、内存占用和数据效率方面均表现优异，显著降低了先进基因组AI模型的应用门槛。
*   **实用性上**：明确支持并验证了“冻结骨干+轻量级分类器”的工作流程，为计算资源有限的生物医学实验室提供了切实可行的解决方案。

尽管在超长上下文建模和绝对任务统治力方面存在局限，但GenoJEPA为基因组表征学习开辟了一条新的、高效的路径。它强调语义而非像素（核苷酸）的建模哲学，可能对处理其他具有高噪声、弱结构特性的生物序列数据（如蛋白质无序区域）也具有启发意义。这项工作标志着基因组AI从模仿NLP范式向发展适应其自身数据特性的原生范式的关键一步。

（完）
