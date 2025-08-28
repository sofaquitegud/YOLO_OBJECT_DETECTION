# YOLOv8 Object Detection Assessment

## Overview

This project demonstrates object detection using YOLOv8s on a custom dataset containing `live` and `spoof` images. The workflow covers preprocessing, visualization, training, evaluation, and deployment steps.

## Directory Structure

```
data/
  dataset.yaml                # YOLO dataset configuration
  datasets/
    images/
      train/                  # Raw training images
      val/                    # Raw validation images
      test/                   # Raw test images
    labels/
      train/                  # Raw training labels
      val/                    # Raw validation labels
      test/                   # Raw test labels
    train.txt                 # List of training images
    val.txt                   # List of validation images
    test.txt                  # List of test images
  processed/
    train/
      images/                 # Preprocessed training images (resized)
      labels/                 # Preprocessed training labels (normalized)
    val/
      images/                 # Preprocessed validation images
      labels/                 # Preprocessed validation labels
    test/
      images/                 # Preprocessed test images
      labels/                 # Preprocessed test labels

runs/
  detect/
    train/                    # YOLOv8 training outputs (weights, plots, metrics)
    val/                      # YOLOv8 validation outputs

object_detection.ipynb        # Main notebook with code, results, and explanations
```

## Steps

1. **Preprocessing:**

   - Images resized to 640x640.
   - Bounding box coordinates normalized for YOLO format.
   - Output saved in `data/processed/`.

2. **Visualization:**

   - Bounding boxes drawn on sample images to verify preprocessing.

3. **Training:**

   - Model: YOLOv8s (`yolov8s.pt`)
   - Dataset: `data/processed/`
   - Config: See `data/dataset.yaml`
   - Training results and weights saved in `runs/detect/train/`.

4. **Evaluation:**

   - Validation and test sets evaluated using trained weights.
   - Metrics and visualizations included in notebook.

5. **Bonus (Deployment):**
   - Example FastAPI code provided for model serving.
   - Other improvements (accuracy, speed, conversion) described in notebook.

## Usage

- Run all cells in `object_detection.ipynb` for end-to-end workflow.
- Training and evaluation use the processed dataset (`data/processed/`).
- Model weights and results are in `runs/detect/train/`.

## Notes

- Classes:
  - `0`: live
  - `1`: spoof
