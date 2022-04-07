# my YOLO Projects

## Table of Contents

- [About](#about)
- [Getting Started](#getting_started)
- [Projects](#projects)

## About <a name = "about"></a>

YOLO is a family of compound-scaled object detection models trained on the COCO dataset, and includes simple functionality for Test Time Augmentation (TTA), model ensembling, hyperparameter evolution, and export to ONNX, CoreML and TFLite.

Through this repository you will find some projects of my own developed using the YOLO object detection models.

## Getting Started <a name = "getting_started"></a>

### Installing YOLO from Ultralytics

```
git clone https://github.com/ultralytics/yolov5
cd yolov5
pip install requirements.txt
```

### Software for label images

```
git clone https://github.com/tzutalin/labelImg
pip install pyqt5 lxml --upgrade
cd labelImg && pyrcc5 -o libs/resources.py resources.qrc

python .\labelImg.py
```

### Train YOLOv5 from scratch (example from Drowsiness Detection)

### 1. Create dataset.yaml

```
# Train/val/test sets as 1) dir: path/to/imgs, 2) file: path/to/imgs.txt, or 3) list: [path/to/imgs1, path/to/imgs2, ..]
path: ../data/drowsinessDetection # dataset root dir
train: images # train images
val: images # val images
test: # test images (optional)

# Classes
nc: 17 # number of classes
names: [
    "dog", "person", "cat", "tv", "car", "meatballs", "marinara sauce",
    "tomato soup", "chicken noodle soup", "french onion soup", "chicken breast",
    "ribs", "pulled pork", "hamburger", "cavity", "awake", "drowsy"
] # class names

download: # (optional)
```

### 2. Run cmd

```
python ./yolov5/train.py --img 320 --batch 16 --epochs 100 --data ./data/drowsinessDetection/dataset.yaml --weights yolov5s.pt --workers 2 --project ../data/drowsinessDetection/runs/train
```

<!--

A step by step series of examples that tell you how to get a development env running.

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo.

-->

## Projects <a name = "projects"></a>

### 1. Drowsiness Detection (from youtube Tutorial @NicholasRenotte)

![batch](utils\drowsinessDetection\val_batch1_labels.jpg)
![results](utils\drowsinessDetection\results.png)

<p align="center">
  <img alt="Light" src="utils\drowsinessDetection\F1_curve.png" width="33%">
&nbsp; &nbsp; &nbsp; &nbsp;
  <img alt="Dark" src="utils\drowsinessDetection\P_curve.png" width="33%">
&nbsp; &nbsp; &nbsp; &nbsp;
  <img alt="Dark" src="utils\drowsinessDetection\R_curve.png" width="33%">
</p>