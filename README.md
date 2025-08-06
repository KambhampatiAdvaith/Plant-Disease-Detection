# Plant Disease Detection Framework using YOLOv11

![App Screenshot]("<img width="1919" height="861" alt="image" src="https://github.com/user-attachments/assets/645ad80a-f01c-42fa-9da8-e781547365a6" />")

This repository contains a complete, end-to-end framework for identifying diseases in medicinal plants using a custom-trained **YOLOv11** object detection model. The project features an interactive **Streamlit** dashboard that allows for both live diagnosis via webcam and detailed report generation from uploaded images.

The framework is designed to be plant-agnostic and its effectiveness has been demonstrated through an initial case study on **Ashwagandha**. This project showcases a full MLOps lifecycle, from data creation to a user-facing application.

**Developed by:** [Shresth Agarwal](https://github.com/Shresth-Agarwal) and [K Advaith](https://github.com/KambhampatiAdvaith)

---

## ✨ Key Features

- **Plant-Agnostic Framework:** The methodology is designed to be easily adapted to detect diseases in any plant species.
- **Interactive Web Dashboard:** A user-friendly interface built with **Streamlit** supporting two powerful modes:
    - **📁 Image Upload & Report:** Analyze a static image to get a full diagnostic report in HTML and PDF formats.
    - **📹 Live Webcam Detection:** Perform real-time disease detection using a live camera feed, a key add-on feature.
- **Professional Report Generation:** Automatically generates detailed reports including the annotated image, detected conditions, confidence levels, and practical care tips.
- **Custom Model Training:** The project was built on a custom-annotated dataset, demonstrating the full workflow from scratch.

---

## 🚀 Getting Started: How to Clone and Run This Project

Follow these steps precisely to get the application running on your local machine.

### Prerequisites
- **Git** installed on your system.
- **Anaconda or Miniconda** installed to manage the Python environment.

### Step 1: Clone the Repository
Open your terminal or command prompt and run the following commands to clone the project and navigate into the directory:
```bash
git clone https://github.com/Shresth-Agarwal/Plant-Disease-Detection.git
cd Plant-Disease-Detection
