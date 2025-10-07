# semantic_seg

# Cityscapes Semantic Segmentation Evaluation

A comprehensive framework for evaluating semantic segmentation models on the Cityscapes dataset with IoU-based miscoverage categorization.

## Project Overview

This project evaluates the SegFormer-B0 model on the Cityscapes validation set for car segmentation (class ID: 13), achieving an mIoU of 0.8688.

## Results Summary

### Model Performance (SegFormer-B0 on Car Class)

| Metric    | Value  |
|-----------|--------|
| **mIoU**  | 0.8688 |
| Precision | 0.9191 |
| Recall    | 0.9253 |
| F1-Score  | 0.9155 |
| Images    | 479    |

### Miscoverage Distribution

| Category | Count | Percentage |
|----------|-------|------------|
|  Excellent (IoU ≥ 0.9) | 313 | 65.3% |
|  Good (IoU ≥ 0.75) | 113 | 23.6% |
|  Over-segmentation | 14 | 2.9% |
|  Under-segmentation | 10 | 2.1% |
|  Critical Failure | 7 | 1.5% |
|  Severe Under-segmentation | 6 | 1.3% |
|  Complete Failure | 5 | 1.0% |
|  Poor Alignment | 4 | 0.8% |
|  Severe Over-segmentation | 4 | 0.8% |
|  Moderate Miscoverage | 3 | 0.6% |

## Miscoverage Categories：

### 1. **Excellent** (IoU ≥ 0.9)

### 2. **Good** (IoU ≥ 0.75)

### 3. **Under-segmentation**
Model misses parts of the car, resulting in false negatives.
- Causes: Occlusion, poor lighting, small objects

### 4. **Over-segmentation** 
Model incorrectly predicts non-car pixels as car, resulting in false positives.
- Causes: Similar textures, reflections, shadows

### 5. **Critical/Complete Failure**
Severe misalignment or complete failure to detect the car.
- Causes: Extreme weather, heavy occlusion, dataset annotation errors

**Error Analysis Color Legend**:
- 🟡 **Yellow (TP)**: Correctly predicted car pixels
- 🔴 **Red (FP)**: False positive - incorrectly predicted as car
- 🟢 **Green (FN)**: False negative - missed car pixels
