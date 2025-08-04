# 🌿 Medicinal Plant Disease Detection Framework

![App Screenshot](path/to/your/app_screenshot.png)

This repository contains the source code for an end-to-end framework that uses **YOLOv8** to detect diseases in medicinal plants. The project provides a complete, user-friendly solution, including a web-based dashboard for live and image-based diagnosis, and a professional report generation feature.

The effectiveness of this framework has been validated through an initial case study on **Ashwagandha**, a high-value medicinal crop. This project was developed as part of an AI/ML internship at **IIIT Hyderabad**.

**Developed by:** [K Advaith](https://github.com/KambhampatiAdvaith) and [Shresth Agarwal](https://github.com/Shresth-Agarwal)

## ✨ Key Features

- **Plant-Agnostic Framework:** The methodology is designed to be easily adaptable for disease detection in any plant species.
- **Custom Model Training:** Includes a complete workflow for creating a custom dataset, annotating it with **LabelImg**, and training a YOLOv8 model.
- **Interactive Web Dashboard:** A user-friendly interface built with **Streamlit** that supports two modes of operation:
    - **📁 Image Upload:** Analyze a static image for a detailed diagnosis.
    - **📹 Live Webcam Detection:** Perform real-time disease detection using a live camera feed.
- **Professional Report Generation:** Automatically generates detailed diagnostic reports in both **HTML** and **PDF** formats, which include:
    - The annotated image with detection boxes.
    - A summary of detected conditions and their confidence levels.
    - Practical care tips and suggestions for each diagnosed disease.
    - A professional disclaimer for proper usage.

## 📂 Case Study: Plant Disease Detection

To validate the framework, a YOLOv8s model was trained on a custom-annotated dataset of 100 Medicinal plants images. The model was trained to identify four distinct classes: `healthy_leaf`, `leaf_spot`, `powdery_mildew`, and `root_rot` (visible symptoms).

- **Performance:** After 30 epochs, the model achieved a promising **mAP50 of 40.3%**, with exceptional performance on visually distinct diseases like `powdery_mildew` (mAP50 of 86.9%). This result confirms the viability of the framework as a strong proof-of-concept.

![Ashwagandha Results](path/to/your/results_collage.png)

