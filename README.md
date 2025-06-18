# 🛰️ Ganga River Shrinkage Detection using Vision Transformers (ViT)

This research project focuses on detecting and analyzing the **shrinkage of the Ganga River** across different time periods using **satellite imagery** and advanced **semantic segmentation models**, primarily **Vision Transformers (ViT)**. The analysis is carried out on multi-temporal satellite data from **Sentinel-2, Landsat-8, and Landsat-9**, focusing on regions such as **Prayagraj** and **Varanasi**.

## 📌 Objective

To monitor and quantify the changes in the **Ganga river width** over the past decade by:
- Segmenting water bodies using state-of-the-art deep learning models (ViT, Swin Transformer, SegFormer).
- Applying NDWI (Normalized Difference Water Index) for pre-processing.
- Comparing satellite imagery from **2014 to 2025** for change detection.

---

## 🧠 Model Architecture

The project uses **Vision Transformers (ViT)** for multiclass semantic segmentation. The following architectures were explored:
- ViT (Vanilla)
- Swin Transformer
- SegFormer
- DeepLabV3+ (as baseline for comparison)

---

## 🛰️ Data

- **Sources**: [Sentinel-2](https://sentinel.esa.int/web/sentinel/sentinel-data-access), [Landsat-8 & 9](https://earthexplorer.usgs.gov/)
- **Regions Analyzed**:
  - Prayagraj (Kumbh Mela zone)
  - Varanasi
  - Kanpur, Patna (future expansion planned)
- **Preprocessing**:
  - NDWI computation
  - Resizing and patching of satellite tiles
  - Manual annotation/mask creation using QGIS/LabelMe

---

## 📊 Methodology

1. **Preprocessing**:
   - NDWI masking to isolate water bodies.
   - Image normalization and resizing.

2. **Model Training**:
   - Dataset split into train/val/test.
   - Augmentation using Albumentations.
   - Trained on Google Colab with GPUs.

3. **Evaluation Metrics**:
   - mIoU (Mean Intersection over Union)
   - Pixel Accuracy
   - F1-Score

4. **Change Detection**:
   - Overlay past and present segmentation masks.
   - Compute area difference (in sq.km) to detect river shrinkage.

---

## 📁 Project Structure

