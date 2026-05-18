---
title: Interpretable Predictive Modeling for Medical Data Using Boolean Rule-aware Regression
title_zh: 基于布尔规则感知回归的医疗数据可解释预测建模
authors: "Eskandarian, M., Malekpour, S. A."
date: 2026-05-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.14.725084v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 用于癌症检测的可解释预测模型
tldr: 针对临床预测中深度学习模型缺乏透明度的问题，本文提出了一种基于回归的布尔规则（RBBR）框架。该方法通过从患者数据中自动提取简洁的逻辑规则（如特征的“与”组合），并结合岭回归进行疾病风险预测。在肺癌、乳腺癌和糖尿病等六个医疗数据集上的实验表明，RBBR不仅能提供高度可解释的临床决策支持，还能保持较强的预测性能，有效弥合了模型准确性与临床实用性之间的鸿沟。
source: biorxiv
selection_source: fresh_fetch
motivation: 临床实践需要高精度且透明可解释的预测模型，而传统的深度学习黑盒模型难以满足医疗决策的信任和监管要求。
method: 提出RBBR框架，通过提取临床特征的布尔逻辑组合作为回归输入，并利用岭回归和贝叶斯信息准则筛选出最简洁且具预测力的规则集。
result: 在六个真实医疗数据集上，RBBR生成了符合临床逻辑的规则，实现了高达0.92的解释力（R2）以及具有竞争力的分类性能。
conclusion: RBBR通过提供与临床推理一致的透明决策规则，增强了医生对预测结果的验证能力，有助于在日常诊疗中实现更安全的决策支持。
---

## 摘要
目的：在临床实践中，疾病风险的准确预测必须伴随透明、人类可理解的解释，以支持诊断信心、指导治疗决策，并符合伦理和监管标准。虽然深度神经网络在癌症检测和糖尿病风险分层等任务中取得了很高的预测性能，但其黑盒性质阻碍了临床医生理解预测背后的推理，严重限制了信任以及在患者护理中的安全集成。方法：我们提出了基于回归的布尔规则（RBBR），这是一个直接从患者数据中自动推导临床可解释布尔规则的框架。RBBR 生成最多包含三个临床特征的人类可读合取式（逻辑“与”组合），将其转化为岭回归的输入以预测二分类或多分类疾病结果，通过正则化系数估计规则重要性，并使用贝叶斯信息准则选择最简洁且具预测性的规则集。结果：应用于六个真实世界的医学数据集（肺癌筛查与分期、威斯康星州及诊断性乳腺癌、心力衰竭和早期糖尿病风险），RBBR 一致地产生了简洁且具有临床意义的规则——例如糖尿病中特定性别的症状组合、乳腺癌中不同的组织病理学亚群，以及肺癌中的症状与风险因素交互作用——具有强大的解释力（R2 高达 0.92）和具有竞争力的区分度。结论：通过提供符合临床推理的逻辑、透明的决策规则（如“如果症状 A 且 B，则为高风险”），RBBR 弥合了预测准确性与临床实用性之间的鸿沟，使临床医生能够验证预测、识别高风险患者、对亚群进行分层，并增强常规护理中的共同决策。

## Abstract
Purpose: In clinical practice, accurate prediction of disease risk must be accompanied by transparent, human-understandable explanations to support diagnostic confidence, guide therapeutic decisions, and meet ethical and regulatory standards. While deep neural networks achieve high predictive performance in tasks such as cancer detection and diabetes risk stratification, their black-box nature prevents clinicians from understanding the reasoning behind predictions, severely limiting trust and safe integration into patient care. Methods: We present Regression-Based Boolean Rule (RBBR), a framework that automatically derives clinically interpretable Boolean rules directly from patient data. RBBR generates human-readable conjunctions (logical AND combinations) of up to three clinical features, transforms them into inputs for ridge regression to predict binary or multi-class disease outcomes, estimates rule importance via regularized coefficients, and selects the most parsimonious and predictive rule sets using the Bayesian Information Criterion. Results: Applied to six real-world medical datasets (lung cancer screening and staging, Wisconsin and diagnostic breast cancer, heart failure, and early-stage diabetes risk), RBBR consistently produced concise, clinically meaningful rules - e.g., gender-specific symptom combinations in diabetes, distinct histopathological subpopulations in breast cancer, and symptom-risk factor interactions in lung cancer - with strong explanatory power (R2 up to 0.92) and competitive discrimination. Conclusion: By delivering logical, transparent decision rules aligned with clinical reasoning (if symptom A and B, then high risk), RBBR bridges the gap between predictive accuracy and bedside usability, enabling clinicians to validate predictions, identify high-risk patients, stratify subpopulations, and enhance shared decision-making in routine care.