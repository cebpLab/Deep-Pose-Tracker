# Deep-Pose-Tracker

This repository contains scripts for Deep-Pose-Tracker (DPT), a deep learning model for real-time pose detection of C. elegans.

---

## Model features

The model is composed of the following features:

1. **Real-time pose detection**

2. **Quantification of eigenworms**

3. **Worm tracking and speed measurement**
   - Performs multi-object tracking of worms from video files using the YOLOv8 `track` function (ByteTrack).
   - Generates trajectory data (`positions.csv`) and computes per-worm distance and velocity statistics.

5. **Area measurement**

6. **Orientation of motion**
   - Uses Kalman filtering to smooth noisy trajectory data.
   - Computes velocity, angular orientation, and temporal dynamics for each trajectory.

8. **Detecting forward-reverse movement**

9. **Detecting omega turns**

10. **Multi-class detection and counting**

11. **Bacteria/Worm Counting**
   - Uses YOLOv8 object detection to count organisms in static images.
   - Saves annotated images and count data.

   

---

## Repository Structure

