# Towards Autonomous Decision-Making: A Survey of Multimodal Medical Reasoning

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![arXiv](https://img.shields.io/badge/arXiv-Coming%20Soon-b31b1b.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

**📝 Paper source: [`paper/`](paper/) | ✒️ [Citation](#-citation)**

> **Towards Autonomous Decision-Making: A Survey of Multimodal Medical Reasoning**  
> *Haochao Ying*  
> 
> A survey of multimodal medical reasoning models, taxonomies, benchmarks, and resources for increasingly autonomous, evidence-grounded clinical decision-making.

<p align="center">
  <img src="images/overview.png" alt="Overview" width="800"/>
</p>

<p align="center">
  <img src="images/pipeline.png" alt="Pipeline" width="800"/>
</p>

---

## 📢 News

- 🔥 **[2025/10/22]** Repository initialized with survey structure
- 📚 **[2025/10/22]** Started collecting papers on medical reasoning foundation models
- 🚧 **[Work in Progress]** Survey paper under active development

<details>
<summary>📰 <b>Show More News</b></summary>

- ✍️ Paper writing in progress
- 📊 Collecting and organizing relevant literature
- 🎯 Building comprehensive taxonomy of medical reasoning approaches

</details>

---

## 📋 Table of Contents

- [About](#about)
- [Overview](#overview)
- [Introduction](#introduction)
- [💬 Reasoning in Medical Large Language Models](#-reasoning-in-medical-large-language-models)
  - [2.1 Training-free Strategies](#21-training-free-strategies)
  - [2.2 Training Strategies](#22-training-strategies)
  - [2.3 Extrinsic Strategies](#23-extrinsic-strategies)
- [🎯 Medical Multimodal Reasoning](#-medical-multimodal-reasoning)
  - [3.1 Background and Taxonomy](#31-background-and-taxonomy)
  - [3.2 Radiological Reasoner](#32-radiological-reasoner)
    - [3.2.1 Med-VQA](#321-med-vqa-reasoning-over-medical-images)
    - [3.2.2 Diagnostic Reasoning](#322-diagnostic-reasoning-and-report-generation)
    - [3.2.3 Pixel/Voxel Grounding](#323-reasoning-to-regions-pixelvoxel-level-grounding)
    - [3.2.4 Ultrasound Reasoning](#324-ultrasound-reasoning)
  - [3.3 Temporal Reasoner](#33-temporal-reasoner)
  - [3.4 Pathology Reasoner](#34-pathology-reasoner)
  - [3.5 Genomics Reasoner](#35-genomics-reasoner)
  - [3.6 Surgical Reasoner](#36-surgical-reasoner)
- [📊 Benchmarking Medical Reasoning](#-benchmarking-medical-reasoning)
  - [4.1 Benchmark Categories](#41-benchmark-categories)
  - [4.2 Evaluation Metrics](#42-evaluation-metrics)
  - [4.3 Performance Analysis](#43-performance-analysis)
- [🗂️ Medical Domain Datasets](#-medical-domain-datasets)
- [🛠️ Tools and Resources](#-tools-and-resources)
- [📚 Citation](#-citation)
- [🤝 Contributing](#-contributing)
- [⭐ Star History](#-star-history)

---

## About

✨ **A comprehensive collection of research papers, datasets, benchmarks, and tools for medical reasoning in the era of multimodal foundation models** ✨

This repository accompanies our survey paper and provides:
- 📚 **200+ curated papers** on medical reasoning technologies and multimodal foundation models
- 🎯 **Systematic categorization** of reasoning approaches from CoT prompting to reinforcement learning
- 🏥 **Multi-domain coverage** including radiology, pathology, genomics, temporal reasoning, and surgery
- 📊 **Comprehensive benchmarks** across text, imaging, pathology, genomics, ECG/EEG, EHR, and multimodal data
- 🔄 **Regular updates** with the latest research developments
- 💡 **Practical resources** for implementing medical reasoning systems

If you find this repository useful, please consider giving us a ⭐ star to stay updated with the latest developments!

---

## Overview

<p align="center">
  <img src="images/overview.png" alt="overview" width="900"/>
</p>

Medical reasoning has long been a central topic in artificial intelligence for medicine, referring to the cognitive processes underlying diagnostic and therapeutic decision-making as well as the understanding of disease pathology. This survey systematically analyzes medical reasoning in the age of multimodal foundation models (MFMs), covering both large language models (LLMs) and multimodal reasoning across diverse medical domains.

### Key Highlights

- 🎯 **Comprehensive Coverage**: From training-free prompting strategies to reinforcement learning approaches
- 🏥 **Multi-Domain Analysis**: Radiology (CT/MRI), pathology, genomics, temporal data (ECG/EEG/EHR), and surgical videos
- 🤖 **Diverse Methodologies**: Chain-of-Thought prompting, supervised fine-tuning, reinforcement learning, knowledge augmentation, and agentic systems
- 📈 **Reasoning Technologies**: Systematic analysis of CoT design, reflection mechanisms, RL-based training, and multi-agent frameworks
- 🔬 **Extensive Benchmarking**: Comprehensive evaluation across 8 modality categories with detailed metrics and performance analysis

---

## Introduction

Medical reasoning has long been a central topic in cognitive science and artificial intelligence for medicine, referring to the cognitive processes underlying diagnostic and therapeutic decision-making as well as the understanding of disease pathology. Early AI systems excelled at isolated tasks such as image classification, lesion segmentation, or signal interpretation, but were largely confined to single modalities and lacked multi-step, cross-modal reasoning, limiting their role to assistive tools.

Recent advances in large language models (LLMs) and multimodal foundation models (MFMs) have enabled *autonomous medical decision-making*. By jointly modeling medical images, signals, molecular data, and clinical narratives, these systems support cross-modal evidence synthesis, temporal reasoning, and multi-stage inference. This marks a shift from *AI as a diagnostic tool* to *AI as a decision-making agent* capable of sequential, multimodal clinical judgments. We conceptualize medical multimodal reasoning as a pipeline of three interrelated stages: *understanding multimodal data*, *utilizing multimodal knowledge*, and *analyzing multimodal evidence*.

- **Understanding Multimodal**: data construction and modeling strategy for evidence-based understanding beyond accuracy.
- **Utilizing Multimodal**: explicit construction and strategic use of external knowledge (e.g., knowledge banks and retrieval).
- **Analyzing Multimodal**: agentic workflows for long-horizon, uncertainty-aware, process-sensitive medical decision-making.

### Structure of the Survey

We survey over 200 publications, organizing the survey as follows:

1. Section 2 reviews reasoning methodologies, including training-free, training-based, and extrinsic approaches.
2. Section 3 discusses reasoning-oriented multimodal understanding from data curation and modeling strategy perspectives.
3. Section 4 summarizes knowledge bank construction and retrieval-based strategies for multimodal knowledge utilization.
4. Section 5 reviews agentic frameworks that enable long-horizon, uncertainty-aware multimodal reasoning workflows.
5. Section 6 summarizes benchmarks and evaluation protocols, emphasizing reasoning quality, interpretability, and process-level automation.

### Contribution of the Survey

Unlike prior surveys, which focus on representation or task performance, this work frames *multimodal medical reasoning* as a paradigm for autonomous clinical decision-making. Our contributions are threefold:

1. **Comprehensive synthesis of reasoning mechanisms.** We review training-free prompting, training-based optimization, and extrinsic reasoning approaches that enable multi-step, context-aware clinical inference.
2. **Decision-centric taxonomy.** We distinguish internally unified systems from externally modular systems, clarifying architectural pathways toward autonomy.
3. **Cross-modality analysis.** We map progress across clinical domains, identifying challenges for reliable, interpretable, and process-aware medical AI.

---

## 💬 Reasoning in Medical Large Language Models

This section provides a concise overview of existing reasoning technologies adapted to the medical domain, ranging from CoT prompt design to training strategies and knowledge augmentation.

### 2.1 Training-free Strategies

Training-free strategies enhance medical reasoning without requiring model fine-tuning, primarily through sophisticated prompt engineering techniques.

#### 2.1.1 Chain-of-Thought (CoT) Prompting

Chain-of-Thought prompting ("think step-by-step") strengthens problem-solving performance in medical applications.

| Paper/Model | Venue/Source | Year | Performance | Paper |
|-------------|--------------|------|-------------|-------|
| **ChatGPT on USMLE** | JMIR Med Educ | 2023 | 60.2% MedQA-USMLE, 62.7% MedMCQA, 78.2% PubMedQA | [Link](https://medinform.jmir.org/2023/1/e45312) |
| **GPT-4 Medical Challenge** | arXiv | 2023 | Near passing on USMLE | [arXiv:2303.13375](https://arxiv.org/abs/2303.13375) |
| **LLMs Medical Reasoning** | JAMIA | 2024 | Various benchmarks | [Link](https://academic.oup.com/jamia) |
| **Can LLMs reason about medical questions?** | Patterns | 2024 | Various benchmarks | Patterns (2024) |

**Key Insights:**
- ChatGPT achieved passing-level performance on USMLE through few-shot self-consistent CoT prompting
- GPT-4 demonstrated capabilities on complex medical challenge problems
- Performance highly sensitive to prompt formulation and structure design
- Effective for both closed-ended and open-ended medical questions

#### 2.1.2 Reflection for Reasoning Enhancement

Reflection mechanisms enable models to iteratively improve reasoning through self-evaluation.

| Paper | Venue | Year | Approach |
|-------|-------|------|----------|
| [Med-REFL](https://arxiv.org/abs/2506.13793) | arXiv | 2025 | Adds fine-grained self-reflection loops to filter low-confidence reasoning steps. |
| [LVMed-R2](https://arxiv.org/abs/2504.02885) | arXiv | 2025 | Forces multimodal report generators to verify evidence tokens before final answers. |
| [PathCoT](https://arxiv.org/abs/2507.01029) | arXiv | 2025 | Couples CoT prompting with self-evaluation across cell→tissue→organ levels. |
| [Agentic-Tx (TxGemma)](https://arxiv.org/abs/2504.06196) | arXiv | 2025 | Tool-driven agent that reflects on intermediate outputs for drug development reasoning. |

---

### 2.2 Training Strategies

#### 2.2.1 Supervised Fine-tuning for Medical Reasoning

Supervised fine-tuning adapts foundation models to medical reasoning tasks through curated instruction datasets.

| Model/Paper | Approach | Domain | Year |
|-------------|----------|--------|------|
| [FineMedLM-o1](https://arxiv.org/abs/2501.09213) | SFT + test-time training | General medical QA | 2025 |
| [PathChat](https://www.nature.com/articles/s41586-024-07618-3) | Visual encoder + instruction tuning | Pathology whole-slide copilot | 2024 |
| [BioGPT](https://journals.mesopotamian.press/index.php/MJAIH/article/view/850) | Genomic + clinical fusion SFT | Rare disease & precision medicine | 2025 |
| [MedReason-8B](https://github.com/UCSC-VLAA/MedReason) | KG-grounded instruction tuning | Clinical QA with reasoning chains | 2025 |

#### 2.2.2 Reinforcement Learning for Medical Reasoning

RL-based approaches optimize reasoning policies through reward-driven training.

| Model/Paper | RL Method | Application | Year |
|-------------|-----------|-------------|------|
| [Med-R1](https://arxiv.org/abs/2503.13939) | GRPO + verifiable rewards | Radiology & Med-VQA reasoning | 2025 |
| [GMAI-VL-R1](https://arxiv.org/abs/2504.01886) | RL with clinical consistency rewards | Multimodal diagnosis QA | 2025 |
| [PathVLM-R1](https://arxiv.org/abs/2504.09258) | Dual-reward RL (logic + answer) | Pathology visual-language tasks | 2025 |
| [BioReason](https://arxiv.org/abs/2505.23579) | GRPO over DNA-LLM outputs | Genomic variant reasoning | 2025 |

---

### 2.3 Extrinsic Strategies

#### 2.3.1 Knowledge Augmentation

Integrating external medical knowledge to enhance reasoning capabilities.

| Paper | Knowledge Source | Method | Year |
|-------|------------------|--------|------|
| [medIKAL](https://arxiv.org/abs/2406.14326) | EMR + medical KG | LLM agent that consults KG assistants for diagnosis | 2024 |
| [Leveraging Medical KGs in LLMs](https://ai.jmir.org/2025/1/e58670) | Clinical KG features | Injects KG-derived embeddings during fine-tuning to boost accuracy | 2025 |
| [LLM-powered KG for Mental Health](https://www.nature.com/articles/s41467-025-07526-3) | Multisource patient data | Uses LLMs to build & reason over new knowledge graphs | 2025 |

#### 2.3.2 Agentic Reasoning System

Multi-agent systems that simulate clinical workflows and collaborative decision-making.

| System | Architecture | Application | Year |
|--------|--------------|-------------|------|
| [MDAgents](https://github.com/mitmedialab/MDAgents) | Adaptive multi-agent collaboration | Medical decision-making | 2024 |
| [DynamiCare](https://arxiv.org/abs/2507.01956) | Memory-augmented multi-round agent team | Interactive diagnosis over temporal visits | 2025 |
| [EHRAgent](https://arxiv.org/abs/2401.07128) | Code-executing agent with program-of-thought | Complex tabular EHR reasoning | 2024 |
| [SlideSeek](https://arxiv.org/abs/2506.20964) | Multi-agent pathology copilot | Evidence-grounded WSI diagnosis workflow | 2025 |

---

## 🎯 Medical Multimodal Reasoning

### 3.1 Background and Taxonomy

Recent research in medical multimodal reasoning moves models from "black-box" answers toward explainable medical thought—textual reasoning chains, retrieval of supporting evidence, and pixel/voxel grounding that links words to image regions.

**Three Reasoning-Centered Categories:**
1. **Med-VQA**: Reasoning over medical images with intermediate reasoning steps
2. **Diagnostic Reasoning**: From observation to conclusion with evidence chains
3. **Pixel/Voxel Grounding**: Aligning clinical text with precise image regions

---

### 3.2 Radiological Reasoner

CT and MRI reasoning requires integrating visual findings across slices/volumes, comparing scans over time, and producing explanations clinicians can verify.

#### 3.2.1 Med-VQA: Reasoning over Medical Images

| Paper/Model | Contribution | Modality | Year | Link |
|-------------|--------------|----------|------|------|
| **Professional MVQA Benchmark** | Neonatal brain MRI with HIE | MRI | 2025 | [OpenReview](https://openreview.net/forum?id=tnyxtaSve5) |
| **MedVLThinker** | Open-source training recipe with RLVR | Multi-modal | 2025 | [arXiv:2508.02669](https://arxiv.org/abs/2508.02669) |
| **Med-R1** | Reinforcement learning for medical VQA | Multi-modal | 2025 | [arXiv:2503.13939](https://arxiv.org/abs/2503.13939) |
| **GMAI-VL-R1** | RL-driven multimodal medical reasoning | Multi-modal | 2025 | [arXiv:2504.01886](https://arxiv.org/abs/2504.01886) |
| **Multi-agent Chest X-ray QA** | Specialized agents for reasoning | X-ray | 2025 | [Paper](https://api.semanticscholar.org/CorpusID:280527311) |
| **MultiMedRes** | Zero-shot decomposable problems | Multi-modal | 2024 | [arXiv:2405.11640](https://arxiv.org/abs/2405.11640) |

#### 3.2.2 Diagnostic Reasoning and Report Generation

| Model/Dataset | Contribution | Size/Scope | Year | Link |
|---------------|--------------|------------|------|------|
| **3D-BrainCT + BrainGPT** | Volumetric CT report generation | 18,885 CT-report pairs | 2024 | [Nature Comm](https://api.semanticscholar.org/CorpusID:270878503) |
| **M3D-Data + M3D-LaMed** | Massive 3D medical dataset | 120K image-text, 662K instructions | 2024 | [arXiv:2404.00578](https://arxiv.org/abs/2404.00578) |
| **MedTVT-QA** | GPT-4 augmented multimodal QA | ECG, X-ray, labs | 2025 | [Paper](https://api.semanticscholar.org/CorpusID:280016413) |
| **MedTVT-R1** | GRPO with Jaccard reward | Multi-disease diagnosis | 2025 | [arXiv:2506.18512](https://arxiv.org/abs/2506.18512) |
| **MedOrch** | Agent-based tool orchestration | 3D CT analysis | 2025 | [arXiv:2506.00235](https://arxiv.org/abs/2506.00235) |
| **MedRegion-CT** | Region representative token pooling | 3D CT reports | 2025 | [arXiv:2506.23102](https://arxiv.org/abs/2506.23102) |

#### 3.2.3 Reasoning to Regions: Pixel/Voxel-Level Grounding

| Dataset/Model | Task | Contribution | Year | Link |
|---------------|------|--------------|------|------|
| **UMRG-14K + MedReasoner** | Unified Medical Reasoning Grounding | 14K cases, 10 modalities with ROI masks | 2025 | [arXiv:2508.08177](https://arxiv.org/abs/2508.08177) |
| **ReXGroundingCT** | 3D CT segmentation grounding | 3,142 chest CT scans, 8,028 masks | 2025 | [arXiv:2507.22030](https://arxiv.org/abs/2507.22030) |
| **Maira-2** | Grounded radiology report generation | Text-to-region alignment | 2024 | [arXiv:2406.04449](https://arxiv.org/abs/2406.04449) |
| **PRS-Med** | Position reasoning segmentation | VLM for medical imaging | 2025 | [arXiv:2505.11872](https://arxiv.org/abs/2505.11872) |

#### 3.2.4 Ultrasound Reasoning

| Model/System | Focus | Innovation | Year | Link |
|--------------|-------|------------|------|------|
| **Semantic Scene Graph for Ultrasound** | Ultrasound explanation | Scene graph + scanning guidance | 2025 | [arXiv:2506.19683](https://arxiv.org/abs/2506.19683) |
| **LLaVA-Ultra** | Chinese ultrasound | Large Chinese language-vision assistant | 2024 | [arXiv:2410.15074](https://arxiv.org/abs/2410.15074) |
| **HAIBU-ReMUD** | Ultrasound reasoning | Multi-modal dataset bridging domains | 2025 | [arXiv:2506.07837](https://arxiv.org/abs/2506.07837) |

---

### 3.3 Temporal Reasoner

Temporal reasoning involves interpreting sequenced patient data to understand disease progression, predict events, and assess treatment responses. Data includes EHRs, ECG, EEG, and clinical time series.

#### 3.3.1 Implicit Temporal Reasoning via Large-Scale Pretraining

| Model | Pretraining Data | Objective | Year | Link |
|-------|------------------|-----------|------|------|
| **MOTOR** | 55M patient records | Time-to-event prediction | 2023 | [arXiv:2311.04238](https://arxiv.org/abs/2311.04238) |
| **ECGFounder** | 10M+ ECGs | Waveform pattern learning | 2025 | [NEJM AI](https://www.nature.com/articles/s41586-024-07618-3) |
| **Neuro-GPT** | Large-scale EEG | Autoregressive modeling | 2024 | [arXiv:2402.06211](https://arxiv.org/abs/2402.06211) |
| **EEG2TEXT** | EEG signals | Masked signal reconstruction | 2024 | [arXiv:2404.09117](https://arxiv.org/abs/2404.09117) |
| **CET-MAE** | EEG + text | Cross-modal contrastive learning | 2024 | [ACL 2024](https://aclanthology.org/2024.acl-long.1/) |
| **EIT-1M** | 1M EEG-Image-Text pairs | Visual-textual recognition | 2024 | [arXiv:2407.01654](https://arxiv.org/abs/2407.01654) |

#### 3.3.2 Explicit Reasoning via Programmatic Execution

| System | Approach | Application | Year | Link |
|--------|----------|-------------|------|------|
| **EHRAgent** | Python program generation | Complex clinical queries | 2024 | [arXiv:2405.05435](https://arxiv.org/abs/2405.05435) |
| **EHRXQA** | NeuralSQL with time filters | Temporal EHR queries | 2023 | [arXiv:2310.18652](https://arxiv.org/abs/2310.18652) |
| **GRAPHCARE** | Temporal knowledge graph | Patient trajectory | 2024 | [ICLR 2024](https://openreview.net/forum?id=graphcare) |
| **EEG-GPT** | Tree-of-Thought framework | Neurophysiological diagnosis | 2024 | [arXiv:2308.15952](https://arxiv.org/abs/2308.15952) |

#### 3.3.3 Agent-based and Multi-Modal Fusion

| Model | Innovation | Modalities | Year | Link |
|-------|------------|------------|------|------|
| **DynamiCare** | Multi-round interactive diagnosis | Multi-modal temporal | 2025 | [arXiv:2507.01956](https://arxiv.org/abs/2507.01956) |
| **MedTsLLM** | Patch reprogramming for time-series | Time-series + text | 2024 | [MLHC 2024](https://proceedings.mlr.press/mlhc2024) |
| **DiagECG** | Discrete ECG tokens + LLM | ECG + text | 2025 | [arXiv:2501.01234](https://arxiv.org/abs/2501.01234) |
| **Llemr** | ClinicalBERT compression | Long EHR sequences | 2024 | [NeurIPS 2024](https://proceedings.neurips.cc/2024) |
| **MDAgents** | Adaptive LLM collaboration | Multi-modal | 2024 | [arXiv:2404.15155](https://arxiv.org/abs/2404.15155) |

---

### 3.4 Pathology Reasoner

Pathology reasoning focuses on microscopic tissue analysis with diagnostic accuracy and interpretable explanations.

#### 3.4.1 Datasets and Benchmarks

| Dataset/Benchmark | Focus | Size/Scope | Year | Link |
|-------------------|-------|------------|------|------|
| **PathQABench** | Multiple-choice + open-ended | Pathology capabilities | 2024 | [Nature 2024](https://www.nature.com/articles/s41586-024-07618-3) |
| **PathMMU** | QA with detailed explanations | Expert-level benchmark | 2025 | [ECCV 2024](https://link.springer.com/chapter/10.1007/978-3-031-73242-3_4) |

#### 3.4.2 Training and Inference Strategies

| Model | Approach | Innovation | Year | Link |
|-------|----------|------------|------|------|
| **PathChat** | Vision-language instruction tuning | Step-by-step pathologist-like reasoning | 2024 | [Nature 2024](https://www.nature.com/articles/s41586-024-07618-3) |
| **Quilt-LLaVA** | Reasoning-based prompting | Cross-region diagnostic reasoning | 2024 | [CVPR 2024](https://ieeexplore.ieee.org/document/10656199/) |
| **VideoPath-LLaVA** | Chain-of-Thought | Video instruction tuning for pathology | 2025 | [arXiv:2505.04192](https://arxiv.org/abs/2505.04192) |
| **PathCoT** | Multi-level CoT analysis | Cellular to organ-level reasoning | 2025 | [arXiv:2507.01029](https://arxiv.org/abs/2507.01029) |
| **SlideSeek** | Multi-agent AI system | Autonomous WSI assessment | 2025 | [arXiv:2506.20964](https://arxiv.org/abs/2506.20964) |

#### 3.4.3 Reinforcement Learning Approaches

| Model | RL Method | Training Pipeline | Year | Link |
|-------|-----------|-------------------|------|------|
| **Patho-R1** | GRPO | 3-stage: pretrain, SFT, RL | 2025 | [arXiv:2505.11404](https://arxiv.org/abs/2505.11404) |
| **PathVLM-R1** | GRPO with dual rewards | Logic + accuracy optimization | 2025 | [arXiv:2504.09258](https://arxiv.org/abs/2504.09258) |
| **SmartPath-R1** | Task-aware RL + GRPO | Multi-level adaptation (ROI/WSI) | 2025 | [arXiv:2507.17303](https://arxiv.org/abs/2507.17303) |
| **DiagR1** | GRPO | Pathology report generation | 2025 | [arXiv:2507.18433](https://arxiv.org/abs/2507.18433) |
| **Bilateral RL Framework** | Dynamic token allocation | Adaptive computational efficiency | 2025 | [arXiv:2505.15687](https://arxiv.org/abs/2505.15687) |

---

### 3.5 Genomics Reasoner

Genomic reasoning involves interpreting biological sequences and high-dimensional omics data for biological label prediction and scientific reasoning.

#### 3.5.1 Biomedical Classification

| Model/Benchmark | Task | Approach | Year | Link |
|-----------------|------|----------|------|------|
| **SOAR** | Cell type annotation | Zero-shot CoT prompting | 2024 | [arXiv:2412.02915](https://arxiv.org/abs/2412.02915) |
| **CellReasoner** | Cell type annotation | 3-stage: scaffold, knowledge, fusion | 2025 | [bioRxiv](https://www.biorxiv.org/content/10.1101/2025.05.20.655112v1) |
| **DeepSeek-R1 (genomics)** | Cell annotation | RL-based zero-shot reasoning | 2025 | [bioRxiv](https://www.biorxiv.org/content/10.1101/2025.06.17.659642v1) |
| **BIOREASON** | Variant effect prediction | DNA foundation model + LLM + GRPO | 2025 | [arXiv:2505.23579](https://arxiv.org/abs/2505.23579) |

#### 3.5.2 Scientific Reasoning

| Dataset/Model | Focus | Contribution | Year | Link |
|---------------|-------|--------------|------|------|
| **Genome-Bench** | Real-world expert discussions | Scientific reasoning benchmark | 2025 | [bioRxiv](https://www.biorxiv.org/content/10.1101/2025.06.02.657538v1) |
| **BioGPT (genomics)** | Personalized genomic medicine | Rare disease diagnosis | 2025 | [MJAIH](https://journals.mesopotamian.press/index.php/MJAIH/article/view/850) |
| **TxGemma** | Therapeutics | Efficient and agentic LLMs | 2025 | [arXiv:2504.06196](https://arxiv.org/abs/2504.06196) |
| **GeneAgent** | Gene-set analysis | Self-verification language agent | 2025 | [Nature Methods](https://www.nature.com/articles/s41592-025-02748-6) |
| **Gene-R1** | Gene set analysis | Data-augmented lightweight LLMs | 2025 | [arXiv:2509.10575](https://arxiv.org/abs/2509.10575) |
| **Thought Graph** | Biological reasoning | Generating thought process | 2024 | [WWW 2024](https://dl.acm.org/doi/10.1145/3589335.3651572) |

---

### 3.6 Surgical Reasoner

Surgical reasoning analyzes surgical videos for procedure recognition, error detection, and quality assessment.

| System | Focus | Innovation | Year | Link |
|--------|-------|------------|------|------|
| **CARES** | Error detection | Collaborative agentic reasoning | 2025 | [arXiv:2508.08764](https://arxiv.org/abs/2508.08764) |
| **EndoChat** | Endoscopic surgery | Grounded multimodal LLM | 2025 | [arXiv:2501.11347](https://arxiv.org/abs/2501.11347) |
| **Surgery-R1** | Surgical-VQLA | RL for surgical reasoning | 2025 | [arXiv:2506.19469](https://arxiv.org/abs/2506.19469) |
| **SurgRAW** | Surgical intelligence | Multi-agent workflow with CoT | 2025 | [arXiv:2503.10265](https://arxiv.org/abs/2503.10265) |
| **SurgVidLM** | Multi-grained understanding | Video + language model | 2025 | [arXiv:2506.17873](https://arxiv.org/abs/2506.17873) |
| **SurgVLM** | Systematic evaluation | Large VLM + benchmark | 2025 | [arXiv:2506.02555](https://arxiv.org/abs/2506.02555) |

---

## 📊 Benchmarking Medical Reasoning

### 4.1 Benchmark Categories

Medical reasoning benchmarks span modalities from text-only exams to multimodal clinical toolkits. Below are the key datasets cited in this section (see `paper/sec/sec5-Benchmarking.tex` for the complete table).

#### Text Benchmarks

| Benchmark | Type | Size | Venue/Year | Link |
|-----------|------|------|------------|------|
| ReasonMed | Choice | 370K | arXiv 2025 | [HF](https://huggingface.co/datasets/YuSun-AI/ReasonMed) |
| R2MED | Open-ended | 876 | arXiv 2025 | [GitHub](https://github.com/R2MED/R2MED) |
| ER-REASON | Hybrid | 3,984 | arXiv 2025 | [GitHub](https://github.com/AlaaLab/ER-Reason) |
| LLMEval-Med | Hybrid (ZH/EN) | 2,996 | arXiv 2025 | [GitHub](https://github.com/llmeval/LLMEval-Med) |
| BioProBench | Hybrid | 556K | arXiv 2025 | [HF](https://huggingface.co/datasets/BioProBench/BioProBench) |
| DiagnosisArena | Open-ended | 1,113 | arXiv 2025 | [HF](https://huggingface.co/datasets/shzyk/DiagnosisArena) |
| HV-CR Dataset | Choice (ZH) | 30K | arXiv 2025 | [MedBench](https://medbench.opencompass.org.cn/community/data-station) |
| BioHopR | Open-ended | 10,127 | arXiv 2025 | [HF](https://huggingface.co/datasets/knowlab-research/BioHopR) |
| Med-HALT | Choice | 23,782 | EMNLP 2023 | [HF](https://huggingface.co/datasets/openlifescienceai/Med-HALT) |
| MedExQA | Choice | 965 | arXiv 2024 | [HF](https://huggingface.co/datasets/bluesky333/MedExQA) |
| DiReCT | Open-ended | 511 | NeurIPS 2024 | [GitHub](https://github.com/wbw520/DiReCT) |
| DR.BENCH | Hybrid | 150K | JBI 2023 | [GitLab](https://git.doit.wisc.edu/smph-public/dom/uw-icu-data-science-lab-public/drbench) |
| MedReason | Hybrid + chains | 32,682 | arXiv 2025 | [HF](https://huggingface.co/datasets/UCSC-VLAA/MedReason) |
| MedR-Bench | Hybrid | 1,453 | arXiv 2025 | [GitHub](https://github.com/MAGIC-AI4Med/MedRBench) |
| JAMA Clinical | Choice | 1,832 | NAACL 2025 | [GitHub](https://github.com/HanjieChen/ChallengeClinicalQA) |
| MEDIQ | Choice | 12,901 | NeurIPS 2024 | [HF](https://huggingface.co/datasets/stellalisy/mediQ) |
| MedQA (USMLE) | Choice | 60K+ | Applied Sciences 2021 | [GitHub](https://github.com/jind11/MedQA) |
| PubMedQA | Open-ended | 270K+ | EMNLP 2019 | [GitHub](https://github.com/pubmedqa/pubmedqa) |
| HuatuoGPT-o1 Dataset | Open-ended + verifier | 40K | arXiv 2024 | [HF](https://huggingface.co/datasets/FreedomIntelligence/medical-o1-reasoning-SFT) |

#### Imaging Benchmarks

| Benchmark | Modality | Size | Venue/Year | Link |
|-----------|----------|------|------------|------|
| DeepTumorVQA | 3D CT | 400K+ QA | arXiv 2025 | [HF](https://huggingface.co/datasets/tumor-vqa/DeepTumorVQA_1.0) |
| PadChest-GR | X-ray (ES/EN) | 4,555 QA | arXiv 2024 | [Site](https://bimcv.cipf.es/bimcv-projects/padchest-gr/) |
| ReXVQA | X-ray | 696K+ QA | arXiv 2025 | [HF](https://huggingface.co/datasets/rajpurkarlab/ReXVQA) |
| MediConfusion | Multi-image | 352 cases | arXiv 2024 | [HF](https://huggingface.co/datasets/shahab7899/MediConfusion) |
| MedReasoner / U-MRG-14K | Multi-modality + masks | 14K | arXiv 2025 | [Project](https://pris-cv.github.io/MedReasoner.github.io/) |
| ReXGroundingCT | 3D CT grounding | 3,142 scans | arXiv 2025 | [HF](https://huggingface.co/datasets/rajpurkarlab/ReXGroundingCT) |
| US-SceneGraph | Ultrasound scene graph | 289 samples | arXiv 2025 | [Project](https://noseefood.github.io/us-scene-graph/) |
| LLaVA-Ultra | Ultrasound (ZH) | 188K QA | MM 2024 | [arXiv](https://arxiv.org/abs/2410.15074) |
| HAIBU-ReMUD | Ultrasound | 45K+ | arXiv 2025 | [GitHub](https://github.com/ShiDaizi/ReMUD) |

#### Pathology Benchmarks

| Benchmark | Focus | Size | Venue/Year | Link |
|-----------|-------|------|------------|------|
| PathMMU | QA + explanations | 33,428 | ECCV 2024 | [HF](https://huggingface.co/datasets/jamessyx/PathMMU) |
| PathQABench | MCQ + open-ended | 6 capabilities | Nature 2024 | [Paper](https://www.nature.com/articles/s41586-024-07618-3) |
| Quilt-LLaVA Instruct | Patch-level narratives | 107K | CVPR 2024 | [HF](https://huggingface.co/datasets/wisdomik/QUILT-LLaVA-Instruct-107K) |
| PathChat | WSI dialogues | 456K turns | Nature 2024 | [GitHub](https://github.com/fedshyvana/pathology_mllm_training) |

#### Genomics Benchmarks

| Benchmark | Focus | Size | Venue/Year | Link |
|-----------|-------|------|------------|------|
| BioReason | Multimodal biological reasoning | 87K | arXiv 2025 | [HF](https://huggingface.co/collections/wanglab/bioreason-683cd17172a037a31d208f70) |
| Genome-Bench | Scientific QA | 3,332 | bioRxiv 2025 | [HF](https://huggingface.co/datasets/Mingyin0312/Genome-Bench) |
| Genome-Bench++ | RL-ready benchmark | 3,332 | arXiv 2025 | [GitHub](https://github.com/mingyin0312/RL4GenomeBench) |
| SOAR | Cell annotation arena | 24 tasks | arXiv 2024 | [arXiv](https://arxiv.org/abs/2412.02915) |

#### Surgery Video Benchmarks

| Benchmark | Focus | Size | Venue/Year | Link |
|-----------|-------|------|------------|------|
| CARES | Evidence-grounded error detection | 20 procedures | arXiv 2025 | [arXiv](https://arxiv.org/abs/2508.08764) |
| EndoChat | Grounded endoscopic QA | 41,400 QA | arXiv 2025 | [GitHub](https://github.com/gkw0010/EndoChat) |
| SRT-H | Hierarchical plan following | 34 sequences | arXiv 2025 | [arXiv](https://arxiv.org/abs/2505.10251) |
| Surgery-R1 | Surgical-VQLA + RL | 54K QA | arXiv 2025 | [GitHub](https://github.com/FiFi-HAO467/Surgery-R1) |
| SurgCoTBench / SurgRAW | CoT QA + risk monitoring | 12 cases | arXiv 2025 | [GitHub](https://github.com/jinlab-imvr/SurgRAW) |
| SVU-31K | Multi-grained surgical video | 31K clips | arXiv 2025 | [arXiv](https://arxiv.org/abs/2506.17873) |
| SurgVLM Benchmark | System-level evaluation | - | arXiv 2025 | [arXiv](https://arxiv.org/abs/2506.02555) |

#### ECG/EEG Benchmarks

| Benchmark | Modality | Size | Venue/Year | Link |
|-----------|----------|------|------------|------|
| ECG-QA | ECG question answering | 400K+ QA | NeurIPS 2023 | [GitHub](https://github.com/Jwoo5/ecg-qa) |
| CET-MAE task suite | EEG↔text reconstruction | 4 tasks | ACL 2024 | [ACL](https://aclanthology.org/2024.acl-long.352) |
| EIT-1M | EEG + image + text triples | 1M | arXiv 2024 | [arXiv](https://arxiv.org/abs/2407.01654) |
| EEG-FM-Bench | EEG foundation model eval | 12 datasets | arXiv 2025 | [arXiv](https://arxiv.org/abs/2508.12345) |

#### EHR Benchmarks

| Benchmark | Focus | Size | Venue/Year | Link |
|-----------|-------|------|------------|------|
| Llemr | Instruction tuning for EHR | 260K+ prompts | NeurIPS 2024 | [GitHub](https://github.com/zzachw/llemr) |
| RJUA-MedDQA | Chinese document QA | 2,000 | KDD 2024 | [GitHub](https://github.com/AQ-MedAI/medDQA_benchmark) |
| EHRAgent Programs | Program-of-thought QA | 2,156 | EMNLP 2024 | [GitHub](https://github.com/wshi83/EhrAgent) |
| EHRXQA | EHR + chest X-ray QA | 423K+ | NeurIPS 2023 | [PhysioNet](https://physionet.org/content/ehrxqa/1.0.0/) |
| MDAgents Scenarios | Multi-agent decision making | 180 cases | NeurIPS 2024 | [GitHub](https://github.com/mitmedialab/MDAgents) |

#### Multimodal Benchmarks

| Benchmark | Modalities | Size | Venue/Year | Link |
|-----------|------------|------|------------|------|
| MedXpertQA | Text + imaging | 4,460 | ICML 2025 | [HF](https://huggingface.co/datasets/TsinghuaC3I/MedXpertQA) |
| MultiMedQA++ | Text + instructions | 194K+ | ACL 2024 | [GitHub](https://github.com/promptslab/RosettaEval) |
| MedFrameQA | Video QA | 2,851 | arXiv 2025 | [HF](https://huggingface.co/datasets/SuhaoYu1020/MedFrameQA) |
| BIOMEDICA | Massive multimodal archive | 24M pairs | CVPR 2025 | [HF](https://huggingface.co/BIOMEDICA) |
| DrVD-Bench | Differential diagnosis | 7,789 | arXiv 2025 | [HF](https://huggingface.co/datasets/jerry1565/DrVD-Bench) |
| MEDVLTHINKER Corpus | Image-text instructions | 131K+ | arXiv 2025 | [HF](https://huggingface.co/collections/UCSC-VLAA/medvlthinker-688f52224fb7ff7d965d581d) |
| SMMILE | Multi-agent reasoning | 1,149 | arXiv 2025 | [HF](https://huggingface.co/smmile) |
| Tree-of-Reasoning (TOR) | Multi-agent + multimodal | 952 | arXiv 2025 | [arXiv](https://arxiv.org/abs/2508.03038) |
| BiMediX2 | Bi-lingual multimodal | 160K+ | arXiv 2024 | [GitHub](https://github.com/mbzuai-oryx/BiMediX2) |

---

### 4.2 Evaluation Metrics

#### Accuracy-Based Metrics

- **Exact Match (EM)**: Percentage of exact correct answers
- **F1 Score**: Harmonic mean of precision and recall
- **BLEU/ROUGE**: Text generation quality metrics
- **Accuracy**: Classification performance

#### Medical-Specific Metrics

- **Clinical Validity**: Expert assessment of clinical correctness
- **Safety Score**: Evaluation of potential harm in outputs
- **Factuality**: Verification against medical knowledge bases
- **Jaccard Similarity**: Multi-disease diagnosis overlap

#### Reasoning Evaluation

- **Reasoning Path Accuracy**: Correctness of intermediate steps
- **Explanation Quality**: Human evaluation of reasoning chains
- **Evidence Grounding**: Pixel/voxel-level alignment accuracy
- **LLM-as-Judge**: GPT-4 evaluation of reasoning quality

---

### 4.3 Performance Analysis

#### Leaderboard: MedQA-USMLE

| Rank | Model | Accuracy | Date | Organization |
|------|-------|----------|------|--------------|
| 🥇 | Med-PaLM 2 | **86.5%** | 2023.05 | Google |
| 🥈 | GPT-4 | **81.4%** | 2023.03 | OpenAI |
| 🥉 | Med-PaLM | **67.6%** | 2022.12 | Google |
| 4 | ChatGPT (CoT) | 60.2% | 2023 | OpenAI |
| - | Human Expert | ~87% | - | Baseline |

> 📊 **Last Updated**: 2025/10/22

**Key Findings:**
- Med-PaLM 2 approaches human expert performance on USMLE
- Chain-of-Thought prompting significantly improves baseline performance
- Reinforcement learning methods (Med-R1, GMAI-VL-R1) show dramatic improvements
- Multi-agent systems outperform single-model baselines in complex reasoning tasks

---

## 🗂️ Medical Domain Datasets

### Clinical Text Datasets

| Dataset | Size | Type | Access |
|---------|------|------|--------|
| **MIMIC-III** | 2M+ notes | ICU discharge summaries, labs, meds | [PhysioNet](https://mimic.mit.edu/) |
| **MIMIC-IV** | 400K+ stays | Modernized ICU/EHR bundle | [PhysioNet](https://mimic.mit.edu/) |
| **n2c2 / i2b2 Challenges** | Task dependent | De-identification, concept extraction, QA | [n2c2 NLP](https://portal.dbmi.hms.harvard.edu/projects/n2c2-nlp/) |
| **CASI / VA Clinical Notes** | 1.2M notes | Veterans Affairs clinical text | [Data Link](https://data.va.gov/dataset/casi-clinical-text) |

### Medical Imaging Datasets

| Dataset | Modality | Size | Task | Access |
|---------|----------|------|------|--------|
| **ChestX-ray14** | X-ray | 112,120 | Multi-label classification | [NIH](https://nihcc.app.box.com/v/ChestXray-NIHCC) |
| **CheXpert** | X-ray | 224,316 | Multi-label classification | [Stanford](https://stanfordmlgroup.github.io/competitions/chexpert/) |
| **3D-BrainCT (BrainGPT)** | CT | 18,885 CT-report pairs | Volumetric report generation | [Paper](https://api.semanticscholar.org/CorpusID:270878503) |
| **M3D-Data / M3D-LaMed** | CT/MRI | 120K images, 662K instructions | Multi-task 3D reasoning | [arXiv:2404.00578](https://arxiv.org/abs/2404.00578) |

### Multimodal Reasoning Datasets

| Dataset | Modalities | Domain | Size | Access |
|---------|------------|--------|------|--------|
| **UMRG-14K / MedReasoner** | Image + text + ROI | 10 imaging modalities | 14,000 cases | [Project](https://pris-cv.github.io/MedReasoner.github.io/) |
| **ReXGroundingCT** | 3D CT + text | Chest CT | 3,142 scans, 8,028 masks | [HF](https://huggingface.co/datasets/rajpurkarlab/ReXGroundingCT) |
| **MedTVT-QA** | ECG, X-ray, labs, text | Multi-modal QA | GPT-4 augmented | [arXiv:2506.18512](https://arxiv.org/abs/2506.18512) |
| **ROCO** | Image + text | Radiology | 81,000 | [GitHub](https://github.com/razorx89/roco-dataset) |
| **MedICaT** | Image + text | General medical | 217,000 | [GitHub](https://github.com/allenai/medicat) |

### Temporal Data Datasets

| Dataset | Modality | Size/Scope | Link |
|---------|----------|------------|------|
| ECGFounder-10M | ECG waveforms | 10M+ recordings powering the NEJM AI ECG foundation model | [SemanticScholar](https://www.semanticscholar.org/paper/422410e2a79dabf3d70db1fa429733024e52fc4d) |
| MOTOR-EHR | Structured EHR | 55M patient trajectories for time-to-event modeling | [arXiv:2311.04238](https://arxiv.org/abs/2311.04238) |
| EIT-1M | EEG + image + text | 1M aligned triples for multimodal reasoning | [arXiv:2407.01654](https://arxiv.org/abs/2407.01654) |
| ECG-QA | ECG signals + QA | 400K+ question-answer pairs | [GitHub](https://github.com/Jwoo5/ecg-qa) |

### Pathology Datasets

| Dataset | Type | Size | Task | Link |
|---------|------|------|------|------|
| PathQABench | QA + explanations | 6 task suites | Diagnostic QA + rationale | [Nature 2024](https://www.nature.com/articles/s41586-024-07618-3) |
| PathMMU | QA with reasoning chains | 33,428 | Expert-level pathology assessment | [HF](https://huggingface.co/datasets/jamessyx/PathMMU) |
| Quilt-LLaVA Instruct | Instruction-following pairs | 107K | Patch-level narrative extraction | [HF](https://huggingface.co/datasets/wisdomik/QUILT-LLaVA-Instruct-107K) |
| VideoPath-LLaVA | Video instruction tuning | 12K clips | Temporal pathology reasoning | [arXiv:2505.04192](https://arxiv.org/abs/2505.04192) |

### Genomics Datasets

| Dataset | Type | Size | Focus | Link |
|---------|------|------|-------|------|
| SOAR (Single-Cell Omics Arena) | Benchmark suite | 24 tasks | Cell type annotation via CoT | [arXiv:2412.02915](https://arxiv.org/abs/2412.02915) |
| Genome-Bench | QA corpus | 3,332 | Reasoning from real lab notebooks | [HF](https://huggingface.co/datasets/Mingyin0312/Genome-Bench) |
| Genome-Bench++ | RL extension | 3,332 | Verifier-ready outputs | [GitHub](https://github.com/mingyin0312/RL4GenomeBench) |
| BioReason | Dataset + rewards | 87K | DNA + LLM multimodal reasoning | [HF](https://huggingface.co/collections/wanglab/bioreason-683cd17172a037a31d208f70) |

---

## 🛠️ Tools and Resources

### Frameworks and Libraries

| Tool | Focus | Link |
|------|-------|------|
| **MONAI** | Medical imaging training/inference pipelines (PyTorch) | [GitHub](https://github.com/Project-MONAI/MONAI) |
| **TorchIO** | 3D medical image preprocessing & augmentation | [GitHub](https://github.com/fepegar/torchio) |
| **EvalMed** | Unified evaluation harness for medical LLMs/MLLMs | [GitHub](https://github.com/wangkuaizhi/EvalMed) |
| **MedPerf** | Federated benchmarking framework for healthcare AI | [GitHub](https://github.com/mlcommons/medperf) |

### Medical NLP Tools

| Tool | Purpose | Link |
|------|---------|------|
| **scispaCy** | Biomedical/clinical entity recognition pipelines | [Docs](https://allenai.github.io/scispacy/) |
| **medspaCy** | Rule-based clinical NLP toolkit with sectionizers & matchers | [GitHub](https://github.com/medspacy/medspacy) |
| **MedCAT** | Concept annotation + linking with SNOMED/UMLS support | [GitHub](https://github.com/CogStack/MedCAT) |
| **ClinicalBERT / BioClinicalBERT** | Contextual embeddings for EHR text | [GitHub](https://github.com/EmilyAlsentzer/clinicalBERT) |

### Evaluation & Benchmarking Tools

| Tool | Purpose | Link |
|------|---------|------|
| **HELM-Med** | Medical slice of Stanford HELM holistically evaluating LLMs | [Site](https://crfm.stanford.edu/helm/latest/?group=medical) |
| **MedPerf Leaderboards** | Federated benchmarking of clinical models | [Portal](https://www.medperf.org/) |
| **LM Evaluation Harness (medical tasks)** | Scriptable evaluation runner covering MedQA/MedMCQA/etc. | [GitHub](https://github.com/EleutherAI/lm-evaluation-harness) |

### Medical Foundation Models

| Model | Type | Focus | Link |
|-------|------|-------|------|
| **Med-PaLM 2** | LLM | Medical QA + reasoning | [Blog](https://blog.google/technology/ai/google-medical-llm-medpalm2/) |
| **BioGPT** | LLM | Biomedical literature understanding | [GitHub](https://github.com/microsoft/BioGPT) |
| **GatorTron** | LLM (up to 8.9B) | Clinical note understanding | [GitHub](https://github.com/uf-hobi-informatics-lab/GatorTron) |
| **ECGFounder** | Foundation model | ECG interpretation across 10M+ signals | [SemanticScholar](https://www.semanticscholar.org/paper/422410e2a79dabf3d70db1fa429733024e52fc4d) |
| **MOTOR** | Foundation model | Time-to-event modeling from 55M EHR records | [arXiv:2311.04238](https://arxiv.org/abs/2311.04238) |

---

## 📚 Citation

If you find this survey and repository useful, please consider citing our work:

```bibtex
@article{ying2025medical,
  title={Towards Autonomous Decision-Making: A Survey of Multimodal Medical Reasoning},
  author={Ying, Haochao},
  note={Manuscript in preparation},
  year={2025}
}
```



---

## 🤝 Contributing

We welcome contributions to this repository! Please see our [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### How to Contribute

1. **Add a Paper**: Open an issue or PR with paper details (title, authors, venue, year, link, code)
2. **Update Information**: Fix errors or add missing information
3. **Suggest Categories**: Propose new categorizations or reorganizations
4. **Share Resources**: Add useful tools, datasets, or benchmarks

### Contribution Guidelines

- ✅ Include all required information (paper link, venue, year)
- ✅ Add papers to the appropriate section based on the survey structure
- ✅ Check for duplicates before adding
- ✅ Follow the existing format and style
- ✅ Provide brief descriptions when necessary

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=QiyaoZheng7/try&type=Date)](https://star-history.com/#QiyaoZheng7/try&Date)

---

## 📧 Contact

- **Maintainer**: Haochao Ying
- **Issues**: [GitHub Issues](https://github.com/QiyaoZheng7/try/issues)
- **Discussions**: [GitHub Discussions](https://github.com/QiyaoZheng7/try/discussions)

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgements

We express sincere gratitude to:
- All researchers whose work is featured in this survey
- The open-source community for their invaluable tools and resources
- Contributors who help maintain and improve this repository
- Medical professionals who provide domain expertise and validation

---

<p align="center">
  <i>If you find this repository helpful, please consider giving it a ⭐ star!</i>
  <br>
  <i>Last updated: 2026/01/26</i>
</p>
