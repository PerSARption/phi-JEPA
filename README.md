<div align="center">

# &phi;-JEPA: Where and What to Reconstruct in Physics-Informed Radar Pre-training?

**Xin Zhang**, **Jiawei Pi**, **Yanhua Wang**, **Liang Zhang**, and **Yang Li**

Radar Technology Research Institute, Beijing Institute of Technology  
Zhengzhou Research Institute, Beijing Institute of Technology  
Henan Provincial Center for Integrated Innovation in Advanced Radar Intelligent Sensing

[![Pretrained Weights](https://img.shields.io/badge/Hugging%20Face-Weights-FFD21E?logo=huggingface&logoColor=black)](https://huggingface.co/kiki-orb/phi-JEPA)
![Status](https://img.shields.io/badge/Release-Weights%20Only-blue)

</div>

## News

- **2026-08-03:** The first &phi;-JEPA pretrained checkpoint is publicly available on [Hugging Face](https://huggingface.co/kiki-orb/phi-JEPA).
- Training code and downstream evaluation code will be released in a future update.

## Overview

Synthetic aperture radar (SAR) image pre-training aims to learn transferable representations from unlabeled SAR data. Existing masked modeling methods commonly rely on random masking and low-level reconstruction targets, which may overlook sparse, target-related scattering responses and overfit speckle fluctuations or background clutter.

We propose **&phi;-JEPA**, a physics-informed masked autoencoder for self-supervised SAR image pre-training. The method introduces:

1. **Scattering-Center-Aware Masked Modeling (SCM):** attributed scattering centers are used to reconstruct a physical scattering prior, which guides masking toward informative target regions while preserving sufficient visible context.
2. **SAR-Specific Semantic Feature Prediction (SFP):** a frozen SARCLIP ViT-B/16 image encoder supplies patch-level semantic targets, replacing low-level pixel or handcrafted-feature reconstruction with semantic representation prediction.

Together, SCM and SFP encourage the encoder to learn physically meaningful and transferable SAR representations for few-shot target recognition.

## Pretrained Weights

The pretrained checkpoint used in our main experiments is available below.

| Method | Backbone | Input size | Pre-training dataset | Epochs | Download |
|---|---|---:|---|---:|---|
| &phi;-JEPA | ViT-B/16 | 224 x 224 | ATRNet-STAR | 100 | [Hugging Face](https://huggingface.co/kiki-orb/phi-JEPA/blob/main/main_experiments/phi_jepa_vitb16_e100.pth) |

