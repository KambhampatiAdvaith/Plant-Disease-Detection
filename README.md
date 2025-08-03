# A Generalizable Framework for Disease Detection in Medicinal Plants using YOLOv8

This repository presents a complete, end-to-end framework for rapidly developing custom object detection models to identify diseases in various medicinal plants. By leveraging the YOLOv8 architecture, this methodology provides a scalable and low-cost solution for farmers, researchers, and agronomists to automate plant health monitoring.

The effectiveness of this framework has been validated through initial case studies on high-value crops like Ashwagandha and Tulsi.

This project was developed as part of my AI/ML internship at IIIT Hyderabad.

## Table of Contents
- [Project Vision](#project-vision)
- [Framework Features](#framework-features)
- [The 3-Step Methodology](#the-3-step-methodology)
  - [Step 1: Custom Dataset Creation](#step-1-custom-dataset-creation)
  - [Step 2: Model Training](#step-2-model-training)
  - [Step 3: Evaluation & Inference](#step-3-evaluation--inference)
- [Case Study: Ashwagandha Disease Detection](#case-study-ashwagandha-disease-detection)
- [How to Use This Framework for Your Own Plant](#how-to-use-this-framework-for-your-own-plant)
- [Future Work](#future-work)

## Project Vision

The cultivation of medicinal plants is often hampered by diseases that reduce yield and compromise quality. Manual inspection is slow, subjective, and requires expertise. Our vision is to provide a universal, easy-to-implement framework that empowers anyone to build a custom AI model to monitor the health of their specific crops, enabling early intervention and improving agricultural outcomes.

## Framework Features

- **Plant-Agnostic:** The methodology is designed to be applied to any plant species with visually distinct disease symptoms.
- **Rapid Prototyping:** Enables the creation of a functional proof-of-concept detector with as few as 100 images.
- **Fine-Grained Detection:** Capable of learning the subtle visual differences between various diseases (e.g., leaf spot vs. powdery mildew) and healthy tissue.
- **End-to-End Workflow:** Provides a complete roadmap, from raw image collection to a trained, deployable model.

## The 3-Step Methodology

This framework simplifies the complex process of creating a custom detector into three core stages.

### Step 1: Custom Dataset Creation
1.  **Data Sourcing:** Collect images of the target plant, capturing both healthy examples and various disease symptoms.
2.  **Structuring:** Organize images into the standard YOLOv8 format: `images/train`, `images/val`, `labels/train`, and `labels/val`.
3.  **Annotation:** Use a tool like **LabelImg** to draw bounding boxes around the specific visual features of each condition (e.g., the spots, the mildew). Save annotations in YOLO `.txt` format.

### Step 2: Model Training
1.  **Configuration:** Create a `.yaml` file defining the dataset path and a list of class names (e.g., `healthy`, `disease_A`, `disease_B`).
2.  **Training:** Use the Ultralytics CLI to train a YOLOv8 model (e.g., `yolov8s.pt`) on the custom dataset. Data augmentation is recommended to improve generalization.

### Step 3: Evaluation & Inference
1.  **Analysis:** Evaluate the model using the generated performance metrics (mAP, confusion matrix) to understand its strengths and weaknesses.
2.  **Inference:** Use the best-trained model weights (`best.pt`) to make predictions on new, unseen images of the plant.

## Case Study: Plant Diseases Detection

To validate the framework, we applied it to a dataset of 100 Ashwagandha images with four classes (`healthy_leaf`, `leaf_spot`, `powdery_mildew`, `root_rot`).

- **Result:** After just 30 epochs, the model successfully learned to identify the diseases, achieving an overall **mAP50 of 40.3%**.
- **Key Insight:** The model performed exceptionally well on classes with distinct features (`powdery_mildew` mAP50: **86.9%**), demonstrating the framework's effectiveness. It also correctly identified that more data is needed for classes with subtle features (`leaf_spot`), providing actionable insights for future improvement.

## Future Work

The success of this framework opens several avenues for future development:
- **Multi-Plant Model:** Combine the Ashwagandha, Tulsi, and other new datasets to train a single, robust model capable of diagnosing diseases across multiple medicinal plant species.
- **Dataset Expansion:** Significantly enlarge the datasets for each plant to improve accuracy and generalization, particularly for fine-grained disease types.
- **Edge Deployment:** Optimize and deploy the trained models on low-cost edge devices (e.g., Raspberry Pi, Jetson Nano) for real-time, in-field analysis.

Developed by Shresth Agarwal and K Advaith
