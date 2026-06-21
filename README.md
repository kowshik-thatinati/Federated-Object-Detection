# Object Detection using Federated Learning

This repository contains the implementation of a **Federated Learning** pipeline for **Object Detection** using the **YOLOv8** deep learning model. The project demonstrates how multiple simulated clients can collaboratively train a shared global model without exchanging raw data, ensuring data privacy and decentralized machine learning.

## 📌 Project Overview
Federated Learning (FL) is an emerging ML paradigm designed to train models across multiple decentralized devices holding local data samples. This project simulates a federated environment where:
- The **COCO128 dataset** is partitioned among multiple clients.
- Each client performs independent local training using **YOLOv8**.
- The server aggregates the learned model weights using the **Federated Averaging (FedAvg)** algorithm.
- A final, improved global model is evaluated against test images to yield high-confidence object detection bounding boxes.

### 🎯 Key Objectives
- Design and implement a privacy-preserving federated framework for object detection.
- Distribute data seamlessly to simulate real-world, localized edge-device training.
- Validate the effectiveness of the **Federated Averaging (FedAvg)** aggregation logic.
- Output visually descriptive detection bounding boxes and statistics.

---

## 🛠️ Technology Stack
| Category | Technology |
|---|---|
| **Core Language** | Python 3 |
| **Deep Learning Framework** | PyTorch |
| **Object Detection Model** | Ultralytics YOLOv8 |
| **Data Processing & Vision** | NumPy, OpenCV, PIL |
| **Visualization** | Matplotlib |
| **Execution Environment** | Google Colab |

---

## 🚀 How to Run

Because this project trains a deep learning model over 20 global rounds, it is highly recommended to run this in **Google Colab**.

1. Download or clone this repository.
2. Open [Google Colab](https://colab.research.google.com/).
3. Upload the `federated_yolov8.ipynb` notebook.
4. Go to **Runtime > Run all**. 
   *(The notebook is fully autonomous and will handle downloading the dataset, splitting it among clients, executing the federated rounds, and visualizing the final output).*

---

## 🧠 Methodology & Architecture

1. **Dataset Preparation & Splitting**: The COCO128 dataset is downloaded and dynamically distributed into isolated directories for `NUM_CLIENTS=2`. Each client generates its own specialized `yaml` configuration.
2. **Model Initialization**: The central server initializes a base `yolov8n.pt` global model.
3. **Federated Training Loop**:
    - **Global Rounds**: 20
    - **Local Epochs**: 10
    - For each round, the server broadcasts the global model's `state_dict` to all clients.
    - Clients train the model on their private datasets.
4. **Federated Averaging**: The `federated_averaging()` function intercepts the trained weights from all clients and computes the mean for every tensor layer, updating the global model for the next round.

---

## 📊 Results and Visualization

Upon completion of the training rounds, the final global model predicts bounding boxes on a subset of test images.

- **Visual Output**: The notebook renders a side-by-side comparison showing the Original Image vs. the Predicted Image with bounding boxes and confidence scores.
- **Statistical Output**: A Bar Chart is generated highlighting the `Detection Count per Image`, alongside text-based summaries of total objects found.

---

## 👨‍💻 Author
**Kowshik Thatinati**  
*Keshav Memorial College of Engineering*  
*Under the Guidance of Dr. Chalavadi Vishnu (IIT Tirupathi)*
