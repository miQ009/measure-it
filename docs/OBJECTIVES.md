# Project Objectives — Measure It

## Primary Objective
Develop a computer vision system capable of segmenting a target object and estimating its real-world dimensions in millimetres.

## Specific Objectives

- Calibrate the camera using checkerboard images.
- Reduce lens distortion before processing images.
- Create a manually annotated dataset containing at least 70 target images.
- Train a custom fine-tuned Mask R-CNN segmentation model.
- Evaluate segmentation performance using IoU and COCO segmentation metrics.
- Use a known physical reference to establish pixel-to-millimetre conversion.
- Estimate object dimensions from the predicted segmentation mask.
- Compare automated measurements against manual measurements.
- Document the methodology, implementation, results, and limitations.

## Expected Outcome
A reproducible prototype that combines camera calibration, instance segmentation, and reference-based metric measurement.

The system should demonstrate the complete measurement workflow while reporting its actual accuracy and limitations.