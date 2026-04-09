---
title: "From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture"
title_zh: 从核苷酸到语义：通过联合嵌入预测架构进行基因组表示学习
authors: "Wang, C., Qi, Q., Sun, H., Zhuang, Z., He, B., Liu, S., Liao, J., Wang, J."
date: 2026-04-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.02.716255v1.full.pdf"
tags: ["query:q2"]
score: 10.0
evidence: 通过联合嵌入预测架构进行基因组表示学习
tldr: 解码基因组序列中的调控语法是计算生物学的核心目标。现有模型多将DNA视为语言进行预训练，但DNA缺乏明确语义边界且包含进化噪声，导致计算开销大、表征能力有限且下游任务依赖昂贵微调。本研究提出GenoJEPA框架，基于联合嵌入预测架构，结合连续分块与语义对齐，将优化重点从局部碱基重建转向潜在空间语义对齐。该框架在55个下游任务中表现出强大的表征能力和泛化性，同时降低了参数量和计算成本；其生成的冻结语义向量支持轻量级无GPU分类器取得有竞争力的准确率。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-001.webp\", \"caption\": \"Fig. 3 GenoJEPA achieves competitive performance with end-to-end finetuning. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the overall performance of GenoJEPA and the baselines across all benchmarks. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show the critical difference diagrams for finetuning and probing performance across all benchmarks. Statistical significance is summarized with the Friedman test at p = 0.05 followed by the Nemenyi post-hoc test at p = 0.05 on the task-level representative scores. The average rank and significance are reported from these mean scores. Black horizontal lines indicate no significant difference between methods. (d), (e), and (f) show finetuning performance for each task within the three benchmarks. Blue circles denote the mean score for each task, and red diamonds denote the average performance across all tasks within each benchmark.\", \"page\": 7, \"index\": 1, \"width\": 813, \"height\": 570}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-002.webp\", \"caption\": \"Fig. 5 GenoJEPA exhibits strong few-shot capabilities and feature versatility. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows probing performance for GenoJEPA and the baselines at different training-data scales across all benchmarks. Within each fold, the training and validation sets are stratified at proportions from 10% to 50% for each label while the test set is kept unchanged. Logistic regression with average pooling is used to assess the data efficiency of each method. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show probing performance under different pooling strategies and classifiers across all benchmarks. The boxplots summarize the distribution of representative scores across 55 tasks from all benchmarks. The center line denotes the median. The box limits denote the first and third quartiles. The whiskers denote the full data range.\", \"page\": 10, \"index\": 2, \"width\": 812, \"height\": 428}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-003.webp\", \"caption\": \"Fig. 4 GenoJEPA demonstrates favourable computational and memory efficiency. (a), (c), (e), and (g) report training time in ms, training memory in MB, inference time in ms, and inference memory in MB, respectively, for GenoJEPA and baselines with fewer than 10M parameters across different sequence lengths. (b), (d), (f), and (h) report the same metrics for GenoJEPA and baselines with more than 50M parameters. Experiments are conducted with a batch size of 1 on an A800 80 GB GPU. Each experiment is repeated for 10 epochs, and mean values are reported. In each epoch, the first 10 steps are excluded to remove cold-start effects. Average metrics are then computed over the next 100 steps. Both axes are shown on a logarithmic scale. Vertical dashed lines indicate sequence lengths that exceed model support or require memory beyond GPU capacity.\", \"page\": 8, \"index\": 3, \"width\": 815, \"height\": 574}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-004.webp\", \"caption\": \"Fig. 1 GenoJEPA learns genomic representations via joint-embedding prediction. (a) shows the pretraining framework. The input DNA sequence is split into non-overlapping patches, linearly projected into dense embeddings, and processed by a Transformer encoder. Token embeddings are then averaged to obtain a sequence representation. Following the LeJEPA formulation, the sequence is augmented into multiple local and global views through random cropping. GenoJEPA is optimized with an invariance loss that aligns semantic features across views together with a SIGReg loss that prevents representation collapse. (b) shows the downstream adaptation strategies for genomic tasks such as functional element identification. In resourcelimited settings, the pretrained encoder is frozen and the resulting sequence embeddings are passed to a lightweight task head for probing. In accuracy-sensitive settings, the entire GenoJEPA model is finetuned end to end together with a task head.\", \"page\": 4, \"index\": 4, \"width\": 815, \"height\": 469}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-005.webp\", \"caption\": \"Fig. 2 GenoJEPA maintains highly discriminative features under probing evaluation. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the probing win-loss comparison between GenoJEPA and the baselines across all benchmarks. A paired Wilcoxon signed-rank test at p = 0.05 is applied to the fold-wise test scores as a stability-aware paired comparison. The number of wins, ties, and losses is reported across 55 tasks from three benchmarks. (b) shows probing performance for each benchmark. The average and median performance across all tasks within each benchmark are reported from the representative scores. (c) shows task-level probing performance. On the horizontal axis, blue labels denote the Genomic Benchmarks, red labels denote the GUE Benchmarks, and green labels denote the Nucleotide Transformer Tasks.\", \"page\": 5, \"index\": 5, \"width\": 815, \"height\": 645}]"
motivation: 现有基因组基础模型多将DNA视为语言并采用自然语言处理的预训练目标，但DNA序列缺乏明确语义边界且包含大量进化噪声，导致计算开销大、表征判别能力有限且下游任务依赖昂贵的微调。
method: 该方法基于联合嵌入预测架构，结合连续分块与语义对齐，将优化目标从局部碱基重建转向潜在空间的语义对齐。
result: 在55个下游任务中，GenoJEPA展现出强大的表征能力和稳健的泛化性，同时减少了参数数量和计算成本；其生成的冻结语义向量支持轻量级无GPU分类器达到有竞争力的准确率。
conclusion: 该研究表明，GenoJEPA为高效训练和大规模基因组基础模型的广泛应用提供了一条实用途径。
---

## 摘要
解码基因组序列中编码的调控语法是计算生物学的核心目标。大多数现有的基因组基础模型将DNA视为一种语言，并采用自然语言处理的预训练目标。然而，DNA序列缺乏明确的语义边界，且包含大量的进化噪声。在低维输入空间中进行核苷酸级重建因此会增加计算开销，并可能产生判别能力有限的表示。下游任务通常依赖于昂贵的微调，这限制了许多生物学实验室的实际应用。在此，我们提出了GenoJEPA，一个基于联合嵌入预测架构的基因组表示学习框架。GenoJEPA将连续分块与语义对齐相结合，将优化从局部碱基重建转向潜在空间中的语义对齐。在55个下游任务中，GenoJEPA展现出强大的表示能力和稳健的泛化能力，同时减少了参数数量和计算成本。来自冻结GenoJEPA的语义向量支持轻量级的无GPU分类器实现具有竞争力的准确度。这些结果为高效训练和大规模基因组基础模型的广泛应用指明了一条实用路径。

## Abstract
Decoding the regulatory syntax encoded in genomic sequences is a central objective in computational biology. Most existing genomic foundation models treat DNA as a language and adopt pretraining objectives from natural language processing. DNA sequences, however, lack explicit semantic boundaries and contain substantial evolutionary noise. Nucleotide-level reconstruction in a low-dimensional input space can therefore increase computational overhead and may yield representations with limited discriminative capacity. Downstream tasks often depend on expensive finetuning, which restricts practical use in many biology laboratories. Here we present GenoJEPA, a genomic representation learning framework based on joint-embedding predictive architecture. GenoJEPA combines continuous patching with semantic alignment, shifting the optimization from local base reconstruction to semantic alignment in latent space. Across 55 downstream tasks, GenoJEPA shows strong representational capacity and robust generalization while reducing parameter count and computational cost. The resulting semantic vectors from frozen GenoJEPA support lightweight GPU-free classifiers to achieve competitive accuracy. These results suggest a practical route towards efficient training and broad application of larger-scale genomic foundation models.

---

## 论文详细总结（自动生成）

### 论文总结：从核苷酸到语义：通过联合嵌入预测架构进行基因组表示学习

#### 1. 核心问题与整体含义
*   **研究动机**：解码基因组序列中的调控语法是计算生物学的核心目标。现有主流方法将DNA序列视为“语言”，并采用自然语言处理（NLP）的预训练目标（如掩码语言建模）。然而，DNA序列缺乏明确的语义边界（如单词），且包含大量进化噪声和冗余信息。这导致现有模型存在三大问题：
    1.  **计算开销大**：在低维输入空间进行核苷酸级重建效率低下。
    2.  **表征能力有限**：可能学习到判别性不足的表征。
    3.  **应用门槛高**：下游任务严重依赖昂贵的端到端微调，限制了其在资源有限的生物学实验室中的广泛应用。
*   **整体含义**：本研究旨在提出一种新的基因组表示学习框架，通过改变预训练的核心优化目标（从局部重建转向语义对齐），以更高效、更具泛化能力的方式学习基因组序列的深层语义表示，推动大规模基因组基础模型的实际应用。

#### 2. 方法论
*   **核心思想**：采用**联合嵌入预测架构**，其核心是让模型学会从同一序列的不同增强视图中提取一致的、高层次的语义信息，而非精确重建原始的局部核苷酸序列。
*   **关键技术细节**：
    *   **框架设计 (GenoJEPA)**：
        1.  **输入处理**：将DNA序列分割成不重叠的片段，通过线性投影转换为密集嵌入向量。
        2.  **编码器**：使用Transformer编码器处理这些嵌入。
        3.  **视图生成**：对输入序列应用随机裁剪，生成多个局部和全局的增强视图。
        4.  **预测与对齐**：模型的目标是预测一个视图的潜在表征与另一个视图的表征之间的对应关系。通过优化一个不变性损失函数，促使不同视图的语义特征在潜在空间中对齐。
    *   **关键创新点**：
        *   **语义对齐取代局部重建**：避免了在像素/核苷酸级别进行精确重建的计算负担和噪声干扰。
        *   **防止表征坍塌**：采用了SIGReg损失函数，确保模型学习到有意义且非退化的表征。

#### 3. 实验设计
*   **评估基准与数据集**：
    *   在总计包含55个下游任务的三个基准测试集上进行评估：
        1.  **Genomic Benchmarks**
        2.  **GUE Benchmarks**
        3.  **Nucleotide Transformer Tasks**
    *   任务类型包括功能元件识别等基因组学典型任务。
*   **对比方法 (Baselines)**：
    *   与现有的基因组基础模型进行对比，这些模型大多基于Transformer架构并使用掩码语言建模等预训练目标。论文中未列出具体所有基线模型名称，但从上下文可知它们代表了当前主流方法。
*   **评估策略**：
    *   **微调评估 (Finetuning)**：对整个预训练模型进行端到端微调以适应下游任务。
    *   **探针评估 (Probing)**：冻结预训练编码器的权重，仅使用其生成的固定表征来训练一个轻量级的分类器（如逻辑回归），以评估表征本身的质量和通用性。

#### 4. 资源与算力
*   论文中部分实验报告了计算效率指标。例如在图4相关的实验中，使用了单张A800（80GB显存）GPU进行测量，比较了不同参数量（少于1000万 vs. 多于5000万）的模型在不同序列长度下的训练/推理时间和内存消耗。但未详细说明完整预训练过程所使用的总GPU数量、型号和总时长。

#### 5. 实验数量与充分性
*   **实验规模较大且系统化**：
    1.  在55个不同的下游任务上进行了全面评估，覆盖了多个基准测试集。
    2.  进行了详尽的性能对比分析（图3），包括平均性能排名和统计显著性检验（Friedman检验及Nemenyi事后检验）。
    3.  深入分析了数据效率和小样本学习能力（图5），测试了在不同比例训练数据下的表现。
    4.  系统地评估了计算效率和内存占用（图4）。
    5.  进行了探针分析以验证冻结表征的质量（图2）。
*   **充分性与客观性评价**：
    *   实验设计较为充分和客观。采用了10折交叉验证以减少随机性影响；使用平均测试分数作为代表性结果；进行了严格的统计检验；同时考虑了“微调”和“探针”两种实际应用场景。这为结论提供了有力的支持。

#### 6. 主要结论与发现
1.  **性能优越性**: GenoJEPA在55个下游任务的综合评估中取得了具有竞争力的性能。其冻结表征配合轻量级分类器能达到接近端到端微调的准确率。
2.  **泛化能力强**: GenoJEPA学习的表征具有高度的判别性和通用性，在小样本设置下表现稳健。
3.  **效率显著提升**: GenoJEPA在保持高性能的同时，显著降低了模型的参数量和计算开销（包括训练时间和内存占用）。
4.  ####方法论有效性:研究结果表明,将预训练目标从核苷酸级重建转向潜在空间的语义对齐是一条有效路径,能够获得更高效、更具泛化能力的基因组表示。

####7\.优点

- ####概念创新:成功地将计算机视觉领域的联合嵌入预测架构思想引入基因组学,从根本上改变了预训练的优化目标,更具生物合理性(关注整体功能语义而非局部碱基)。
- ####实用性强:明确针对现有模型“依赖昂贵微调”的应用痛点,证明了其冻结表征可直接用于轻量级、无需GPU的分类器,极大降低了部署门槛.
- ####实验全面:评测基准广泛(55个任务),不仅关注最终精度,还系统评估了数据效率、计算效率和表征质量等多个维度.
- ####效率优势突出:通过降低对局部细节的重建需求,实现了参数量和计算成本的双重降低.

####8\.不足与局限

- ####生物学解释性有限:作为一种表示学习方法,GenoJEPA所捕获的“语义”具体对应何种生物学机制(如特定转录因子结合模式或染色质状态)缺乏深入的可解释性分析.
- ####进化噪声处理的普适性:虽然指出DNA包含进化噪声,但该方法对不同物种、不同进化距离序列中噪声的鲁棒性未做专门测试.
- ####基准任务的局限性:尽管使用了55个任务,但这些任务可能仍无法完全覆盖基因组学中所有复杂的调控模式(如长程相互作用、三维结构关联).
- ####技术细节披露不足:对于联合嵌入预测中具体的增强策略(裁剪方式)、防止坍塌损失的详细设计等关键超参数和技术选择对结果的影响讨论不够深入.

(完)

### 论文总结：从核苷酸到语义：通过联合嵌入预测架构进行基因组表示学习

#### 9. 潜在影响与未来方向
*   **对基因组学基础模型的影响**：
    *   **范式转变**：本研究挑战了将DNA序列简单视为“语言”并用NLP方法处理的范式，提出应更关注序列的“语义”（功能）而非“语法”（局部结构）。这为开发更高效、更具生物意义的基础模型提供了新思路。
    *   **降低应用门槛**：通过生成高质量的冻结表征，使得资源有限的实验室无需昂贵的GPU微调即可利用先进模型，有望促进基因组学AI工具的民主化。
    *   **推动高效架构设计**：证明了通过改变预训练目标（从重建到对齐）可以显著提升计算效率，激励后续研究探索其他自监督目标在基因组数据上的应用。
*   **对未来研究的启示**：
    *   **可解释性研究**：未来工作可深入分析GenoJEPA学习到的“语义表示”具体对应哪些生物学特征（如增强子、沉默子、特定染色质状态），增强模型的可信度和生物学洞察力。
    *   **扩展到多模态与更大规模**：可将此框架与表观基因组学数据（如ChIP-seq, ATAC-seq）进行多模态对齐学习。同时，在更大规模、更多样化的基因组数据集上进行预训练，以测试其极限泛化能力。
    *   **优化技术细节**：进一步探索不同的视图生成策略（增强方式）、编码器架构以及防止坍塌损失的变体，以持续提升性能与稳定性。

#### 10. 总体评价
本研究是一项具有重要价值的探索性工作。它敏锐地指出了当前基因组表示学习领域过度依赖掩码重建范式的局限性，并创造性地引入了来自计算机视觉的联合嵌入预测架构。实验证明，这种以“语义对齐”为核心的新范式，能够在多个下游任务上取得有竞争力的性能，同时显著降低模型的参数量、计算开销和应用门槛。

尽管在生物学可解释性和某些技术细节的深度分析上存在提升空间，但论文的核心贡献——即提出并验证了一种更高效、更泛化的基因组表示学习新路径——是清晰且有力的。这项工作不仅为构建下一代基因组基础模型提供了切实可行的方案，也为思考如何让AI更好地理解生命的“代码”提供了新的视角。

（完）
