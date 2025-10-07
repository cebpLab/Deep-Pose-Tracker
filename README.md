# Deep-Pose-Tracker

This repository contains scripts for Deep-Pose-Tracker (DPT), a deep learning model for real-time pose detection of *C. elegans*.

---

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
4. All the analysis results will be saved inside the `outputs` folder. For example, if you are running the `pose.ipynb` file on some video, the outputs will be saved in `outputs/pose/run1` folder. If you run this file several times, respective outputs will be saved in `run2`, `run3`, ... inside the main `outputs/pose` folder.

---

## Repository Structure
The repository consists of the following files-
1. All codes for the analysis of different properties.
2. Pretrained weights for pose detection, detection of worms and eggs, detecting and counting *C. elegans* worms, and bacteria counting.
3. Sample input videos for readers to use and practice.

