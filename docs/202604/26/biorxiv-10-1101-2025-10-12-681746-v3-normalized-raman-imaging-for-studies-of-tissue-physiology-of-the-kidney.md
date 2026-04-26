---
title: Normalized Raman Imaging for Studies of Tissue Physiology of the Kidney
title_zh: 归一化拉曼成像用于肾脏组织生理学研究
authors: "Trim, W. V., Oh, S., Diakova, M., Petrova, K., Ichimura, T., Takakura, A., Karmakar, R., Norrelykke, S. F. F., Peshkin, L., Bonventre, J. V., Kirschner, M. W."
date: 2026-04-23
pdf: "https://www.biorxiv.org/content/10.1101/2025.10.12.681746v3.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 无标记器官病理成像的计算校正
tldr: 传统组织学方法因固定和染色过程易导致组织变形及脂质丢失，限制了定量分析。本研究提出归一化拉曼成像（NoRI）技术，利用受激拉曼散射实现蛋白质和脂质的无标记、高分辨率定量成像。通过计算校正光散射，NoRI能精确测量生物量并保留组织结构。在小鼠肾脏研究中，该技术成功实现了小管类型、解剖区域及性别的精准分类，并揭示了性别差异及急性肾损伤后的动态病理变化，为组织生理学研究提供了强有力的定量分析平台。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统组织学方法在处理过程中会破坏细胞结构并丢失脂质等关键分子，严重限制了病理分析的重现性和定量精度。
method: 开发了归一化拉曼成像（NoRI）技术，通过蛋白质、脂质和水的组合拉曼信号对光散射进行计算校正，实现无标记的定量生物量测量。
result: "NoRI在小鼠肾脏结构和性别分类中达到了极高的准确率（F1>0.9），发现了显著的性别特异性生物量差异，并精确追踪了急性肾损伤后的恢复动态。"
conclusion: NoRI为复杂组织的定量分析和特征发现提供了一个高分辨率、可重复且超越传统组织学的强大诊断与研究平台。
---

## 摘要
组织学是临床病理学的基石，也是许多医学领域的重要工具。然而，依赖于固定、包埋、切片和染色的传统组织学方法会扭曲细胞结构，提取出脂质等关键分子，并引入严重限制可重复性的变异性。在此，我们提出了归一化拉曼成像（NoRI），这是一种应用于器官病理学的受激拉曼散射技术。NoRI 能够以高空间分辨率对蛋白质和脂质进行定量的、无标记的测量。NoRI 通过利用蛋白质、脂质和水的组合拉曼信号对每个信号进行计算校正，克服了来自均匀组织的异质光散射。这使得在保留组织结构的同时能够进行定量的生物量测量，从而促进了卷积神经网络的高级分析和特征发现。我们将 NoRI 应用于小鼠肾脏，结果表明，这种成像技术可用于从低至 132.5μm² 的区域中准确分类肾小管类型（中值 F1 [相对于人工标注的精确率和召回率的调和平均值] = 0.93）、解剖区域（F1 = 0.91）和生物性别（F1 = 0.97）。在这些情况下，NoRI 揭示了新的性别特异性特征，包括雌性肾小管中较高的细胞质脂质（+6.9mg/mL；p=0.028）、核蛋白（+26.3mg/mL；p<0.001）和毛细血管蛋白浓度（+3.1mg/mL；p<0.001），以及细胞内脂滴形态的差异。在急性肾损伤（AKI）的时间序列模型中，NoRI 捕捉到了蛋白质和脂质组织的动态变化，在损伤后第 2 天最为显著（F1 = 0.97），并量化了 25 天内刷状缘结构和脂滴的恢复情况。脂质测量对于 AKI 中特征分类和发现的高准确性尤为关键（F1 = 1.0）。这些结果确立了 NoRI 作为一个可重复、高分辨率且完全定量的组织分析和特征发现框架，远超传统组织学。通过保留组织结构并准确量化脂质和蛋白质，NoRI 提供了一个独特的平台来探索和识别复杂组织中未知的生物现象，并作为一种强大的组织病理学诊断工具。

## Abstract
Histology is the cornerstone of clinical pathology and an essential tool for many areas of medicine. Nevertheless, conventional histological methods, which rely on fixation, embedding, sectioning, and staining, distort cellular architecture, extract key molecules such as lipids, and introduce variability that severely limits reproducibility. Here, we present Normalized Raman Imaging (NoRI), a form of stimulated Raman scattering applied to organ pathology. NoRI enables quantitative, label-free measurements of proteins and lipids at high spatial resolution. NoRI overcomes heterogeneous light scattering from homogeneous tissues by computationally correcting each signal by the combined Raman signals of protein, lipid, and water. This enables quantitative biomass measurements while preserving tissue architecture, thereby facilitating advanced analysis by convolutional neural networks and feature discovery. Here we apply NoRI to the mouse kidney, showing that such imaging can be used to accurately classify tubule types (median F1 [harmonic mean of precision and recall against manual annotation]=0.93), anatomical regions (F1=0.91), and biological sex (F1=0.97) from regions as small as 132.5m^2. Under these circumstances, NoRI has revealed novel sex-specific features, including higher cytoplasmic lipid (+6.9mg/mL; p=0.028), nuclear protein (+26.3mg/mL; p<0.001), and capillary protein concentrations (+3.1mg/mL; p<0.001) in female tubules, along with differences in intracellular lipid droplet morphology. In a time-course model of acute kidney injury (AKI), NoRI captured dynamic changes in protein and lipid organization, most pronounced at day 2 post-injury (F1=0.97), and quantified recovery of brush border structures and lipid droplets over 25 days. Lipid measurements were particularly critical for the high accuracy of feature classification and discovery in AKI (F1=1.0). These results establish NoRI as a reproducible, high-resolution, and fully quantitative framework for tissue analysis and feature discovery, far surpassing conventional histology. By preserving tissue architecture and accurately quantifying lipids and proteins, NoRI provides a unique platform to explore and identify unknown biological phenomena in complex tissues, and present as a powerful diagnostic tool for histopathology.