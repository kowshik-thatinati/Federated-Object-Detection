# Object Detection using Federated Learning

## 📌 Overview
This project focuses on **Object Detection using Federated Learning (FL)**, a privacy-preserving machine learning approach where multiple clients collaboratively train a shared object detection model without sharing raw data. The work is currently **research-oriented**, based on a detailed literature survey and problem analysis, and will be extended to implementation in later stages.

---

## 🎯 Problem Statement
Traditional object detection models rely on centralized datasets, which raises concerns related to **data privacy, security, and regulatory compliance**. In many real-world scenarios, sharing raw visual data is not feasible. This project studies how federated learning can be applied to object detection models to enable collaborative training while keeping data local to each client.

---

## 🚀 Motivation
- Preserve data privacy during training  
- Enable collaborative learning across distributed clients  
- Reduce data-sharing and compliance issues  
- Study performance trade-offs between centralized and federated training  

---

## 🧠 Key Concepts
- Federated Learning  
- Object Detection  
- YOLO (You Only Look Once)  
- Non-IID data distribution  
- Secure model aggregation  
- Communication-efficient training  

---

## 🏗️ System Workflow (High Level)
1. A global object detection model (YOLO-based) is initialized on a central server.
2. The model is distributed to multiple clients.
3. Each client trains the model locally using its private dataset.
4. Only model updates (weights) are sent back to the server.
5. The server aggregates updates using federated algorithms (e.g., FedAvg).
6. The updated global model is redistributed.
7. The process repeats until convergence.

---

## ⚠️ Challenges Addressed
- Non-IID data across clients  
- High communication overhead  
- Model convergence instability  
- Privacy and security risks  
- Real-time inference constraints  

---

## 🛠️ Techniques Used
- Federated optimization (FedAvg, FedOpt, FedAvgM)
- Pretrained YOLO initialization
- Lightweight YOLO architectures
- Secure aggregation of model updates
- Communication reduction strategies

---

## 📊 Evaluation Metrics
- Mean Average Precision (mAP)
- Intersection over Union (IoU)
- Frames Per Second (FPS)

---

## 📌 Current Status
- [x] Topic selection  
- [x] Literature survey (2023–2024)  
- [x] Problem formulation and analysis  
- [x] Report documentation  
- [ ] Federated training simulation  
- [ ] Model evaluation  
- [ ] Performance optimization  

---

## 🧰 Tools & Frameworks
- Python  
- PyTorch  
- YOLO (v5 / v7 / v8)  
- Federated learning simulation setup  

---

## 🔮 Future Work
- Implementation of federated training pipeline  
- Improved aggregation strategies  
- Communication-efficient updates  
- Personalized federated models  
- Robustness and scalability analysis  

---

## 👤 Author
**Kowshik Thatinati**  
B.Tech (Hons.) CSE – Artificial Intelligence  
Keshav Memorial College of Engineering  

---

## 🙏 Acknowledgement
This project is carried out under the guidance of **Prof. [Mentor Name]**,  
Indian Institute of Technology (IIT) Tirupati.
