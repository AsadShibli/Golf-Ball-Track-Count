# Golf Ball Track and Count

This repository contains code for detecting and tracking golf balls in video footage. We use YOLOv8 for object detection, trained on a custom dataset. The `Supervision` library is used for drawing annotations, defining zones, and tracking objects across frames. The project is capable of counting objects as they cross a predefined line.

## Demo


https://github.com/user-attachments/assets/807ffb31-b4db-476d-8f27-244dd246ee00


## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Dataset](#dataset)
- [Training the Model](#training-the-model)
- [Tracking and Counting](#tracking-and-counting)
- [References](#references)

## Features
- Detect golf balls using a custom-trained YOLOv8 model.
- Track multiple golf balls across frames using `ByteTrack`.
- Count the number of balls crossing a defined line using a line zone.
- Visualize annotated frames with bounding boxes and object IDs.

## Installation
To run the project, clone this repository and install the required dependencies:

```bash
# Clone the repository
git clone https://github.com/yourusername/GolfBallTrackCount.git

# Navigate to the project directory
cd GolfBallTrackCount

# Install dependencies
pip install -r requirements.txt
