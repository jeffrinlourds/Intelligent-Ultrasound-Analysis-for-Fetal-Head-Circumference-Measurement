# 🧠 Fetal Head Circumference Measurement using Deep Learning

## 📌 Overview

This project presents an **AI-based system for automatic fetal head circumference (HC) measurement** from ultrasound images. It combines **deep learning-based segmentation models** with **geometric analysis** to provide accurate and consistent biometric measurements.

### 🔍 Key Highlights

* Uses multiple segmentation models trained in **Jupyter Notebooks**
* Compares performance across architectures
* Deploys the **best-performing proposed model** using a frontend application (`app.py`)

---

## 🎯 Objectives

* Segment fetal head region from ultrasound images
* Automatically compute head circumference
* Compare multiple deep learning models
* Deploy the best model for real-time inference

---

## 🧪 Dataset

**Dataset:** HC18 Grand Challenge Dataset

* 2D fetal ultrasound images with annotations
* Used for segmentation and circumference evaluation

🔗 [https://hc18.grand-challenge.org/](https://hc18.grand-challenge.org/)

---

## 🏗️ Methodology

### 🔹 Preprocessing

* Image resizing (e.g., 256×256)
* Normalization
* Data augmentation (flip, rotation, scaling)

### 🔹 Segmentation Models (Notebook-Based)

Implemented models:

* U-Net
* UNet++
* Attention U-Net
* SegNet
* DeepLabV3+
* U-Net+resnet
* **Proposed Hybrid Model (U-Net + Transformer Encoder)**

📁 All models are implemented in the `notebooks/` folder.

---

### 🔹 Post-processing

* Convert predicted mask → contour
* Apply ellipse fitting

---

### 🔹 Circumference Calculation

```
C ≈ π [ 3(a + b) − sqrt((3a + b)(a + 3b)) ]
```

Where:

* `a` = semi-major axis
* `b` = semi-minor axis

---

## 🧠 Best Model (Proposed)

* Hybrid **U-Net + Transformer Encoder (MiT-B2 inspired)**
* Performance:

  * ✅ ~99% Segmentation Accuracy
  * ✅ ~98.5% IoU
* Saved model is used in **`app.py` for inference**

---

## 📁 Project Structure

```
Fetal-Head-Circumference-Measurements/
│── notebooks/        # Training & experimentation notebooks
│── models/           # Saved trained models
│── app.py            # Frontend application (inference)
│── utils/            # Helper functions
│── results/          # Output predictions & visualizations
│── README.md
```

---

## ⚙️ Installation

```bash
git clone https://github.com/Jimlan7/Fetal-Head-Circumference-Measurements.git
cd Fetal-Head-Circumference-Measurements
pip install -r requirements.txt
```

---

## ▶️ Usage

### Run the Application

```bash
python app.py
```

### Steps

1. Upload an ultrasound image
2. Model performs segmentation
3. Displays:

   * Segmented fetal head
   * Estimated circumference

---

## 📊 Evaluation Metrics

* Dice Coefficient
* IoU (Intersection over Union)
* Accuracy
* Mean Absolute Error (HC measurement)

---

## 🚀 Key Features

* 📓 Notebook-based model experimentation
* 🤖 Transformer-enhanced segmentation
* ⚡ Real-time inference via frontend
* 📏 Fully automated HC measurement pipeline

---

## 🔮 Future Improvements

* Real-time ultrasound video processing
* Multi-task learning (HC + BPD + OFD)
* Mobile/web deployment
* Clinical validation

---

## 👨‍💻 Author

**Jeffrin Lourds**
Deep Learning | Medical Imaging | Computer Vision

---

## 📜 License

This project is licensed under the **MIT License**

