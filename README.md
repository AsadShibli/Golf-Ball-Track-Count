# Golf Ball Track and Count

This repository is designed to track and count golf balls in video footage using object detection and line crossing. The project utilizes a custom-trained YOLOv8 model and integrates the `Supervision` library for video frame processing, object tracking, and zone counting.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Dataset](#dataset)
- [Training the Model](#training-the-model)
- [Tracking and Counting](#tracking-and-counting)
- [References](#references)

## Overview
This repository contains code for detecting and tracking golf balls in video footage. We use YOLOv8 for object detection, trained on a custom dataset. The `Supervision` library is used for drawing annotations, defining zones, and tracking objects across frames. The project is capable of counting objects as they cross a predefined line.

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
