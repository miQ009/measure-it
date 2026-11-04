# Project Plan — Measure It

## Project Overview
The goal is to develop a computer vision pipeline that segments a target object and estimates its physical dimensions in millimetres using camera calibration and a known reference object.

## Implementation Plan

1. **Data Collection**
   - Capture 20 checkerboard calibration images.
   - Capture 70 images of the target object.
   - Maintain consistent image quality and object visibility.

2. **Annotation**
   - Annotate all 70 target images using CVAT.
   - Export annotations in COCO format.

3. **Camera Calibration**
   - Use a 7×9 checkerboard with 20 mm squares.
   - Calculate the camera matrix and distortion coefficients using OpenCV.
   - Save calibration parameters.

4. **Image Undistortion**
   - Correct lens distortion in the dataset images.
   - Transform annotation polygon coordinates accordingly.

5. **Model Training**
   - Fine-tune Mask R-CNN with a ResNet50-FPN backbone.
   - Use a 56/14 training-validation split.
   - Train for 10 epochs using a GPU.

6. **Evaluation**
   - Evaluate segmentation using IoU and COCO segmentation AP.
   - Report precision and recall with their evaluation methodology.

7. **Metric Measurement**
   - Use a separate 150 mm ruler as the known reference.
   - Calculate the pixel-to-millimetre scale.
   - Extract the target mask and calculate dimensions using a rotated bounding rectangle.
   - Compare automated measurements with manual measurements.

8. **Documentation and Delivery**
   - Provide project documentation, evaluation results, visual evidence, and source code.
   - Publish the project on GitHub using the required branch `dev-test01`.

## Tools and Technologies
- Python
- OpenCV
- PyTorch
- Torchvision
- Google Colab
- CVAT
- COCO annotation format
- NumPy and Matplotlib

## Current Status
Core calibration, annotation, model training, evaluation, and initial measurement have been completed. Final documentation, repository preparation, and submission remain.
