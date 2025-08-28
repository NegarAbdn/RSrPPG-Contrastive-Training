# RS-rPPG: Contrastive Training (Selected Implementation)

This repository contains the **selected implementation from my MSc thesis project**.  
It demonstrates the **contrastive training stage** of RS-rPPG (Remote Photoplethysmography) for non-contact heart-rate estimation, with a focus on robustness under **H.264 video compression**.

---

## Key Features
- **Contrastive learning (triplet loss)** in the frequency domain  
- **Frequency-band regularization** (0.5–3 Hz, heart-rate range)  
- **Swin Transformer** encoder–decoder for spatio-temporal features  
- **Single- and multi-dataset** training scripts  
- Automatic saving of model weights, logs, and plots  

---

## Files in this Repository
- `trained_modified.py` — contrastive training on a **single dataset**  
- `trained_modified_multi.py` — contrastive training on **multiple datasets**

These are the core training scripts ; they refine RS-rPPG for realistic, compressed-video scenarios.

---

## Example Usage

### Single dataset
```bash
python trained_modified_version.py \
  --name exp1 \
  --data purecrf10 \
  --fold 1 \
  --margin 0 \
  --batch 4 \
  --pre 1 \
  --epochs 30 \
  --use_crf0_tmaps 0/1
```

### Multi-dataset
```bash
python trained_modified_version_multi.py \
  --name exp_multi \
  --data purecrf5,purecrf10 \
  --fold 1 \
  --margin 0 \
  --batch 4\
  --pre 1 \
  --epochs 30 \
  --use_crf0_tmaps 0/1
```

---

## Outputs
Each run automatically saves results under an output folder:

- **`.pt`** → trained model weights  
- **`.txt`** → training and validation logs  
- **`.png`** → error plots and RMSE/MAE curves  

---

## Context
This work was completed as part of my **Master’s thesis in Applied Mathematics (Data Science & Optimization) at Vrije Universiteit Amsterdam**, in collaboration with **VicarVision**.  

The thesis investigated how **H.264 video compression** affects rPPG-based heart-rate estimation and proposed the use of **uncompressed Tmaps during contrastive training** to improve robustness.  

---

## Note
This repository is focused on showcasing the **selected implementation**.  
Supporting dataset loaders, utilities, and full experimental pipelines are part of the **complete thesis codebase** and are not included here.  

---
