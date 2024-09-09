# YOLOv9 + DeepSORT for Object Detection and Tracking

This repository contains a project combining **YOLOv9** for object detection and **DeepSORT** for object tracking. The system detects objects in real-time and assigns unique IDs to each detected object, ensuring accurate tracking across frames.

## For easy and interactive use, I have made this all in one Google Colab Notebook : [Notebook Link](https://colab.research.google.com/drive/1lp3bGxLWAq26XZmoKZW6vvNaZyXrZIKf?usp=sharing) : Just follow & understand the procedure.

## Table of Contents
- [Project Overview](#project-overview)
- [Installation](#installation)
- [Usage](#usage)
  - [Running on Images](#running-on-images)
  - [Running on Videos](#running-on-videos)
- [Model Training](#model-training)
- [Tracking Algorithm](#tracking-algorithm)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Project Overview
This project integrates the **YOLOv9** model for object detection with **DeepSORT**, a popular multi-object tracking algorithm. It enables accurate detection and tracking of objects in real-time from both video and image inputs. YOLOv9 is responsible for identifying and classifying objects, while DeepSORT tracks their movements across frames, maintaining unique IDs even after re-entry or occlusion.

### Features:

- **Fast Object Detection**: Using YOLOv9, the system can detect multiple objects with high accuracy.
- **Object Tracking**: DeepSORT assigns and maintains unique IDs for objects, making tracking smooth even across occlusions.
- **Real-Time Processing**: Capable of processing video feeds in real-time.
- **Customizable Models**: Supports custom YOLOv9 models for specific object categories.

## Installation
Clone the repository and install the required dependencies.

```bash
git clone https://github.com/Rachit2912/YOLOv9_Deepsort
```

```bash
cd YOLOv9_Deepsort
```

```bash
pip install -r requirements.txt -q
```

## Usage:
### Running on Images:
To run the detection and tracking on a static image, use the following command:

```bash
python detect_dual.py --source path/to/image.jpg --weights yolov9-c.pt --device cpu 
```

### Running on Videos:
To run detection and tracking on a video file:

```bash
python detect_dual_tracking.py --source path/to/video.mp4 --weights yolov9-c.pt --device cpu 
```

#### Options:
--source: Path to image or video file. \
--weights: Path to YOLOv9 pre-trained weights.

## Model Training:
To train your own YOLOv9 model on custom data, follow these steps:
Prepare your dataset in YOLO format.
Modify the configuration files for your dataset.
Run the training script:
```bash
python train.py --data path/to/data.yaml --cfg path/to/yolov9.cfg --weights yolov9.pt --device cpu 
```

### Tracking Algorithm
This project uses DeepSORT (Deep Simple Online and Realtime Tracking) to track objects after they have been detected. DeepSORT improves upon the original SORT algorithm by using deep learning to model the appearance of objects, making it more robust to occlusions and re-entry of objects into the frame.

### Results
Check the runs/detect/  directory for latest results of image and video detection and tracking.

Here are some example outputs:
### Image Results:
[Click Here](https://kajabi-storefronts-production.kajabi-cdn.com/kajabi-storefronts-production/file-uploads/blogs/22606/images/1446e76-f181-6047-4e73-8d8ba3c6a50e_object_detection_1.webp)
### Video Results:
[Click Here](https://www.youtube.com/watch?v=chzq2E75M84)

The model was able to successfully track multiple objects, maintaining unique IDs for each object and re-assigning them after temporary occlusions.

### Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

