# STA2453: Fish Detection and Analysis  

This repository contains the code and data for the **STA2453 project**, which focuses on **fish detection using YOLO**. The project involves **exploratory data analysis (EDA), dataset verification, and model selection** to optimize object detection performance in underwater environments.

---

## 📁 Repository Structure

```text
STA2453/
├── data_analysis/              # Jupyter Notebooks for data exploration
│   ├── EDA.ipynb
│   ├── check_dataset.ipynb
│   └── model_selection.ipynb

├── model/                      # YOLOv8 trained model and outputs
│   ├── yolov8n.pt
│   └── output/
│       └── fish_count_small_subset_batch16/

├── reports/                    # All reports and associated figures
│   ├── Ziyu_Xu_Caroline_Proposal.pdf
│   ├── Ziyu_Xu_Caroline_EDA.pdf
│   ├── STA2453_Progress_Report.pdf
│   ├── STA2453_Final_Report.pdf
│   └── output_images/          # The images have been used in those reports

├── src/                        # Data, annotations, and config
│   ├── cfc_channel_test/       # Original test images
│   ├── yolo_images/            # Subset of training and validating images
│   ├── yaml_file/              # YOLOv8 config files
│   ├── cfc_channel_test.json / .cache
│   ├── cfc_train.json / .cache
│   ├── train_small_subset.json
│   └── subset_selection.ipynb  # Subset generation logic

├── README.md                   # This file
```
---

## 📝 Dataset Notes

The original training dataset is too large to upload to GitHub.  
Only selected subsets are included in this repository:

- `yolo_images/`: sampled training and testing images and labels
- `cfc_channel_test/`: original test images  
- Annotation JSON and cache files are located in the `src/` directory  
- Subset selection and filtering process is documented in `subset_selection.ipynb`

---

## 📌 Project Overview

This project explores the application of YOLOv8 to detect and count fish in underwater images, using a domain adaptation task from the Caltech Fish Counting (CFC) Dataset. The main objective is to train a model on data from one location (Kenai Left Bank) and evaluate its generalization ability on a different domain (Kenai Channel), where visual conditions like lighting, background complexity, and fish appearance may vary significantly.

Key challenges in this project include:
- Detecting extremely small fish (many with bounding boxes occupying <1% of the image area)
- Handling complex and noisy underwater backgrounds with bubbles, plants, and shadows
- Managing domain shifts between source and target environments

To address these challenges, we conducted extensive data analysis on object size, background texture, and image complexity. Based on these insights, YOLOv8 was selected for its balance of speed and performance in small-object detection.

---

### 🔧 Techniques & Strategies Used:
- **Input Resolutions**: Comparison between 512×512 and 1024×1024 to capture finer detail
- **Batch Sizes**: Tested 4, 8, and 16 to optimize learning stability and accuracy
- **Data Augmentation**: Used techniques like Mosaic, Mixup, Copy-Paste, and Erasing to improve generalization

---

### ✅ Results Summary:
- Best configuration achieved **mAP@50 = 0.59**, **Precision = 0.73**, and **Recall = 0.53**
- Larger batch sizes and Mixup augmentation were most effective in improving recall
- High-resolution inputs (1024×1024) improved small object detection, at the cost of training speed

---

### 🎯 Conclusion:
This project demonstrates the effectiveness of YOLOv8 in handling small-object detection and domain adaptation tasks. It also highlights the importance of detailed data analysis, augmentation, and model tuning. The trained model can serve as a strong baseline for real-world scientific applications such as wildlife monitoring using sonar or underwater imaging.



