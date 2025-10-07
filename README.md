# Deep-Pose-Tracker

This repository contains scripts for Deep-Pose-Tracker (DPT), a deep learning model for real-time pose detection of C. elegans.

---

## Model features

The model is composed of the following features:

1. **Real-time pose detection**
   - Supports both single-worm and multi-worm tracking.
   - Generates pose keypoints and annotated outputs.
   - Saves detection outputs (images/videos) and keypoint data for downstream analysis.

3. **Quantification of eigenworms**
   - Computes eigenworm modes from skeletonized body postures.
   - Reduces high-dimensional body coordinates into low-dimensional posture representations.

5. **Worm tracking and speed measurement**
   - Performs multi-object tracking of worms using the YOLOv8 track function with ByteTrack.
   - Produces per-worm trajectory data (positions.csv).
   - Computes metrics like displacement, locomotion speed, and frame-wise motion statistics.

6. **Area measurement**
   - Estimates worm or bacterial colony area using segmentation masks.
   - Useful for quantifying crowding, clustering, and spatial dynamics.

8. **Orientation of motion**
   - Uses Kalman filtering to smooth noisy trajectory data.
   - Computes instantaneous speed, angular orientation, and temporal dynamics for each trajectory.

9. **Detecting forward-reverse movement**
   - Classifies directional motion (forward vs. reverse) based on head-tail orientation dynamics.
   - Visualizes transitions and frequency of reversals.
   - Useful for locomotion pattern analysis.

11. **Detecting omega turns**
   - Detects and counts omega turns and delta turns based on body curvature and eigenworm coefficients.
   - Automatically logs detected events with frame indices and durations.

13. **Multi-class detection and counting**
   - Enables detection of multiple biological entities (e.g., worms, eggs, bacteria) in the same frame.
   - Can be trained with custom YOLOv8 datasets for multi-class recognition.

15. **Bacteria/Worm Counting**
   - Uses YOLOv8 object detection for counting in static images.
   - Saves annotated images with detection boxes and count labels.
   - Exports results (counts per image) as .csv in structured folders (e.g., outputs/counting/run1, run2, etc.).

   

---

## Repository Structure

