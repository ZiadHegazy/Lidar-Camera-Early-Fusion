# 🚗 LiDAR–Camera Fusion for Object Detection using Faster R-CNN

## 📌 Overview

This project implements an **early fusion perception pipeline** for autonomous driving by combining **LiDAR point clouds and camera images** to improve vehicle detection performance. The system embeds LiDAR depth information directly into RGB images and trains a **Faster R-CNN** detector on the fused representation.

The project is based on the **KITTI Object Detection Dataset** and targets real-world perception challenges such as scale variation, depth ambiguity, and partial occlusions in autonomous driving environments.

---

## 🎯 Motivation

Camera-only perception systems often struggle with:
- Lack of explicit depth information
- Sensitivity to lighting and weather conditions
- Difficulty detecting distant or partially occluded objects

LiDAR provides accurate 3D geometry but limited semantic context.

**Early fusion** enables the model to jointly learn **appearance and geometric depth cues**, leading to more robust perception for autonomous vehicle systems.

---

## 🧠 Methodology

### 1️⃣ Dataset
- KITTI Object Detection Dataset
- RGB camera images
- Velodyne LiDAR point clouds
- 2D bounding box annotations

---

### 2️⃣ LiDAR to Camera Projection
- LiDAR point clouds are projected into the camera coordinate frame
- Per-point depth values are computed
- A dense depth map is generated for each image

---

### 3️⃣ Early Fusion Strategy
- Depth maps are normalized
- The **blue channel of the RGB image is replaced with LiDAR depth**
- Final fused image format: **(H, W, 3)**

This approach allows the use of standard CNN backbones without architectural changes while injecting geometric information.

---

### 4️⃣ Model Architecture
- **Faster R-CNN**
- ResNet-based backbone
- Implemented using **PyTorch**
- Input: Fused RGB–Depth images
- Output: 2D bounding boxes and class predictions (vehicles)

---

### 5️⃣ Training & Evaluation
- Model trained on fused KITTI samples
- Evaluation metrics:
  - Intersection over Union (IoU)
  - Precision–Recall analysis
- Qualitative comparison against RGB-only detection

---

## 🧪 Results & Observations

- Improved detection confidence for distant vehicles
- Reduced false positives in cluttered scenes
- Demonstrates the effectiveness of early fusion for autonomous perception

*(Quantitative benchmarking such as mAP can be added as future work.)*

---

## 🛠️ Technologies Used

- Python
- PyTorch
- OpenCV
- NumPy
- KITTI Dataset
- Faster R-CNN
- LiDAR point cloud processing

---

## 📂 Project Structure

