# YOLOv8 for Disease Detection in Medicinal Plants

This project presents a scalable, end-to-end computer vision pipeline for the automated detection of common diseases in high-value medicinal plants. Using the state-of-the-art YOLOv8 object detection model, this work serves as a proof-of-concept for creating a low-cost, efficient tool to help farmers and researchers monitor crop health and ensure the quality of therapeutic herbs.

This project was developed as part of my AI/ML internship at IIIT Hyderabad, in collaboration with a colleague. My work focused on the Ashwagandha plant, while my colleague's work focused on Tulsi, demonstrating the framework's adaptability.

## Table of Contents
- [Project Overview](#project-overview)
- [Key Features](#key-features)
- [Methodology](#methodology)
  - [1. Dataset Creation](#1-dataset-creation)
  - [2. Annotation](#2-annotation)
  - [3. Model Training](#3-model-training)
- [Results & Performance (Ashwagandha Case Study)](#results--performance-ashwagandha-case-study)
- [How to Use This Project](#how-to-use-this-project)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running Inference](#running-inference)
- [Future Work](#future-work)

## Project Overview

Medicinal plants like Ashwagandha and Tulsi are cornerstones of traditional medicine and a significant source of income for many farmers. However, these crops are susceptible to diseases such as leaf spot and powdery mildew, which can drastically reduce yield and compromise the quality of the final product. Manual inspection is labor-intensive and requires expertise. This project leverages YOLOv8 to automate the identification and localization of disease symptoms, enabling early intervention.

## Key Features

- **Scalable Framework:** A methodology applicable to various types of medicinal plants, not just a single species.
- **Custom Datasets:** Unique, manually annotated datasets were created for multiple plants, including Ashwagandha.
- **Multi-Class Disease Detection:** The model for the Ashwagandha case study was trained to identify four distinct plant health states:
  - `healthy_leaf`
  - `leaf_spot`
  - `powdery_mildew`
  - `root_rot` (visible symptoms)
- **End-to-End Pipeline:** Demonstrates the complete workflow from raw image collection to a trained, predictive model ready for inference.

## Methodology

The project followed a standard machine learning pipeline for object detection, applied here to the Ashwagandha plant.

### 1. Dataset Creation

- **Data Sourcing:** A custom dataset of 100 images of Ashwagandha plants was collected, showcasing both healthy specimens and those with various disease symptoms.
- **Data Split:** The dataset was partitioned into a training set (80 images) and a validation set (20 images) for robust model evaluation.
- **Folder Structure:** Data was organized into the standard YOLOv8 format (`images`/`labels` folders for `train`/`val` splits).

### 2. Annotation

- **Tool:** All 100 images were manually annotated using **LabelImg**.
- **Strategy:** To train a fine-grained detector, bounding boxes were drawn around the specific visual symptoms of each disease (e.g., the spots, the mildew patches) rather than the entire leaf. This encourages the model to learn the precise features of each condition.
- **Output:** Annotations were saved in the YOLO `.txt` format.

### 3. Model Training

- **Model:** YOLOv8s ('small') was selected to balance strong performance with efficient training.
- **Environment:** The model was trained for **30 epochs** on a CPU using PyTorch and the Ultralytics framework.
- **Configuration:** A `ashwagandha_config.yaml` file was created to define all dataset paths and class names.

## Results & Performance (Ashwagandha Case Study)

The training was successful, proving the viability of the pipeline. The final model achieved an overall **mAP50 of 40.3%** on the validation set.

### Key Performance Highlights:

- **High Accuracy on Distinct Diseases:** The model performed exceptionally well on `powdery_mildew`, achieving an **mAP50 of 86.9%**. This demonstrates the model's strength in learning diseases with clear, consistent visual patterns.
- **Identified Challenges:** Performance was lower on classes with subtle features and fewer examples, such as `leaf_spot`. This is a classic and expected result for a proof-of-concept with a limited dataset, highlighting the need for more data.
- **Actionable Insights:** The results validate the methodology and provide a clear roadmap for improvement: significantly expanding the dataset, especially for underperforming classes, will be key to developing a production-ready model.

### Example Predictions:

*(Here, you should insert one of your best result images, like `val_batch0_pred.jpg`. Upload it to your GitHub repo and then link it here.)*

![Example Predictions on Ashwagandha](path/to/your/prediction_image.jpg)

This image shows the model successfully identifying `powdery_mildew` and other classes on the validation set.

## How to Use This Project

### Prerequisites

- Python 3.9+
- [Anaconda](https://www.anaconda.com/products/distribution) or Miniconda
- Git

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/KambhampatiAdvaith/your-repo-name.git
   cd your-repo-name
