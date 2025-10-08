# Deep-Pose-Tracker

This repository contains scripts for Deep-Pose-Tracker (DPT), a deep learning model for real-time pose detection of *C. elegans*.

 <img src="sample_outputs/multiclass_detection.gif" height="200" />  <img src="sample_outputs/omega_turns.gif" height="200" />  <img src="sample_outputs/pose_1.gif" height="200" />
 <img src="sample_outputs/pose_2.gif" height="200" />  <img src="sample_outputs/reversals.gif" height="200" />  <img src="sample_outputs/tracking.gif" height="200" />
 <img src="sample_outputs/pose_3.gif" height="200" /> 

<!--
<p align="center">
  <img src="sample_outputs/1x 1 p011.gif" width="500" /><br>
  <em>Pose detection: Example 1</em>
</p>

<p align="center">
  <img src="sample_outputs/multiclass_detection.gif" width="500" /><br>
  <em>Real-time counting multiple class objects</em>
</p>
-->

<!-- ![image alt](https://github.com/cebpLab/Deep-Pose-Tracker/blob/c7a0b8b9b948c293c008b6cad273611e9e1725cd/image.png)  -->

## Model features

The model is composed of the following features:

1. Real-time pose detection
2. Quantification of eigenworms
3. Worm tracking and speed measurement
4. Area measurement
5. Orientation of motion
6. Detecting forward-reverse movement
7. Detecting omega turns
8. Multi-class detection and counting
9. Bacteria/Worm Counting

**Note:** 
1. All the codes are optimized such that they can be used for a single worm as well as multiple worms.
2. The codes work on videos as well as images (wherever applicable).
3. You can keep multiple files in a folder, and give the folder path as input. That will work as well.
4. All the analysis results will be saved inside the `outputs` folder. For example, if you are running the `pose.ipynb` file on some video, the outputs will be saved in the `outputs/pose/run1` folder. If you run this file several times, respective outputs will be saved in `run2`, `run3`, ... inside the main `outputs/pose` folder.


## Repository Structure
The repository consists of the following files-
1. All the codes for the analysis of different properties.
2. Pretrained weights for pose detection, detection of worms and eggs, detecting and counting *C. elegans* worms, and bacteria counting.
3. Pretrained weights on different YOLO architectures and image sizes.
4. Sample input videos for readers to use and practice.


## Installation steps
Here are the steps to install Deep-Pose-Tracker. We highly recommend installing the dependencies in a separate environment. Here we have shown the steps using `conda`. One can use `python3` as well for creating the environments.

1. Clone the repository first, using
   
   ``git clone https://github.com/cebpLab/Deep-Pose-Tracker.git``
   
2. Enter the `Deep-Pose-Tracker` directory.

   ``cd Deep-Pose-Tracker``

3. Create an environment where you install the dependencies.

   ``conda create -n deep-pose-tracker``

   ``conda activate deep-pose-tracker``
   
   ``pip install untralytics``

4. Once the dependencies are installed, you are ready to use the code.


## Annotations


## Training model
The training process is the same as the standard training procedure in [YOLO](https://docs.ultralytics.com/modes/train/). In this model, we have used [YOLOv8](https://docs.ultralytics.com/models/yolov8/) for all the analysis. The training was performed on a custom dataset with labelled images of *C. elegans*. Here are the following details that we followed during training:
- A total of 3455 images were taken for training different YOLOv8 architectures.
- We trained different YOLOv8 architectures (`medium`, `large`, and `extra`) for `pose` detection.
- Training was performed on different input image sizes, which are $640 \times 640$, $832 \times 832$ and $1024 \times 1024$.

Here is the detailed training procedure. We assume that you have properly installed `untralytics`.

1. Import YOLO.

      ``from ultralytics import YOLO``

2. Define the model on which you want to perform the training. Here is the list of different YOLOv8 [models](https://docs.ultralytics.com/tasks/pose/#models) for pose detection.

      ``model = YOLO("yolo11m-pose.pt")``

3. Once the model is defined, you can now start the training.

     ``model.train(data="path/to/data.yaml", epochs=100, save=True, batch=32, val=True, device=[0,1], imgsz=640)``

That's it. Now let's unpack each of the parameters defined here.



















