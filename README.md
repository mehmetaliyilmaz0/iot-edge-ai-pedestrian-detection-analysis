# Real-Time Pedestrian Detection on IoT Edge Devices: A Lightweight Deep Learning Approach (Paper Analysis)

This repository contains the academic paper analysis I presented for my **SENG423: Internet of Things** course. The presentation focuses on the critical engineering trade-offs required to optimize and deploy deep learning models on resource-constrained IoT edge devices.

## 📜 Paper Under Review

* [cite_start]**Title:** "Real-Time Pedestrian Detection on IoT Edge Devices: A Lightweight Deep Learning Approach" [cite: 4]
* [cite_start]**Authors:** Muhammad Dany Alfikri, Rafael Kaliski [cite: 1]
* [cite_start]**Identifier:** arXiv:2409.15740v1 [cite: 2]

## 🎯 Core Concept & Scope

[cite_start]The presentation analyzes a proposed solution to the high-latency problem of cloud-based processing in safety-critical applications [cite: 11][cite_start], where real-time responses are crucial and "milliseconds save lives"[cite: 15].

[cite_start]The proposed solution is **Edge Computing**, which performs computation locally on an IoT device [cite: 12] to ensure minimal delay.

### 💡 The Core Engineering Dilemma
[cite_start]How do you run a model that is simultaneously **FAST**, **ACCURATE**, and **LIGHTWEIGHT** on a resource-constrained IoT device (like an Nvidia Jetson Nano)? [cite: 21, 39, 68]

### 🚀 The Paper's Proposed Architecture
The paper proposes a novel, lightweight "Tiny YOLO" model, optimized specifically for edge devices.

The optimization is achieved through two key architectural changes:
1.  [cite_start]**Backbone:** Replaces the standard Darknet-53 backbone with the highly efficient **MobileNetV2** architecture[cite: 49], which is designed for mobile and resource-constrained systems.
2.  [cite_start]**Model Novelty:** Simplifies the architecture by reducing the detection scales from three to **two** [cite: 57] [cite_start]and using fewer convolutional layers[cite: 58].

[cite_start]This optimized model runs on the edge device and transmits only lightweight **JSON** data via the **MQTT** protocol[cite: 44], completing the IoT system architecture.

## 📊 Key Findings & Results
The paper's tests demonstrate that the proposed model achieves the best balance of performance metrics, making it the most "fit-for-purpose" solution.

| Model | Accuracy (mAP) | Speed (on Jetson Nano) | Size (Parameters) | RAM Usage (GPU) |
| :--- | :---: | :---: | :---: | :---: |
| **Proposed (Tiny YOLO)** | [cite_start]**78%** [cite: 110] | [cite_start]**423 ms** [cite: 100] | [cite_start]**7.39 M** [cite: 89] | [cite_start]**50.81 MB** [cite: 120] |
| Original YOLOv3 | [cite_start]75% [cite: 110] | [cite_start]610 ms [cite: 99] | - | [cite_start]~312 MB [cite: 119] |
| Faster R-CNN | [cite_start]90% [cite: 110] | [cite_start]~2200 ms (Unusable) [cite: 97] | [cite_start]41.12 M [cite: 88] | [cite_start]~480 MB [cite: 118] |

[cite_start]**Key Takeaway:** The proposed model is **5x faster** than the most accurate competitor (Faster R-CNN) [cite: 97, 100] [cite_start]and uses approximately **6x less RAM** than the standard YOLOv3[cite: 119, 120]. It proves that for real-time safety, the "fittest" model is superior to the "most accurate" but unusable model.

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
The presentation file (`.pptx`) can be found in this repository:
