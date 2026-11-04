# Definition of Done — Measure It

## 1. Data Collection and Annotation
The data preparation phase is complete when:
- At least 70 original images of the target object have been collected.
- All target images have corresponding segmentation annotations.
- Annotations are exported in COCO format and validated against the image dataset.
- At least 20 checkerboard images are available for camera calibration.

## 2. Camera Calibration and Undistortion
Camera calibration is complete when:
- OpenCV successfully detects checkerboard corners in the calibration images.
- The camera matrix and distortion coefficients are calculated and saved.
- Calibration parameters can be loaded for subsequent processing.
- Dataset images are undistorted and their corresponding annotation coordinates are transformed consistently.

## 3. Segmentation Model
Model development is complete when:
- A Mask R-CNN model is configured for the target object class.
- The model is fine-tuned using the collected and annotated dataset.
- Training and validation datasets are kept separate.
- The trained model is saved and can generate segmentation predictions on unseen images.

## 4. Model Evaluation
Model evaluation is complete when:
- Mean Intersection over Union (IoU) is calculated on the validation dataset.
- COCO segmentation Average Precision (AP) is reported.
- Precision and recall are calculated with their evaluation methodology clearly stated.
- Prediction visualizations are available for qualitative inspection.

## 5. Metric Measurement
The measurement phase is complete when:
- A separate rigid reference object with known dimensions is placed in the same plane as the target.
- Pixel-to-millimetre scale is calculated from the reference.
- The segmentation mask is used to estimate the target's dimensions.
- Automated measurements are compared against manual measurements.
- Measurement discrepancies and potential sources of error are documented.

## 6. Documentation and Delivery
The project delivery is complete when:
- The README explains the project, workflow, dependencies, results, and limitations.
- The Plan, Objectives, and Definition of Done documents are included.
- Source code, dataset annotations, calibration parameters, model artifacts, and relevant outputs are organized.
- A public GitHub repository is available with the required `dev-test01` branch.
- Project development history is represented through incremental commits.
- A Loom recording of no more than five minutes addresses all four assessment questions.
- The repository and recording links are ready for submission.

## 7. Current Implementation Status and Limitations

The core data preparation, calibration, undistortion, model training, and initial evaluation phases have been completed.

Current evaluation results:
- Mean IoU: 94.93%
- COCO segmentation AP@[0.50:0.95]: 94.3%
- AP@0.50: 100%
- AP@0.75: 100%

Initial measurement comparison:
- Automated measurement: 89.37 × 58.41 mm
- Manual measurement: approximately 86 × 54 mm
- Length discrepancy: 3.37 mm
- Width discrepancy: 4.41 mm

The current measurement output does not yet match the manual reference closely. Minor segmentation boundary errors and possible reference alignment or perspective effects remain limitations.

The implementation should be considered a working prototype. Final delivery is complete only after the documentation, repository, required branch, incremental commits, and Loom recording are prepared.