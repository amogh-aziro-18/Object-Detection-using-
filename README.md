# Object Detection using YOLOv8  

## Introduction  
This project demonstrates an **end-to-end object detection pipeline** using **YOLOv8 (Ultralytics)**. The goal was to train and evaluate a model capable of detecting cows (and other classes) from a custom dataset. The pipeline was built and executed entirely in **Google Colab** with GPU acceleration.  

YOLOv8 is a **Convolutional Neural Network (CNN)-based model**, optimized for real-time object detection and classification. By leveraging pre-trained YOLOv8 models, I fine-tuned them on a custom dataset for better accuracy.  

---

## Problem Statement  
Object detection is a challenging computer vision task due to variations in:  
- Object size and orientation  
- Lighting conditions  
- Occlusions and background clutter  

The problem addressed in this project was:  
 **Can we train YOLOv8 on a custom dataset of cows and related classes to accurately detect and localize them in images?**

---

##  Objectives  
- Understand and implement a **complete object detection pipeline** in Google Colab.  
- Train YOLOv8 models (`nano`, `small`, `medium`, `large`) on a custom dataset.  
- Compare model performance (Precision, Recall, mAP).  
- Visualize predictions vs. ground truth.  
- Conclude with the **best performing model**.  

---

##  Dataset  
- Source: Custom dataset of cows (and related classes).  
- Images + YOLO format labels (`.txt`).  
- Split into **train (85%)** and **validation (15%)**.  

 **Note**: The dataset is too large to upload directly to GitHub.  
Instead, it was stored and accessed via **Google Drive** in Colab.  

---

##  Technologies Used  
- **Python**  
- **Google Colab (with GPU: Tesla T4)**  
- **YOLOv8 (Ultralytics)**  
- **OpenCV** (for image handling)  
- **Matplotlib** (for visualization)  
- **NumPy**  

---

##  Steps Implemented  

1. **Environment Setup**  
   - Mounted Google Drive  
   - Installed Ultralytics YOLOv8 library  

2. **Data Preparation**  
   - Verified matching image-label pairs  
   - Train/Validation split  
   - Created `data.yaml` for YOLO  

3. **Model Training**  
   - Trained multiple YOLOv8 variants:  
     - `YOLOv8n` (Nano)  
     - `YOLOv8s` (Small)  
     - `YOLOv8m` (Medium)  
     - `YOLOv8l` (Large)  
   - Config:  
     - Epochs = 10  
     - Image size = 416  
     - Batch size = 8  

4. **Evaluation & Visualization**  
   - Compared predictions from each model  
   - Plotted bounding boxes for **ground truth vs. predictions**  

5. **Model Comparison**  
   - Evaluated **Precision, Recall, mAP50, mAP50-95**  
   - Best Model → **YOLOv8s** with `mAP50-95 = 0.319`  

---

## Results  

| Model     | Precision | Recall | mAP50 | mAP50-95 |
|-----------|-----------|--------|-------|----------|
| YOLOv8s   | 0.534     | 0.476  | 0.533 | **0.319** |
| YOLOv8m   | 0.640     | 0.428  | 0.494 | 0.306 |
| YOLOv8l   | 0.200     | 0.264  | 0.228 | 0.149 |

 **YOLOv8s (Small)** performed best, balancing speed and accuracy.  

---

##  Conclusion  
- Successfully implemented an **end-to-end object detection pipeline**.  
- Learned how to prepare custom datasets for YOLOv8.  
- Trained and compared multiple YOLOv8 models.  
- Found **YOLOv8s** to be the most effective for this dataset.  
- Reinforced understanding of **CNN-based detection models** and practical ML workflows.  

---

##  Future Work  
- Train for **more epochs** and with **larger batch sizes**.  
- Experiment with **data augmentation**.  
- Deploy trained model for **real-time inference** on videos.  
