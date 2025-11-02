# 🔥 Fire Extinguisher Detection

This repository contains an end-to-end computer vision project to detect fire extinguishers using a YOLOv8 object detection model.

---

## 🚀 Demo Result

Here is the final model successfully identifying fire extinguishers in a test image it had never seen before.

![test_image](https://github.com/user-attachments/assets/403bf1d8-b913-4279-9160-65a6b3979052)

---

## 📖 Project Overview

The task was to build a complete pipeline to detect fire extinguishers on campus. The final deliverable is an object detection model trained on a custom dataset.

### Deliverables Checklist
- [x] **Custom Dataset:** A collection of 105 original images of fire extinguishers.
- [x] **Preprocessing Pipeline:** Augmentations applied via Roboflow to create a robust dataset.
- [x] **Model Training Notebook:** A Google Colab notebook (`notebooks/Fire_extinguisher_detector.ipynb`) showing the entire process.
- [x] **Evaluation Report:** Metrics and graphs showing the model's high performance.
- [x] **Inference Demo:** The model successfully running on a new, unseen test image.

---

## 📦 Dataset & Preprocessing

The foundation of this project is a custom dataset collected from my hostel and surrounding campus areas.

* **Data Collection:** I manually collected **105 images** using a smartphone, ensuring variations in lighting, angle, occlusion, and distance as specified in the task.
* **Annotation:** All images were manually annotated with bounding boxes using **Roboflow**.
* **Preprocessing & Augmentation:** To make the model more robust, I applied the following augmentations to generate a final dataset of 270 images:
    * **Split:** 80% Train, 10% Valid, 10% Test
    * **Flip:** Horizontal
    * **Rotate:** $\pm 15^{\circ}$
    * **Brightness:** $\pm 25\%$

> **[Link to Public Roboflow Dataset](https://universe.roboflow.com/tanren/fire-extinguisher-detector-zd4m1)**

---

## 🤖 Model & Training

### Model
I used **YOLOv8n** (the "nano" version) by Ultrallitics. I chose this model because it offers an excellent balance of high speed and strong accuracy, making it perfect for potential real-time applications. The model was fine-tuned on the custom dataset for **50 epochs**.

### Training Environment
* **Platform:** Google Colab
* **Hardware:** T4 GPU

---

## 📊 Evaluation Report

The model trained successfully and achieved excellent performance metrics on the validation dataset.

The final **mAP50-95 score of 0.743** shows that the model is highly accurate and confident in its predictions.

<img width="2400" height="1200" alt="results" src="https://github.com/user-attachments/assets/5e699d69-af9c-4ea4-bb62-7a4683b680cf" />

* **mAP50-95 (Primary Metric):** **0.743**
* **Precision:** **0.992** (When it predicts an extinguisher, it's 99.2% correct)
* **Recall:** **0.917** (It found 91.7% of all extinguishers)

---

## ⚙️ How to Run
All code for training and inference is contained in the `notebooks/Fire_extinguisher_detector.ipynb` notebook.

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/sanjayy-j/Fire-extinguisher-detector](https://github.com/sanjayy-j/Fire-extinguisher-detector)
    ```
2.  **Open the notebook** in Google Colab.
3.  **Run the cells** from top to bottom. The notebook handles all dependencies, data downloads, training, and inference.
