---
layout: post
section-type: post
title: "SpineGPT: Self-supervised learning of human spinal cord anatomy — ESMRMB 2025"
category: Research
tags: ['neuroimaging', 'conference']
---

I am glad to share our abstract presented at the [ESMRMB Congress 2025](https://www.esmrmb.org/congress/past-meetings/congress-2025/) (Marseille, 8–11 October 2025), published in the Book of Abstracts ([doi:10.1007/s10334-025-01278-8](https://doi.org/10.1007/s10334-025-01278-8), Abstract 276):

**Self-supervised learning of human spinal cord anatomy for therapeutic optimization after neurological deficit — SpineGPT**

**Sergio Daniel Hernandez-Charpak**\*, Icare Sakr\*, Léon Muller, Juliette Hars, Jonas Blanc, Bilel El-Ghallali, Philippe Forero, Jean-Baptiste Ledoux, Fabio Becce, Jocelyne Bloch#, Grégoire Courtine#, Henri Lorach#

\* Contributed equally &nbsp;·&nbsp; # Contributed equally

*Defitech Center for Interventional Neurotherapies (.NeuroRestore), EPFL / CHUV / UNIL — Lausanne, Switzerland*

---

### Introduction

Personalized spinal cord models are essential for enhancing the effectiveness of epidural electrical stimulation (EES) therapies in individuals with spinal cord injury (SCI), Parkinson's Disease (PD), and Multiple System Atrophy (MSA). Built from patient-specific MRI and CT data, these models play a critical role in both the pre-operative planning and post-operative fine-tuning of multielectrode EES implant placements. However, the meticulous processing and annotation of medical imaging required to create these models is labor-intensive — anatomical tissue segmentation remains a bottleneck for scalability and widespread clinical adoption.

Artificial neural networks (ANNs) hold promise for automating tissue segmentation, but face significant challenges from limited labeled medical data, patient variability, and heterogeneity across imaging protocols, anatomical regions, and scanner types.

Self-supervised learning (SSL) has emerged as a powerful approach for learning meaningful data representations without human supervision, leveraging large quantities of unlabeled data. SSL has fueled the success of NLP models like GPT, which learn language structure by predicting masked words from their context. Taking direct inspiration from this, we developed **SpineGPT** — a foundation model for spinal cord MRI that learns by reconstructing masked regions of 3D volumes, capturing the spinal cord's underlying structure and variability. We then fine-tune SpineGPT for clinically relevant downstream tasks such as tissue segmentation.

### Methods

SpineGPT is built on a **masked auto-encoder (MAE)** framework. During pretraining, a 3D chunk of an MRI volume is largely masked (80%) at random and fed to an autoencoder, which is trained to reconstruct the missing portions from the visible parts (Figure 1). Through this self-reconstruction objective, the encoder learns latent representations that capture essential structural details of the spinal cord.

The encoder and decoder consist of standard Vision Transformer (ViT) layers adapted for 3D volumes. Pretraining leverages all available unlabeled data — over **1,300 diverse T2-weighted MRI volumes** of the spine, drawn from both publicly available and private datasets.

![Figure 1 — SpineGPT self-supervised learning framework]({{site.baseurl}}/img/activities/Posts/ESRMB_2025/Figure_1.png)
Figure 1: SpineGPT self-supervised learning framework. The original MRI volume undergoes random masking. The masked volume is then input to the encoder, which generates latent representations capturing structural features of the spinal cord. The decoder reconstructs the original volume by filling in the missing parts based on the learned latent representations. This self-reconstruction objective enables SpineGPT to develop a comprehensive understanding of spinal anatomy from unlabeled data.

For spinal tissue segmentation — a task central to building personalized EES models — we freeze the pretrained encoder and fine-tune the decoder to segment spinal roots, white matter (WM), cerebrospinal fluid (CSF), vertebrae, and intervertebral discs.

### Results

We fine-tuned SpineGPT on 31 high-resolution T2-weighted MRI volumes (0.3 × 0.3 × 0.6 mm³) with labeled CSF, WM, and spinal roots. Testing on an internal set (2 individuals, dorsal and ventral roots) yielded Dice scores of **0.95 ± 0.01** (CSF), **0.94 ± 0.01** (WM), and **0.73 ± 0.00** (spinal roots). On a public lumbosacral dataset (14 participants, dorsal roots only), we achieved **0.91 ± 0.03** (CSF), **0.89 ± 0.23** (WM), and **0.41 ± 0.17** (spinal roots) — already matching state-of-the-art performance on this challenging task.

![Figure 2 — SpineGPT pipeline and preliminary segmentation results]({{site.baseurl}}/img/activities/Posts/ESRMB_2025/Figure_2.png)
Figure 2:  SpineGPT pipeline for spinal tissue segmentation. (1) Finetuning SpineGPT for	 spinal tissue segmentation: A labeled database of personalized models, built from high-definition MRI volumes, is used to target specific spinal tissues: the cerebrospinal fluid (CSF), white matter (WM), and spinal roots. (2) Preliminary results of segmentations of CSF, WM, and spinal roots across axial, sagittal, and coronal views, on a test T2 MRI volume showing SpineGPT’s promising ability to accurately delineate spinal structures in MRI scans.

### Discussion

SpineGPT is a foundation framework for spinal cord T2-weighted MRI, designed to learn from the wealth of unlabeled imaging data available across research and clinical settings. Preliminary results on tissue segmentation are promising, already reaching state-of-the-art performance. Extensive validation remains necessary to ensure robustness across the full diversity of clinical scenarios — but the path toward scalable, automated personalized modelling for EES therapies is becoming clearer.
