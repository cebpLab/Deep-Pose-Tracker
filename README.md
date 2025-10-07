# Deep-Pose-Tracker

This repository contains scripts for Deep-Pose-Tracker (DPT), a deep learning model for real-time pose detection of C. elegans.

---

## Model features

The model is composed of the following features:

1. **Real-time pose detection**
   - Generates pose keypoints and annotated outputs.
   - Saves detection outputs (images/videos) and keypoint data for downstream analysis.

2. **Quantification of eigenworms**
   - Computes eigenworm modes from skeletonized body postures.
   - Reduces high-dimensional body coordinates into low-dimensional posture representations.

3. **Worm tracking and speed measurement**
   - Performs multi-object tracking of worms using the YOLOv8 track function with ByteTrack.
   - Produces per-worm trajectory data (positions.csv).
   - Computes metrics like displacement, locomotion speed, and frame-wise motion statistics.

4. **Area measurement**
   - Estimates worm or bacterial colony area using segmentation masks.
   - Useful for quantifying crowding, clustering, and spatial dynamics.

5. **Orientation of motion**
   - Uses Kalman filtering to smooth noisy trajectory data.
   - Computes instantaneous speed, angular orientation, and temporal dynamics for each trajectory.

6. **Detecting forward-reverse movement**
   - Classifies directional motion (forward vs. reverse) based on head-tail orientation dynamics.
   - Visualizes transitions and frequency of reversals.
   - Useful for locomotion pattern analysis.

7. **Detecting omega turns**
   - Detects and counts omega turns and delta turns based on body curvature and eigenworm coefficients.
   - Automatically logs detected events with frame indices and durations.

8. **Multi-class detection and counting**
   - Enables detection of multiple biological entities (e.g., worms, eggs, bacteria) in the same frame.
   - Can be trained with custom YOLOv8 datasets for multi-class recognition.

9. **Bacteria/Worm Counting**
   - Uses YOLOv8 object detection for counting in static images.
   - Saves annotated images with detection boxes and count labels.

**Note:** 
1. All the codes are optimized such that they can be used for a single worm as well as multiple worms.
2. The codes work on videos as well as images (wherever applicable).
3. You can keep multiple files in a folder, and give the folder path as input. That will work as well.
4. All the analysis results will be saved inside the `outputs` folder. For example, if you are running the `pose.ipynb` file on some video, the outputs will be saved in `outputs/pose/run1` folder. If you run this file several times, respective outputs will be saved in `run2`, `run3`, ... inside the main `outputs/pose` folder.

---

## Repository Structure
The repository consists of the following files-
1. All codes for the analysis of different properties.
2. Pretrained weights for pose detection, detection of worms and eggs, detecting and counting C. elegans worms, and bacteria counting.
3. Sample input videos for readers to use and practice.

