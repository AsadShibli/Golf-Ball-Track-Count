# Golf Ball Track and Count

This repository contains code for detecting and tracking golf balls in video footage. We use YOLOv8 for object detection, trained on a custom dataset. The `Supervision` library is used for drawing annotations, defining zones, and tracking objects across frames. The project is capable of counting objects as they cross a predefined line.

## Demo


https://github.com/user-attachments/assets/807ffb31-b4db-476d-8f27-244dd246ee00


## Table of Contents

- [Features](#features)
- [Usage](#usage)
- [Dataset](#dataset)
- [Model Weight](#Model-Weight)
- [Tracking and Counting](#tracking-and-counting)
- [References](#references)

## Features

- Detect golf balls using a custom-trained YOLOv8 model.
- Track multiple golf balls across frames using `ByteTrack`.
- Count the number of balls crossing a defined line using a line zone.
- Visualize annotated frames with bounding boxes and object IDs.

## Usage

### Step 1: Mount Google Drive (if using Colab)
Ensure you have access to your dataset and output directories by mounting Google Drive:
```python
from google.colab import drive
drive.mount('/content/drive')
```
### Step 2: Run the Tracking and Counting
The main code is in `ball_track_count.ipynb`. Modify the `SOURCE_VIDEO_PATH` and `TARGET_VIDEO_PATH` to point to your video files:
```python
SOURCE_VIDEO_PATH = "/content/drive/MyDrive/client work/0828.mp4"
TARGET_VIDEO_PATH = "/content/drive/MyDrive/client project/result.mp4"
```
To define a custom line for counting objects, modify the `START` and `END` points. You can obtain these coordinates using [this tool](https://roboflow.github.io/polygonzone/) by drawing a line on your image.
```python
START = sv.Point(130, 620)
END = sv.Point(900, 620)
```
### Step 3: Process Video
Run the `callback` function to process each frame and track the golf balls:
```python
sv.process_video(
    source_path=SOURCE_VIDEO_PATH,
    target_path=TARGET_VIDEO_PATH,
    callback=callback
)
```
## Dataset
The dataset for this project was created and manually annotated to detect defects on golf balls. It was uploaded to Roboflow for easy management and download.

## Model Weight
you can download the model weight from this [link](https://drive.google.com/file/d/166nJ4bgnm_bRLNIpq8j_JQFyZSrvzlNn/view?usp=sharing).

## Tracking and Counting
The project uses `ByteTrack` for object tracking, integrated into the callback function. The `Supervision` library is used to define a line zone, and the number of objects crossing this line is tracked.
```python
byte_tracker = sv.ByteTrack()
line_zone = sv.LineZone(start=START, end=END)
```
The results will be saved to `TARGET_VIDEO_PATH`.

## References
- [Roboflow PolygonZone Tool](https://roboflow.github.io/polygonzone/)
- [YOLOv8 Documentation](https://docs.ultralytics.com/models/yolov8/)
- [Supervision Library](https://github.com/roboflow/supervision)



