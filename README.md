# STA2453: Fish Detection and Analysis  

This repository contains the code and data for the **STA2453 project**, which focuses on **fish detection using YOLO**. The project involves **exploratory data analysis (EDA), dataset verification, and model selection** to optimize object detection performance in underwater environments.

---

## 📁 Repository Structure  

- 📜 **check_dataset.ipynb** – Verifies dataset integrity and structure 
- 📜 **EDA.ipynb** – Exploratory Data Analysis (EDA) of the dataset  
- 📜 **model_selection.ipynb** – Find suitable models for fish detection  
- 📜 **model.ipynb** – Main model training and evaluation pipeline (WIP)  
- 📜 **target_yolo_data.yaml** – YOLO configuration for the target dataset  
- 📜 **yolo_data.yaml** – General YOLO configuration file  
- 📜 **README.md** – Project documentation (this file)  

---

## 📊 Project Overview  

This project aims to develop an optimized fish detection model using **YOLO (You Only Look Once)**. The dataset consists of **76,619 images** with **132,010 fish annotations**, and the primary challenges include:
- **Small object detection**: Many fish occupy less than 5% of the image.
- **Background complexity**: High variance in underwater environments.
- **Texture variability**: Strong edge features in some images, making detection difficult.
- **Low fish density**: Average **1.72 fish per image**, minimizing occlusion.

Currently, the focus is on **dataset analysis and preparation** before full model training.

---
