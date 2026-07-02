---
title: "MCD Stitcher: An open-source tool for whole-slide stitching and conversion of Imaging Mass Cytometry data"
title_zh: MCD Stitcher：一种用于全切片拼接和成像质谱流式数据转换的开源工具
authors: "Chaurasia, P."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.26.732348v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 提供了用于成像质谱流式数据的全切片拼接工具
tldr: 成像质谱流式(IMC)需采集多个ROI并拼接成全玻片图像，但.mcd专有格式限制与标准分析工具兼容。MCD Stitcher是一款开源Python工具，可将.mcd文件自动拼接并转换为OME-TIFF格式，支持矩形/多边形ROI及可变像素大小，采用内存感知分块读取处理大文件。输出保留空间、通道和采集元数据，可直接用于QuPath、napari等工具。该工具提供可重现工作流，摆脱厂商依赖，实现全玻片空间分析。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决IMC全玻片重建和格式转换问题，避免依赖专有软件，提升数据互操作性。
method: 开发MCD Stitcher Python包，自动读取.mcd，拼接多种形状ROI，使用内存感知分块写入生成OME-TIFF，保留元数据。
result: 生成的OME-TIFF可直接被QuPath、napari等标准工具使用，实现全玻片空间分析。
conclusion: MCD Stitcher提供可重现工作流，转换原始IMC数据为互操作格式，便于全玻片分析。
---

## 摘要
成像质谱流式（IMC）结合金属标记抗体与激光剥蚀质谱，生成组织切片的高度多重空间图像。然而，单个感兴趣区域（ROI）内可采集的区域受硬件和软件限制，需要将大组织成像为多个拼接的ROI。将这些ROI重建为全切片图像需要额外处理，而专有的.mcd文件格式可能阻碍与标准生物图像分析工作流的集成。在此，我们介绍MCD Stitcher，一个用于将.mcd文件转换为具有自动全切片拼接功能的OME-TIFF图像的开源Python包。该工具支持矩形和多边形ROI，适应ROI之间可变的像素大小，并在数据摄入期间使用内存感知的分块读取，以在标准工作站上处理大型数据集。生成的OME-TIFF输出保留了空间、通道和采集元数据，便于在QuPath、napari和ImageJ/Fiji等工具中进行下游分析。MCD Stitcher提供了一种可重复的工作流，用于将原始IMC数据转换为互操作的图像格式，从而无需依赖供应商特定软件即可实现全切片空间分析。

## Abstract
Imaging Mass Cytometry (IMC) combines metal-tagged antibody labelling with laser ablation mass spectrometry to generate highly multiplexed spatial images of tissue sections. However, the area that can be acquired within a single region of interest (ROI) is limited by hardware and software constraints, requiring large tissues to be imaged as multiple tiled ROIs. Reconstructing these ROIs into whole-slide images requires additional processing, while the proprietary .mcd file format can hinder integration with standard bioimage analysis workflows. Here, we present MCD Stitcher, an open-source Python package for converting .mcd files into OME-TIFF images with automated whole-slide stitching. The tool supports rectangular and polygonal ROIs, accommodates variable pixel sizes between ROIs, and uses memory-aware chunked reading during data ingestion to process large datasets on standard workstations. The generated OME-TIFF outputs preserve spatial, channel, and acquisition metadata for downstream analysis in tools such as QuPath, napari, and ImageJ/Fiji. MCD Stitcher provides a reproducible workflow for converting raw IMC data into interoperable image formats, enabling whole-slide spatial analysis without reliance on vendor-specific software.