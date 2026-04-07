---
title: "From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture"
title_zh: 从核苷酸到语义：通过联合嵌入预测架构进行基因组表示学习
authors: "Wang, C., Qi, Q., Sun, H., Zhuang, Z., He, B., Liu, S., Liao, J., Wang, J."
date: 2026-04-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.02.716255v1.full.pdf"
tags: ["query:q2"]
score: 9.0
evidence: 通过联合嵌入预测架构进行基因组表示学习
tldr: 解码基因组序列中的调控语法是计算生物学的核心目标。现有模型多将DNA视为语言进行预训练，但DNA缺乏明确语义边界且包含进化噪声，导致核苷酸级重建计算开销大、表征判别力有限且下游任务依赖昂贵微调。本文提出GenoJEPA，一个基于联合嵌入预测架构的基因组表征学习框架。它结合连续分块与语义对齐，将优化从局部碱基重建转向潜在空间语义对齐。在55个下游任务中表现出强大表征能力和稳健泛化性，同时降低参数量和计算成本；其冻结语义向量支持轻量级无GPU分类器取得有竞争力的准确率。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-001.webp\", \"caption\": \"Fig. 3 GenoJEPA achieves competitive performance with end-to-end finetuning. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the overall performance of GenoJEPA and the baselines across all benchmarks. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show the critical difference diagrams for finetuning and probing performance across all benchmarks. Statistical significance is summarized with the Friedman test at p = 0.05 followed by the Nemenyi post-hoc test at p = 0.05 on the task-level representative scores. The average rank and significance are reported from these mean scores. Black horizontal lines indicate no significant difference between methods. (d), (e), and (f) show finetuning performance for each task within the three benchmarks. Blue circles denote the mean score for each task, and red diamonds denote the average performance across all tasks within each benchmark.\", \"page\": 7, \"index\": 1, \"width\": 813, \"height\": 570}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-002.webp\", \"caption\": \"Fig. 5 GenoJEPA exhibits strong few-shot capabilities and feature versatility. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows probing performance for GenoJEPA and the baselines at different training-data scales across all benchmarks. Within each fold, the training and validation sets are stratified at proportions from 10% to 50% for each label while the test set is kept unchanged. Logistic regression with average pooling is used to assess the data efficiency of each method. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show probing performance under different pooling strategies and classifiers across all benchmarks. The boxplots summarize the distribution of representative scores across 55 tasks from all benchmarks. The center line denotes the median. The box limits denote the first and third quartiles. The whiskers denote the full data range.\", \"page\": 10, \"index\": 2, \"width\": 812, \"height\": 428}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-003.webp\", \"caption\": \"Fig. 4 GenoJEPA demonstrates favourable computational and memory efficiency. (a), (c), (e), and (g) report training time in ms, training memory in MB, inference time in ms, and inference memory in MB, respectively, for GenoJEPA and baselines with fewer than 10M parameters across different sequence lengths. (b), (d), (f), and (h) report the same metrics for GenoJEPA and baselines with more than 50M parameters. Experiments are conducted with a batch size of 1 on an A800 80 GB GPU. Each experiment is repeated for 10 epochs, and mean values are reported. In each epoch, the first 10 steps are excluded to remove cold-start effects. Average metrics are then computed over the next 100 steps. Both axes are shown on a logarithmic scale. Vertical dashed lines indicate sequence lengths that exceed model support or require memory beyond GPU capacity.\", \"page\": 8, \"index\": 3, \"width\": 815, \"height\": 574}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-004.webp\", \"caption\": \"Fig. 1 GenoJEPA learns genomic representations via joint-embedding prediction. (a) shows the pretraining framework. The input DNA sequence is split into non-overlapping patches, linearly projected into dense embeddings, and processed by a Transformer encoder. Token embeddings are then averaged to obtain a sequence representation. Following the LeJEPA formulation, the sequence is augmented into multiple local and global views through random cropping. GenoJEPA is optimized with an invariance loss that aligns semantic features across views together with a SIGReg loss that prevents representation collapse. (b) shows the downstream adaptation strategies for genomic tasks such as functional element identification. In resourcelimited settings, the pretrained encoder is frozen and the resulting sequence embeddings are passed to a lightweight task head for probing. In accuracy-sensitive settings, the entire GenoJEPA model is finetuned end to end together with a task head.\", \"page\": 4, \"index\": 4, \"width\": 815, \"height\": 469}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-005.webp\", \"caption\": \"Fig. 2 GenoJEPA maintains highly discriminative features under probing evaluation. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the probing win-loss comparison between GenoJEPA and the baselines across all benchmarks. A paired Wilcoxon signed-rank test at p = 0.05 is applied to the fold-wise test scores as a stability-aware paired comparison. The number of wins, ties, and losses is reported across 55 tasks from three benchmarks. (b) shows probing performance for each benchmark. The average and median performance across all tasks within each benchmark are reported from the representative scores. (c) shows task-level probing performance. On the horizontal axis, blue labels denote the Genomic Benchmarks, red labels denote the GUE Benchmarks, and green labels denote the Nucleotide Transformer Tasks.\", \"page\": 5, \"index\": 5, \"width\": 815, \"height\": 645}]"
motivation: 现有基因组基础模型多将DNA视为语言并采用自然语言处理的预训练目标，但DNA序列缺乏明确语义边界且包含大量进化噪声，导致计算开销大、表征判别能力有限且下游任务依赖昂贵的微调。
method: 该方法基于联合嵌入预测架构，结合连续分块与语义对齐，将优化目标从局部碱基重建转向潜在空间的语义对齐。
result: 在55个下游任务中，GenoJEPA展现出强大的表征能力和稳健的泛化性，同时减少了参数数量和计算成本；其生成的冻结语义向量支持轻量级无GPU分类器达到有竞争力的准确率。
conclusion: 该研究表明，GenoJEPA为高效训练和大规模基因组基础模型的广泛应用提供了一条实用途径。
---

## 摘要
解码基因组序列中编码的调控语法是计算生物学的核心目标。大多数现有的基因组基础模型将DNA视为一种语言，并采用自然语言处理的预训练目标。然而，DNA序列缺乏明确的语义边界，并且包含大量的进化噪声。在低维输入空间中进行核苷酸级别的重建因此会增加计算开销，并可能产生判别能力有限的表示。下游任务通常依赖于昂贵的微调，这限制了许多生物学实验室的实际应用。在此，我们提出了GenoJEPA，一个基于联合嵌入预测架构的基因组表示学习框架。GenoJEPA将连续分块与语义对齐相结合，将优化重点从局部碱基重建转移到潜在空间的语义对齐上。在55个下游任务中，GenoJEPA展现出强大的表示能力和稳健的泛化能力，同时减少了参数数量和计算成本。来自冻结的GenoJEPA生成的语义向量支持轻量级的无需GPU的分类器实现具有竞争力的准确度。这些结果为更大规模基因组基础模型的高效训练和广泛应用指明了一条实用路径。

## Abstract
Decoding the regulatory syntax encoded in genomic sequences is a central objective in computational biology. Most existing genomic foundation models treat DNA as a language and adopt pretraining objectives from natural language processing. DNA sequences, however, lack explicit semantic boundaries and contain substantial evolutionary noise. Nucleotide-level reconstruction in a low-dimensional input space can therefore increase computational overhead and may yield representations with limited discriminative capacity. Downstream tasks often depend on expensive finetuning, which restricts practical use in many biology laboratories. Here we present GenoJEPA, a genomic representation learning framework based on joint-embedding predictive architecture. GenoJEPA combines continuous patching with semantic alignment, shifting the optimization from local base reconstruction to semantic alignment in latent space. Across 55 downstream tasks, GenoJEPA shows strong representational capacity and robust generalization while reducing parameter count and computational cost. The resulting semantic vectors from frozen GenoJEPA support lightweight GPU-free classifiers to achieve competitive accuracy. These results suggest a practical route towards efficient training and broad application of larger-scale genomic foundation models.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将对这篇题为《From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture》的论文进行结构化、深入且客观的总结。

---

### **论文总结：GenoJEPA——基于联合嵌入预测架构的基因组表示学习**

#### **1. 核心问题与整体含义**
*   **研究动机**：解码基因组序列中的调控“语法”是计算生物学的核心目标。现有主流方法（如DNABERT-2, NT-v2）将DNA视为语言，采用掩码语言建模等源自自然语言处理的预训练目标。然而，DNA序列与人类语言存在本质差异：缺乏明确的语义边界（如单词），且包含大量进化噪声（如中性突变）。这导致模型在低维输入空间进行精确的核苷酸级重建时，可能浪费计算资源去拟合噪声，从而学到的表征判别能力有限。
*   **核心问题**：上述“重建式”预训练范式导致下游任务严重依赖昂贵的全参数微调，限制了模型在计算资源有限的生物学实验室中的广泛应用。
*   **整体含义**：本文提出了一种新的基因组表示学习范式——**GenoJEPA**。它借鉴计算机视觉中联合嵌入预测架构的思想，将优化目标从“重建输入”转变为“在潜在空间对齐语义”，旨在学习更具判别力、更易迁移的冻结表征，从而降低下游应用的门槛。

#### **2. 方法论**
*   **核心思想**：将基因组序列建模为更像自然图像而非文本的对象，通过在高维潜在空间中对齐不同数据增强视图的语义特征来学习表征，避免对低维核苷酸细节的重建。
*   **关键技术细节**：
    1.  **连续分块 (Continuous Patching)**：
        *   替代传统的k-mer或BPE分词。将输入DNA序列划分为不重叠的核苷酸片段（如16bp），通过线性投影直接映射为连续的稠密向量。
        *   **优势**：避免了离散词汇表膨胀问题；保留了片段内的生化依赖关系；压缩了序列长度，降低了计算开销。
    2.  **基于LeJEPA的预训练目标**：
        *   **多视图生成**：对同一序列进行随机裁剪，生成多个全局视图（捕获长程依赖）和局部视图（关注精细结构）。
        *   **不变性损失 (Invariance Loss)**：将所有视图的表征向全局视图表征的平均值对齐（使用均方误差）。
        *   **防坍缩正则化 (SIGReg Loss)**：采用“草图化各向同性高斯正则化”，引导潜在特征分布趋向于各向同性高斯分布，防止所有表征坍缩到同一个点。这是LeJEPA框架的理论贡献，避免了动量编码器等启发式设计。
        *   **总损失函数**: `L_total = (1 - α) * L_Invariance + α * L_SIGReg` （α=0.05）。
    3.  **模型架构**：
        *   主干网络基于ModernBERT Transformer编码器。
        *   设计了两个规模版本：轻量版 GenoJEPA-T (6M参数) 和基础版 GenoJEPA-B (52M参数)。

#### **3. 实验设计**
*   **预训练数据**：来自850个代表性物种的多物种基因组语料库（约1930亿核苷酸），与NT-v2相同。
*   **评估基准与任务**：
    *   涵盖三个广泛使用的基准测试集共55个子任务：
        1.  Genomic Benchmarks (9个任务)：跨物种分类、调控元件识别等。
        2.  GUE Benchmarks (28个任务)：转录因子结合位点、启动子、剪接位点预测等。
        3.  Nucleotide Transformer Tasks (18个任务)：人类表观遗传标记、增强子等预测。
*   **对比基线方法**：
    *   覆盖不同分词策略和架构的代表性模型：HyenaDNA (7M), CaduceusPh (8M), GROVER (87M), DNABERT-2 (117M), NT-v2 (494M)。
*   **评估协议**：
    *   **探测评估(Probing)**：冻结预训练主干网络权重，仅训练一个轻量级分类器（逻辑回归）。用于直接评估表征质量。
    *   **微调评估(Finetuning)**：对整个模型进行端到端微调。用于评估模型适应特定任务后的上限性能。
    *   **主要评价指标**：马修斯相关系数(MCC)，适用于类别不平衡的数据集。

#### **4. 资源与算力**
文中明确说明了预训练的算力消耗：
*   GenoJEPA-T **(6M参数)**:
    - GPU: `1 x RTX 3090 (24GB)`
    - 训练步数: `100,000`步
    - 耗时: `约12小时`
* GenoJEPA-B **(52M参数)**:
- GPU: `1 x A800 (80GB)`
- 训练步数: `500,000`步
- 耗时: `约150小时`

这表明GenoJEPA在相对适中的单卡算力下即可完成有效训练。

####5.**实验数量与充分性**
实验设计非常全面和系统化：

-主实验数量充足：

在55个下游任务上对所有基线模型进行了探测和微调两种模式的全面比较。

进行了详细的效率分析包括不同序列长度下的训练/推理时间和内存占用对比。

进行了少样本学习能力测试在不同比例的训练数据下进行评估。

分析了不同池化策略CLS平均最大和不同分类器KNN逻辑回归CatBoost对性能的影响。

消融实验丰富附录中包含了23项消融研究使用GenoJEPAT验证了关键设计选择包括：

数据增强策略物种多样性全局/局部视图数量及尺度随机突变/反向互补概率

架构设计分块大小滑动步长嵌入维度池化策略投影头设计

目标函数不变性距离准则SIGReg超参数切片数积分域正则化权重

优化设置学习率权重衰减

这些实验覆盖了方法设计的各个方面结果以表格形式详细呈现支持了核心结论并提供了实用的超参指导。整体而言实验设计严谨对比公平遵循了统一的评估协议例如探测时统一使用平均池化和逻辑回归并使用相同的10折交叉验证流程保证了结果的客观性和可比性。

####6.**主要结论与发现**

在高维潜在空间进行语义对齐而非低维输入空间重建能学到判别力更强更易迁移的基因组表征。

GenoJEPAB52M在探测评估中平均排名第一其冻结表征质量显著优于参数量大近10倍的NTv2494M表明预训练目标比单纯扩大参数量更重要。

在微调模式下GenoJEPAB仍能取得最佳平均性能证明了其作为强大基础模型的潜力。

GenoJEPAT6M在参数量相近的模型中表现最优甚至优于某些参数量大得多的基线展现了卓越的参数效率。

GenoJEPA的计算和内存效率优于传统Transformer基线GROVERDNABERT2NTv2并且在大多数测试序列长度下也优于理论复杂度更低的CaduceusPh和HyenaDNA表现出更稳定的实际运行性能。

GenoJE PA具有出色的少样本学习能力仅用10%的训练数据即可达到其他基线用50%数据或全量数据的性能水平表明其对标注数据稀缺场景友好。

平均池化在探测时表现最好而分类符CLS令牌在微调时表现更好这为不同应用场景提供了实用指导线性分类器逻辑回归通常足以利用其高质量表征获得良好性能无需复杂非线性分类器。

####7.**优点**

范式创新首次将联合嵌入预测架构JE PA成功应用于基因组表示学习为解决DN A序列建模中的噪声问题和下游应用门槛高的问题提供了新思路。

方法实用性强提出的连续分块策略巧妙借鉴计算机视觉思想有效平衡了信息保留与计算效率强调冻结表征的质量使其特别适合资源有限的实验室环境只需轻量级GPUfree分类器即可部署证明了其推动技术民主化的潜力。

理论支撑采用LeJE PA框架及其SIGReg损失为防坍缩机制提供了理论依据减少了启发式超参数提升了训练的稳定性与可复现性。

实验验证极其全面系统性的多维度评估探测微调效率少样本泛化能力消融分析远超常规论文标准结论说服力强代码和数据开源承诺高透明度附录信息详实可作为后续研究的宝贵参考。


####8.**不足与局限**

序列长度限制当前预训练的上下文长度为4096bp这适用于基因级别任务但不足以建模更长范围的染色质相互作用例如拓扑关联域TAD边界识别等尽管效率分析表明有扩展潜力但未在实际长程任务上验证。


模型规模探索有限最大的模型仅52 M参数虽然展示了高效性但未探索百亿或千亿参数的更大规模下的缩放定律Scaling Laws以及性能天花板。


生物学解释性不足论文聚焦于表示学习的工程性能和实用性但对学到的潜在空间具体编码了哪些生物学规律例如特定的调控基序或进化约束缺乏深入的定性和可解释性分析。


基准任务的局限性虽然覆盖了55个任务但主要集中在分类问题上对于生成式任务例如非编码区变异效应预测或新序列设计以及更复杂的多模态整合任务的适用性尚未验证。


潜在的偏差风险预训练语料库虽涵盖多物种但仍以哺乳动物脊椎动物为主且依赖于参考基因组的质量可能引入采样偏差影响对高度可变区域或非模式生物的表征能力。


完

好的，我们继续从“不足与局限”部分开始，补充其后的内容。

#### **8. 不足与局限**
*   **序列长度限制**：当前预训练的上下文长度为4096bp，这适用于基因级别任务，但不足以建模更长范围的染色质相互作用（例如拓扑关联域TAD边界识别等）。尽管效率分析表明有扩展潜力，但未在实际长程任务上验证。
*   **模型规模探索有限**：最大的模型仅52M参数。虽然展示了卓越的参数效率，但未探索百亿或千亿参数的更大规模下的缩放定律（Scaling Laws）以及性能天花板。这限制了对其作为“基础模型”潜力的全面评估。
*   **生物学解释性不足**：论文聚焦于表示学习的工程性能和实用性，但对学到的潜在空间具体编码了哪些生物学规律（例如特定的调控基序、进化约束或功能模块）缺乏深入的定性和可解释性分析。表征的“语义”具体是什么仍是一个黑箱。
*   **基准任务的局限性**：虽然覆盖了55个任务，但主要集中在分类问题上。对于生成式任务（例如非编码区变异效应预测、新序列设计）以及更复杂的多模态整合任务（如结合表观基因组或3D结构信息）的适用性尚未验证。
*   **潜在的偏差风险**：预训练语料库虽涵盖多物种，但仍以哺乳动物/脊椎动物为主，且依赖于参考基因组的质量。这可能导致模型对高度可变区域、结构变异或非模式生物的表征能力存在偏差。

#### **9. 未来方向**
基于本研究的成果与局限，可以展望以下几个有潜力的未来研究方向：
1.  **扩展上下文长度**：将JEPA架构与高效的Transformer变体（如Mamba、Longformer）结合，以处理染色体级别的长序列输入，从而研究长程调控和三维基因组组织。
2.  **探索缩放定律**：在更大规模的参数和数据上训练GenoJEPA变体，系统性地研究其性能随规模增长的规律，并评估其在更复杂任务上的涌现能力。
3.  **增强可解释性**：开发针对JEPA学习到的基因组表征的解释工具。例如，通过潜在空间插值、扰动分析或特征可视化技术来揭示表征所对应的具体生物学功能和调控逻辑。
4.  **迈向生成与多模态**：将联合嵌入预测架构扩展为生成式模型（如掩码生成式JEPA），用于可控的DNA序列生成或编辑。同时，整合多组学数据（如染色质可及性、Hi-C），构建统一的多模态基因组基础模型。
5.  **应用于临床与发现**：利用其高效、高质量的冻结表征优势，快速构建针对特定疾病（如癌症驱动突变识别）或性状（如作物农艺性状预测）的诊断和发现工具链。

#### **10. 总结评价**
总体而言，《From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture》是一篇高质量、具有范式创新意义的研究论文。

*   **核心贡献明确**：它成功地将计算机视觉中的联合嵌入预测架构引入基因组学领域，为解决传统重建式预训练范式的固有缺陷提供了新颖且有效的解决方案。
*   **方法设计精巧且实用**：“连续分块”策略和LeJEPA框架的结合在理论上有依据（SIGReg防坍缩），在实践中高效（单卡可训），其强调高质量冻结表征的理念显著降低了下游应用的门槛。
*   **实验验证极为充分且严谨**：通过大规模、多维度的基准测试、效率分析和消融实验，全面而有力地证明了GenoJEPA在表征质量、参数效率、计算效率和少样本学习能力上的显著优势。附录中详实的超参研究和开源承诺极大地提升了工作的可复现性和参考价值。

尽管存在对长序列建模、可解释性和任务广度等方面的局限——这在任何开创性工作中都难以避免——但本文无疑为基因组表示学习领域开辟了一条富有前景的新路径。它不仅仅提出了一个性能更优的模型，更重要的是推动整个领域重新思考“如何为DNA序列这一特殊‘语言’设计更本质的预训练目标”。这项工作有望加速计算生物学工具在资源有限环境中的普及和应用。

（完）
