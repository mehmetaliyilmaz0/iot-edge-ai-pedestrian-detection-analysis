# Real-Time Pedestrian Detection on IoT Edge Devices: A Lightweight Deep Learning Approach (Paper Analysis)

This repository contains the academic paper analysis I presented for my **SENG423: Internet of Things** course. The presentation focuses on the critical engineering trade-offs required to optimize and deploy deep learning models on resource-constrained IoT edge devices.

## 📜 Paper Under Review

* **Title:** "Real-Time Pedestrian Detection on IoT Edge Devices: A Lightweight Deep Learning Approach"
* **Authors:** Muhammad Dany Alfikri, Rafael Kaliski
* **Identifier:** arXiv:2409.15740v1

## 🎯 Core Concept & Scope

The presentation analyzes a proposed solution to the high-latency problem of cloud-based processing in safety-critical applications, where real-time responses are crucial and "milliseconds save lives".

The proposed solution is **Edge Computing**, which performs computation locally on an IoT device to ensure minimal delay.

### 💡 The Core Engineering Dilemma
How do you run a model that is simultaneously **FAST**, **ACCURATE**, and **LIGHTWEIGHT** on a resource-constrained IoT device (like an Nvidia Jetson Nano)?

### 🚀 The Paper's Proposed Architecture
The paper proposes a novel, lightweight "Tiny YOLO" model, optimized specifically for edge devices.

The optimization is achieved through two key architectural changes:
1.  **Backbone:** Replaces the standard Darknet-53 backbone with the highly efficient **MobileNetV2** architecture, which is designed for mobile and resource-constrained systems.
2.  **Model Novelty:** Simplifies the architecture by reducing the detection scales from three to **two** and using fewer convolutional layers.

This optimized model runs on the edge device and transmits only lightweight **JSON** data via the **MQTT** protocol, completing the IoT system architecture.

## 📊 Key Findings & Results
The paper's tests demonstrate that the proposed model achieves the best balance of performance metrics, making it the most "fit-for-purpose" solution.

| Model | Accuracy (mAP) | Speed (on Jetson Nano) | Size (Parameters) | RAM Usage (GPU) |
| :--- | :---: | :---: | :---: | :---: |
| **Proposed (Tiny YOLO)** | **78%** | **423 ms** | **7.39 M** | **50.81 MB** |
| Original YOLOv3 | 75% | 610 ms | - | ~312 MB |
| Faster R-CNN | 90% | ~2200 ms (Unusable) | 41.12 M | ~480 MB |

**Key Takeaway:** The proposed model is **5x faster** than the most accurate competitor (Faster R-CNN) and uses approximately **6x less RAM** than the standard YOLOv3. It proves that for real-time safety, the "fittest" model is superior to the "most accurate" but unusable model.

## 🛠️ Technologies & Concepts Discussed
* Internet of Things (IoT)
* Edge Computing
* Deep Learning (CNN)
* Object Detection
* YOLO (You Only Look Once)
* MobileNetV2
* NVIDIA Jetson Nano
* Communication Protocols: MQTT
* Performance Metrics: mAP, FLOPS, FPS, Latency

## 📂 Presentation File
The presentation file (`.pdf` or `.pptx`) can be found in this repository:
[Link to your presentation file, e.g., Mehmet Ali Yılmaz - IoT Course Article Presentation.pdf]
