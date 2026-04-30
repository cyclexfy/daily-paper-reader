---
title: "BioEngine: scalable execution and adaptation of bioimage AI through agent-readable interfaces"
title_zh: BioEngine：通过代理可读接口实现生物图像人工智能的可扩展执行与适配
authors: "Mechtel, N., Källander, H. D., Cheng, S., Zhang, H., AI4Life Horizon Europe Program Consortium,, Ouyang, W."
date: 2026-04-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.19.719496v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 生物图像AI基础模型的执行与适配
tldr: 尽管基础模型和资源库推动了生物图像AI的发展，但生物学家在现有硬件上运行和适配这些模型仍面临挑战。BioEngine作为一个连接AI模型与可扩展计算资源的执行与适配层，支持从笔记本到集群的部署。它通过AI代理接口，让科学家能以自然语言描述目标，实现模型筛选、浏览器端微调、实时智能显微成像及分析应用部署，显著降低了生物图像AI的使用门槛。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决生物学家在现有硬件上难以运行、适配和扩展复杂生物图像AI模型的问题。
method: 开发了BioEngine系统，作为AI模型与可扩展计算资源之间的执行层，并提供AI代理可读的接口。
result: 科学家可以通过向AI代理描述目标，轻松完成模型筛选、在线微调、智能显微成像及应用部署。
conclusion: BioEngine通过简化模型执行与适配流程，极大地提升了生物图像AI的可访问性和扩展性。
---

## 摘要
基础模型和精选资源库已经改变了生物图像人工智能（bioimage AI），但大多数生物学家仍无法在现有硬件上轻松运行、适配或扩展这些模型。BioEngine 填补了这一空白，它作为精选 AI 与可扩展计算之间的执行与适配层，可部署在笔记本电脑、工作站或集群上。科学家只需向 AI 代理描述其目标，即可筛选模型、在浏览器中进行微调、实现实时智能显微成像并部署分析应用。

## Abstract
Foundation models and curated repositories have transformed bioimage AI, yet most biologists cannot readily run, adapt, or extend them on available hardware. BioEngine lls this gap as the execution and adaptation layer between curated AI and scalable compute, deployable on a laptop, workstation, or cluster. Scientists then screen models, ne-tune from the browser, enable real-time smart microscopy, and deploy analysis applications, all by describing their goal to an AI agent.