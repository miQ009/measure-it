# Measure It — Segmentation and Metric Measurement

## Overview
Measure It is a computer vision prototype that segments a target object and estimates its physical dimensions in millimetres.

The pipeline combines camera calibration, image undistortion, instance segmentation, and reference-based pixel-to-millimetre conversion.

## Workflow
1. Capture checkerboard images for camera calibration.
2. Collect and annotate target object images.
3. Calibrate the camera using OpenCV.
4. Undistort images and transform annotation coordinates.
5. Fine-tune a Mask R-CNN segmentation model.
6. Evaluate predictions on a held-out validation set.
7. Use a known-size ruler to calculate pixel scale.
8. Estimate object dimensions from the segmentation mask.

## Dataset
- Calibration images: 20
- Target images: 70
- Training images: 56
- Validation images: 14
- Annotation format: COCO
- Annotation tool: CVAT

## Model
- Architecture: Mask R-CNN
- Backbone: ResNet50-FPN
- Framework: PyTorch / Torchvision
- Training epochs: 10
- Training environment: Google Colab Tesla T4 GPU
- Initialization: Pretrained COCO weights, fine-tuned on the collected dataset.

## Evaluation Results

| Metric | Result |
|---|---:|
| Mean IoU | 94.93% |
| COCO Segmentation AP (0.50:0.95) | 94.3% |
| AP@0.50 | 100% |
| AP@0.75 | 100% |
| AR@100 | 95.7% |
| Image-level Precision | 100% |
| Image-level Recall | 100% |

Precision and recall are image-level measurements based on an IoU threshold of 0.5, not detection-level metrics.

## Metric Measurement

A separate 150 mm ruler was used as the reference object.

**Initial measurement results:**

| Dimension | Automated | Manual |
|---|---:|---:|
| Length | 89.37 mm | 86 mm |
| Width | 58.41 mm | 54 mm |

The initial measurement errors were 3.37 mm and 4.41 mm respectively.

## Project Structure

```text
measure-it/
├── calibration/
├── dataset/
├── models/
├── outputs/
├── notebooks/
├── docs/
│   ├── PLAN.md
│   ├── OBJECTIVES.md
│   └── DEFINITION_OF_DONE.md
└── README.md
```

## Technologies
- Python
- OpenCV
- PyTorch
- Torchvision
- NumPy
- Matplotlib
- CVAT
- Google Colab

## Limitations
The current prototype has minor segmentation boundary errors and measurement discrepancies. Results may also be affected by perspective, reference alignment, and the accuracy of manual measurements.

## Reproducibility
The notebook contains the implementation workflow. The calibration parameters, trained model, dataset, and annotations are provided as project artifacts where repository size permits.

## Status
Core implementation and initial evaluation completed. Final packaging and submission preparation in progress.

## Download Assets

Large files are hosted on Google Drive due to GitHub file size limitations.

- [Calibration Images](https://drive.google.com/drive/folders/1gg2RwZ4S2A3tOTM5c0RpBG8jSAh5l67P?usp=sharing)
- [Dataset Images (70 images)](https://drive.google.com/drive/folders/1Kv3lPQ8vHWLgPkLuD3w9KX_U-Arl-l_Q?usp=sharing)
- [Trained Mask R-CNN Model](https://drive.google.com/drive/folders/1q3_l1ffbPMbT2TaL1RB6EgaUXX6wRPOh?usp=sharing)

Download these assets before running the notebook.
