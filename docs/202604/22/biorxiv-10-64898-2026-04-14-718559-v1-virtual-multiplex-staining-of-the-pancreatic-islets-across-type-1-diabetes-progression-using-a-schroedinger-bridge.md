---
title: Virtual multiplex staining of the pancreatic islets across type 1 diabetes progression using a Schroedinger bridge
title_zh: 基于薛定谔桥的1型糖尿病进展过程中胰岛虚拟多重染色
authors: "Shen, Y., Cho, W. J., Joshi, S., Wen, B., Naganathanhalli, S., Beery, M., Grubel, C. R., Sivasubramanian, A., Forjaz, A., Grahn, M. P., Dequiedt, L., Huang, Y., Han, K. S., Wu, F., Pedro, B. A., Wood, L. D., Chen, T., Hruban, R. H., Kusmartseva, I., Atkinson, M. A., Wirtz, D., Kiemen, A. L."
date: 2026-04-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.14.718559v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: "组织病理学中H&E到IHC的染色转换"
tldr: "针对传统免疫组化（IHC）染色成本高、耗时长的挑战，本研究提出了一种名为SMILE的薛定谔桥扩散模型，用于将H&E染色图像虚拟转换为多重免疫组化（mIHC）图像。该模型通过直接映射源图像到目标图像，有效克服了GAN模型的幻觉和结构失真问题。在胰岛组织及乳腺癌数据集上的实验证明，SMILE在保持组织结构和蛋白质分布准确性方面优于现有方法，为高通量蛋白质组学推断和数字病理研究提供了高效工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: "传统的H&E染色缺乏分子信息，而多重免疫组化成本高昂且复杂，现有的GAN模型在进行虚拟染色转换时容易产生幻觉和结构失真。"
method: "提出SMILE框架，利用薛定谔桥扩散模型实现从H&E到mIHC的直接映射，避免了中间高斯噪声步骤以更好地保留组织结构。"
result: 在胰腺和乳腺癌数据集上的实验表明，SMILE在图像保真度、抗体特异性指标及病理学家评估中均优于GAN模型，并能生成准确的3D组织图谱。
conclusion: "SMILE为从存档H&E图像中进行高通量蛋白质组学推断提供了一个可扩展且高保真的虚拟染色方案，具有显著的临床和科研应用潜力。"
---

## 摘要
传统的苏木精-伊红（H&E）染色能够观察组织形态，但缺乏关于细胞分子状态的信息。免疫组织化学（IHC）技术标记组织中的特定蛋白质，从而能够区分在H&E染色中可能无法检测到的相关结构。然而，IHC过程复杂、昂贵且耗时，特别是多重IHC（mIHC），这限制了其在大规模队列中的应用。使用生成对抗网络（GANs）等生成式人工智能模型将H&E转换为IHC染色是解决该问题的一种方案。然而，GANs在分布外采样时不稳定，且容易产生幻觉或模式崩溃，限制了其在具有挑战性的图像转换任务中的准确性。为了解决这一问题，该领域近期转向了扩散模型。在此，我们介绍了用于多重免疫标签估计的薛定谔桥（SMILE）。与通过中间高斯噪声从源映射到目标的传统扩散模型不同，薛定谔桥扩散模型跳过了这一步，并已被证明在图像转换过程中能更好地保留结构。为了测试SMILE的性能，我们从胰腺器官捐献者中生成了一个包含高保真H&E-mIHC图像对的大型队列，目标蛋白包括胰岛素、胰高血糖素和CD3。我们的数据集在1型糖尿病状态、胰腺解剖位置、年龄和性别方面进行了充分采样。利用该队列，我们通过一个结合了纹理、分布、抗体特异性指标以及盲法病理学家审查的综合评估框架，证明了SMILE优于GANs。我们进一步证实了SMILE能够从外部站点生成的H&E图像中生成准确的mIHC图像、执行全切片图像转换，并在非糖尿病、自身抗体阳性和1型糖尿病捐献者组织中生成逼真的胰岛三维图谱。最后，我们对乳腺癌中配对的H&E到HER2和Ki67图像进行了染色转换，证实了SMILE在多种染色转换应用中的优越性。总的来说，该框架为从存档H&E图像中进行高通量蛋白质组学推断提供了一个可扩展的流程，为胰腺研究和数字病理学带来了变革性的潜力。

## Abstract
Classical hematoxylin and eosin (H&E) staining enables review of tissue morphology but lacks information regarding the molecular state of cells. Immunohistochemical (IHC) techniques label specific proteins in tissue, allowing differentiation of relevant structures that may go undetectable in H&E. However, the IHC process is complex, expensive, and time-consuming, especially for multiplex IHC (mIHC) limiting its use in large cohorts. Stain conversion of H&E to IHC using generative artificial intelligence models such as generative adversarial networks (GANs) represent one solution to this problem. However, GANs are unstable during out of distribution sampling and are prone to hallucinations or mode collapse, limiting their accuracy in challenging image conversion tasks. To address this, the field has recently turned to diffusion models. Here, we introduce Schrodinger-bridge for Multiplex ImmunoLabel Estimation (SMILE). Unlike conventional diffusion models that map from source to target through an intermediate Gaussian noise, Schrodinger-bridge diffusion models skip this step and have been shown to better preserve structures during image translation.

To test the performance of SMILE, we generated a large cohort of high-fidelity H&E-mIHC image pairs from pancreatic organ donors, targeting insulin, glucagon, and CD3. Our dataset well-sampled across type-1 diabetes status, pancreas anatomical location, age, and sex. Using this cohort, we demonstrate the superiority of SMILE compared to GANs via a comprehensive evaluation framework incorporating texture, distribution, and antibody-specific metrics, as well as blinded pathologist reviews. We further confirmed the ability of SMILE to generate accurate mIHC images from H&Es generated at an external site, to perform whole slide image conversion, and to generate realistic three-dimensional maps of the pancreatic islets in non-diabetic, auto-antibody positive, and type-1 diabetic donor tissue. Finally, we performed stain conversion of paired H&E to HER2 and Ki67 images in breast cancer, confirming the superiority of SMILE in diverse stain conversion applications. Collectively, this framework provides a scalable pipeline for high-throughput proteomic inference from archival H&Es, providing transformative potential for pancreatic research and digital pathology.