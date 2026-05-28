---
title: Multi-Algorithm Machine Learning Benchmarking for Pan-Cancer Classification from Tumour-Educated Platelet RNA Sequencing
title_zh: 基于肿瘤教育血小板RNA测序的泛癌分类多算法机器学习基准测试
authors: "Ray, S., Zalawadia, D. H., Bhate, V., Chakravarthy, T. D., Chetty, A. G."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.22.727079v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 利用机器学习从血小板RNA测序进行泛癌分类
tldr: 对280个肿瘤教育血小板RNA-seq样本（6种癌症+健康对照），采用7种机器学习分类器进行基准测试，通过分层5折交叉验证和2000次自助法量化不确定性。多项逻辑回归表现最佳（宏F1=0.522，宏AUC=0.869）。SHAP分析揭示IFITM3为全局标志物，并发现癌症特异性基因特征。研究支持TEP转录组学作为多类液体活检平台。
source: biorxiv
selection_source: fresh_fetch
motivation: 系统评估多种机器学习算法在泛癌分类中的性能，并量化统计不确定性。
method: 对280个全血血小板RNA-seq样本进行标准化预处理和归一化，使用7种监督分类器进行分层5折交叉验证和留存测试集评估，通过2000次自助法计算置信区间。
result: 多项逻辑回归取得最高宏F1分数0.522和宏AUC 0.869，随机森林的SHAP分析识别IFITM3为全局生物标志物及多种癌症特异性基因。
conclusion: TEP转录组学具有作为多类液体活检平台的诊断潜力，本研究提供了方法透明、可重复的基准框架。
---

## 摘要
肿瘤教育血小板（TEPs）携带可通过全血RNA测序获得的癌症类型特异性RNA特征，但此前尚未对GSE68086数据集（该领域的主要参考队列）进行系统性的多算法基准测试并量化统计不确定性。我们应用端到端的转录组学和机器学习框架，分析了来自六种癌症类型（非小细胞肺癌、结直肠癌、多形性胶质母细胞瘤、肝胆癌、乳腺癌和胰腺癌）及健康供体的280个全血血小板RNA-seq样本。经过标准化的预处理和归一化流程，我们对七种监督分类器——逻辑回归、SVM（RBF）、XGBoost、LightGBM、随机森林、K近邻和多层感知器——进行了基准测试，采用分层5折交叉验证和独立测试集。统计不确定性通过2000次重采样百分位自助法置信区间量化。多项逻辑回归取得了最高的测试宏F1分数（0.522）和宏平均ROC-AUC（0.869），均显著高于七类随机水平（1/7 ≈ 0.14）。对随机森林分类器的SHAP分析显示IFITM3是全局主导的TEP生物标志物；癌症类型特异性判别因子包括ATP5PD（肝胆癌）、C6orf62（非小细胞肺癌和胰腺癌）、VPS13C（健康供体）和TMSB4Y（乳腺癌）。基因本体论和KEGG通路富集分析证实了所识别转录组特征的生物学特异性。这些结果支持TEP转录组学作为多分类液体活检平台的诊断潜力，并为未来的血液癌症分类研究提供了方法学透明、可重复的参考框架。

## Abstract
Tumour-educated platelets (TEPs) carry cancer-type-specific RNA signatures accessible through whole-blood RNA sequencing, but systematic multi-algorithm benchmarking with quantified statistical uncertainty had not been applied to the GSE68086 dataset, the fields primary reference cohort. We applied an end-to-end transcriptomic and machine learning framework to 280 whole-blood platelet RNA-seq samples from six cancer types (non-small cell lung cancer, colorectal cancer, glioblastoma multiforme, hepatobiliary cancer, breast cancer, and pancreatic cancer) and healthy donors. After a standardised preprocessing and normalisation pipeline, seven supervised classifiers - Logistic Regression, SVM (RBF), XGBoost, LightGBM, Random Forest, K-Nearest Neighbours, and a Multilayer Perceptron were benchmarked using stratified 5-fold cross-validation and a held-out test set. Statistical uncertainty was quantified via 2,000-resample percentile bootstrap confidence intervals. Multinomial Logistic Regression achieved the highest test macro F1-score (0.522) and macro-averaged ROC-AUC (0.869), both substantially above the seven-class chance level (1/7 {approx} 0.14). SHAP analysis of the Random Forest classifier identified IFITM3 as the globally dominant TEP biomarker; cancer-type-specific discriminators included ATP5PD (hepatobiliary cancer), C6orf62 (NSCLC and pancreatic cancer), VPS13C (healthy donors), and TMSB4Y (breast cancer). Gene Ontology and KEGG pathway enrichment corroborated the biological specificity of identified transcriptomic signatures. These results support the diagnostic potential of TEP transcriptomics as a multi-class liquid biopsy platform and provide a methodologically transparent, reproducible reference framework for future blood-based cancer classification studies.