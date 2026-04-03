# 🧑‍💻 Face Detection & Recognition Toolkit (Google Colab)

This repository contains a collection of Python scripts designed to teach and demonstrate the core concepts of computer vision, face detection, and facial recognition. 

All scripts are specifically optimized to run in **Google Colab**, utilizing cloud-friendly file handling, automatic dataset generation, and visual outputs via `matplotlib`.

## 🚀 Projects Included

### 1. Basic Face Detection (OpenCV)
A foundational script that introduces object detection. It uses OpenCV's pre-trained Haar Cascade classifiers to locate human faces within a single uploaded image and draw bounding boxes around them. 
* **Key Concept:** Object detection vs. recognition.
* **Libraries:** `cv2`, `matplotlib`.

### 2. Auto-Dataset Builder & LBPH Face Recognizer
A complete end-to-end machine learning pipeline. Instead of manually downloading datasets, this script acts autonomously:
* **Scraping:** Uses `urllib` with custom headers to securely download public domain celebrity images (e.g., Salman Khan) from Wikimedia Commons.
* **Preprocessing:** Automatically detects and crops the faces from the downloaded images to create a structured training dataset.
* **Training:** Trains a Local Binary Patterns Histograms (LBPH) model on the generated dataset.
* **Testing:** Downloads a completely unseen image and identifies the person with a confidence score.
* **Libraries:** `cv2`, `numpy`, `urllib`, `time`.

### 3. Smartphone Face Unlock Simulation
A high-accuracy script simulating how modern smartphones (like Face ID) register and authenticate users. Unlike LBPH, this uses deep learning to map 128 unique points on a face.
* **Phase 1 (Registration):** Upload an "Owner" image to extract and save the 128-dimensional mathematical blueprint.
* **Phase 2 (Authentication):** Upload a "Test" image. The system compares it to the owner's blueprint and visually outputs `UNLOCKED - Welcome!` (Green) or `LOCKED - Unknown` (Red).
* **Libraries:** `face_recognition`, `cv2`, `google.colab`.


## 📋 Prerequisites & Installation

Since these scripts are designed for Google Colab, you do not need to set up a local Python environment. However, you must install the required deep learning library within your Colab notebook before running the Face Unlock simulation.

Create a code cell at the top of your notebook and run:
```bash
!pip install face_recognition opencv-python
