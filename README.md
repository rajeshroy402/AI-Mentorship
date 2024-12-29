# YOLOv8 Setup and Usage Guide

## Requirements

Make sure you have the necessary environment with NVIDIA GPU support.

---

### Check GPU Status

```bash
!nvidia-smi
```

**Explanation:** The `!nvidia-smi` command displays information about your NVIDIA GPU, such as usage, temperature, and memory allocation. Ensure that the GPU is available and working for efficient model processing.

---

### Set Current Directory

```python
import os
HOME = os.getcwd()
print(HOME)
```

**Explanation:** This sets the `HOME` variable to the current working directory and prints it to confirm the environment setup.

---

### Install YOLOv8

```bash
!pip install ultralytics==8.2.103 -q
```

**Explanation:** Installs the `ultralytics` library, which provides YOLOv8 functionality.

---

### Check Installation

```python
from IPython import display

display.clear_output()

import ultralytics
ultralytics.checks()
```

**Explanation:** Verifies the `ultralytics` library installation and checks for system compatibility.

---

### Import Required Libraries

```python
from ultralytics import YOLO
from IPython.display import display, Image
```

**Explanation:** Imports the YOLO class for model interactions and utilities for displaying images in a Jupyter environment.

---

### YOLOv8 Command Usage

The following example demonstrates the usage of YOLOv8 commands:

#### Training
```bash
!yolo task=detect mode=train model=yolov8n.yaml
```

#### Prediction
```bash
%cd {HOME}
!yolo task=detect mode=predict model=yolov8l.pt conf=0.7 source='https://media.roboflow.com/notebooks/examples/dog.jpeg' save=True
```

**Explanation:** This runs the YOLOv8 model in prediction mode using the pre-trained `yolov8l.pt` model. The confidence threshold is set to `0.7`, and the image source is a URL. The prediction results are saved in the specified directory.

#### Classification
```bash
!yolo task=classify mode=predict model=yolov8n-cls.yaml
```

#### Segmentation
```bash
!yolo task=segment mode=val model=yolov8n-seg.yaml
```

#### Export
```bash
!yolo task=detect mode=export model=yolov8n.pt format=onnx
```

**Explanation:** These commands cover training, classification, segmentation, validation, and export functionalities of YOLOv8.

---

### Results

- **Predictions:** The prediction results include bounding boxes, confidence scores, and class labels. They are saved in the specified output folder.
- **Output Files:** Exported models can be used in various formats such as ONNX for deployment.

---

Enjoy using YOLOv8 for your object detection, classification, and segmentation tasks!
