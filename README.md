# Protein Cell Classification

Multi-label classification of protein types present in biological microscopy images of blood cells.

## Overview

This project applies deep learning to identify and classify co-occurring protein types within individual blood cell images. The core challenge is a multi-label classification problem — multiple protein types can be present simultaneously in a single image — which requires models and evaluation strategies that go beyond standard single-label approaches.

## Problem

Given a fluorescence microscopy image of a blood cell, predict which protein types are present. The dataset exhibits class imbalance and label co-occurrence, both common in real biological imaging tasks.

## Approach

- **Architecture:** CNN-based classification models trained on biological cell imagery
- **Multi-label handling:** Binary cross-entropy loss with per-class thresholding
- **Evaluation:** Decomposed per-class metrics (precision, recall, F1) alongside aggregate scores to isolate model performance across individual protein types
- **Data challenges addressed:** Class imbalance via weighted sampling and augmentation strategies

## Key Challenges

- **Class co-occurrence:** Multiple protein types present in a single image require independent per-label prediction rather than mutually exclusive classification
- **Class imbalance:** Rare protein types underrepresented in training data — addressed through sampling strategies and evaluation-aware thresholding
- **Evaluation design:** Standard accuracy is misleading for multi-label tasks; decomposed per-class metrics were essential for meaningful model assessment

## Tech Stack

- Python, PyTorch
- torchvision for image preprocessing and augmentation
- scikit-learn for evaluation metrics
- Jupyter Notebook

## Repository Structure

```
Protein-Classification/
├── Protein Multi-label classification.ipynb   # Full training and evaluation pipeline
├── README.md
└── LICENSE
```

## Results

Per-class F1 scores evaluated on held-out test set. Decomposed metrics revealed meaningful variation across protein types, informing targeted data augmentation for underperforming classes.

## Relevance

This work directly addresses the challenge of predicting multiple biological properties from imaging data — a problem structurally analogous to multi-property biosensor performance prediction in protein engineering pipelines.

## Author

**Haider Ali**
[github.com/AliHaider20](https://github.com/AliHaider20) | [linkedin.com/in/haiderzali](https://linkedin.com/in/haiderzali)
