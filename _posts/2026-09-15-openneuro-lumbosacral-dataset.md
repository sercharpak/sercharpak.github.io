---
layout: post
section-type: post
title: "Open dataset: lumbosacral spinal cord task fMRI now on OpenNeuro"
category: Research
tags: ['neuroimaging', 'fMRI', 'open science']
---

I am happy to share that the dataset underlying our [*Imaging Neuroscience* study on lumbosacral spinal cord task fMRI]({{site.baseurl}}/research/2025/01/23/imaging-neuroscience-lumbosacral-fmri.html) is now openly available on [OpenNeuro](https://openneuro.org/):

**[ds008803: Towards personalized mapping through lumbosacral spinal cord task fMRI](https://openneuro.org/datasets/ds008803/versions/1.0.0)**

DOI: [10.18112/openneuro.ds008803.v1.0.0](https://doi.org/10.18112/openneuro.ds008803.v1.0.0)

Corresponding to: [Hernandez-Charpak et al., *Imaging Neuroscience*, Vol. 3 (2025)](https://doi.org/10.1162/imag_a_00455)

---

### What's in the dataset

The release covers the full acquisition from the study: anatomical, functional, timings, and physiological (cardiac, respiration) data for all 12 healthy participants across four sessions each:

- **High-resolution anatomical scans:** T2-weighted structural volumes of the lumbosacral spinal cord, including a reduced field-of-view **ZOOMit** T2w sequence for improved local resolution.
- **Task-based functional MRI**, spanning 14 conditions targeting the extensor and flexor muscles of the right ankle, knee, and hip:
  - **Ankle (4):** active extension, active flexion, passive extension, passive flexion
  - **Knee (2):** active extension, passive flexion
  - **Hip (2):** active flexion, passive extension
  - **Tendon vibration (6):** extension and flexion vibration at the ankle, knee, and hip, isolating proprioceptive afferent input without active or passive joint movement
- **Event timing files** for every run, marking stimulus/movement onsets and durations for first-level analysis.
- **Physiological recordings** (cardiac and respiratory traces) acquired alongside each functional run, enabling retrospective physiological noise correction (e.g. RETROICOR) — a particularly important step for spinal cord fMRI given the region's sensitivity to cardiac-related pulsatility and respiration.

Sharing the raw data alongside the timing and physiological files means the full pipeline — from preprocessing through activation mapping — can be reproduced or re-purposed, whether to benchmark new spinal cord fMRI analysis methods, pool with other lumbosacral datasets, or revisit the active/passive/vibration contrasts with alternative models.

If you use this dataset, please cite both the OpenNeuro release and the original article linked above.

![Figure 2 — Group-level activity for all conditions and muscles]({{site.baseurl}}/img/activities/Posts/IMAG_2025/imag_a_00455_fig2.png)