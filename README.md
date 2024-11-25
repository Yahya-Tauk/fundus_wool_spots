# fundus_wool_spots
This project demonstrates the use of YOLOv11X to detect medical anomalies in fundus images. The model was trained using a small dataset annotated manually in YOLO format. Despite the limited dataset, the trained model shows promising results in identifying anomalies with high accuracy.
- A manually annotated dataset with 69 images (60 training, 6 validation, 3 testing).
- YOLOv11X trained for 200 epochs starting from a pre-trained checkpoint.
- Model achieves moderate accuracy and precision on test images.
- Annotation and training pipeline simplified using Roboflow and Ultralytics.

## Dataset
The dataset was created manually using the following process:
1. Annotated the initial 3 images provided.
2. Annotated 6 additional images manually to expand the dataset.
3. Collected 60 additional images (some containing anomalies, others not) and annotated them using [Roboflow](https://roboflow.com).

The dataset includes:
- **Training images**: 60
- **Validation images**: 6
- **Test images**: 3

## Training
The YOLOv11X model was fine-tuned using Ultralytics' pre-trained checkpoint.

### Training Configuration:
- **Model**: YOLOv11X
- **Images**: 720x720 resolution
- **Epochs**: 200
- **Batch Size**: 16

### Steps:
1. Converted annotations to YOLO format using Roboflow.
2. Set up the YOLO dataset structure and configuration (`data.yaml`).
3. Trained the model using the following command:
   ```bash
   !yolo task=detect mode=train model=yolo11x.pt data=/path/to/data.yaml epochs=200 imgsz=720


