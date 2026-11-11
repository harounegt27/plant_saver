# 🌿 Plant Saver — YOLOv8 + SAM for Agricultural Pest Detection & Segmentation

> Detecting and segmenting crop pests using YOLOv8 object detection combined with  
> the Segment Anything Model (SAM) — applied to real field images.

---

## 📌 Project Overview

This project implements a two-stage vision pipeline for **agricultural pest detection and segmentation**:

1. **YOLOv8** detects and localizes pest instances in crop images
2. **SAM (Segment Anything Model)** refines the detected bounding boxes into precise segmentation masks

The pipeline is applied to greenhouse and field images containing three pest categories:
- 🐛 **Aphids** (*진딧물*)
- 🦟 **Whitefly — Nymph stage** (*가루이-약충*)
- 🦟 **Whitefly — Adult stage** (*가루이-성충*)

This work is directly relevant to **weakly-supervised segmentation** challenges in agriculture,
where pixel-level annotations are expensive and image-level labels are more accessible.

---

## 🧠 Why This Matters

In real agricultural settings:
- Multiple pest species can **coexist in the same image**
- Species are often **visually similar** and small
- **Pixel-wise annotation is costly** — making weakly supervised approaches essential

This project explores how detection models (YOLO) can be combined with foundation models (SAM)
to generate segmentation masks **without full pixel-level supervision** — a core challenge
also addressed in weakly supervised semantic segmentation research (CAM → pseudo-masks → SAM refinement).

---

## 📊 Dataset

| Class | Original | Train | Validation |
|---|---|---|---|
| Aphid | 742 | 575 | 144 |
| Whitefly (nymph) | 615 | 490 | 123 |
| Whitefly (adult) | 708 | 566 | 142 |
| **Total** | **2,065** | **1,631** | **409** |

After data augmentation (×2.8):

| Split | Count |
|---|---|
| Train | 4,566 |
| Validation | 1,183 |
| **Total** | **5,749** |

---

## ⚙️ Training Configuration

| Parameter | Value |
|---|---|
| Model | YOLOv8 |
| Image size | 1024 × 1024 |
| Batch size | 16 |
| Epochs | 300 |
| Workers | 0 |

---

## 📈 Results

- ✅ Confusion matrix showing strong per-class discrimination
- ✅ Stable Train/Validation loss curves
- ✅ High F1-score across pest categories
- ✅ SAM-refined masks visually consistent with pest boundaries

---

## 🛠️ Tech Stack

- Python 3.x
- [YOLOv8 — Ultralytics](https://github.com/ultralytics/ultralytics)
- [SAM — Segment Anything Model (Meta AI)](https://github.com/facebookresearch/segment-anything)
- OpenCV
- PyTorch

---

## 🔗 References

- Original project blog post: [ethanseok.github.io](https://ethanseok.github.io/2023-07-04/yolo_v8_pest-post)
- Original repository: [EthanSeok/YOLO_v8_with_SAM](https://github.com/EthanSeok/YOLO_v8_with_SAM)
- Ultralytics YOLOv8: [ultralytics.com](https://ultralytics.com)
- SAM paper: [Segment Anything — Meta AI Research](https://arxiv.org/abs/2304.02643)

---

## 👤 Maintained by

**Haroun Mezned**  
4th-year Data Science & AI Engineering Student — TEK-UP University, Tunis  
📧 meznedharoun99@gmail.com  
🌐 [myportfoliomhm.netlify.app](https://myportfoliomhm.netlify.app)
