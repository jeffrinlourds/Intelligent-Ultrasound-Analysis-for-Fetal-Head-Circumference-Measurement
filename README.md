FETAL HEAD CIRCUMFERENCE MEASUREMENT USING DEEP LEARNING

OVERVIEW
This project presents an AI-based system for automatic fetal head circumference (HC) measurement from ultrasound images. It combines deep learning-based segmentation models with geometric analysis to provide accurate and consistent biometric measurements.

The project:

Uses multiple segmentation models trained in Jupyter Notebooks
Compares their performance
Uses the best-performing proposed model in a frontend application (app.py)

OBJECTIVES

Segment fetal head region from ultrasound images
Automatically compute head circumference
Compare multiple deep learning models
Deploy the best model for real-time inference

DATASET
Dataset: HC18 Grand Challenge Dataset

2D fetal ultrasound images with annotations
Used for segmentation and circumference evaluation

Link: https://hc18.grand-challenge.org/

METHODOLOGY

PREPROCESSING
Image resizing (e.g., 256×256)
Normalization
Data augmentation (flip, rotation, scaling)
SEGMENTATION MODELS (NOTEBOOK-BASED)
Implemented models:
U-Net
UNet++
Attention U-Net
SegNet
DeepLabV3+
Proposed Hybrid Model (U-Net + Transformer Encoder)

All models are implemented in the "notebooks/" folder.

POST-PROCESSING
Convert predicted mask to contour
Apply ellipse fitting
CIRCUMFERENCE CALCULATION
C ≈ π [ 3(a + b) − sqrt((3a + b)(a + 3b)) ]

Where:
a = semi-major axis
b = semi-minor axis

BEST MODEL (PROPOSED)

Hybrid U-Net + Transformer Encoder (MiT-B2 inspired)
Achieves:
~99% segmentation accuracy
~98.5% IoU
Saved model is used in app.py for inference

PROJECT STRUCTURE

Fetal-Head-Circumference-Measurements/

notebooks/ -> Training and experimentation notebooks
models/ -> Saved trained models
app.py -> Frontend application (inference)
utils/ -> Helper functions
results/ -> Output predictions and visualizations
README.md

INSTALLATION

git clone https://github.com/Jimlan7/Fetal-Head-Circumference-Measurements.git

cd Fetal-Head-Circumference-Measurements
pip install -r requirements.txt

USAGE

Run the application:

python app.py

Steps:

Upload an ultrasound image
Model performs segmentation
Displays segmented head and estimated circumference

EVALUATION METRICS

Dice Coefficient
IoU (Intersection over Union)
Accuracy
Mean Absolute Error (HC measurement)

KEY FEATURES

Multiple model comparison (Notebook-based workflow)
Transformer-enhanced segmentation
Real-time inference via frontend
Fully automated HC measurement

FUTURE IMPROVEMENTS

Real-time ultrasound video processing
Multi-task learning (HC + BPD + OFD)
Mobile/web deployment
Clinical validation

AUTHOR
Jeffrin Lourds
Deep Learning | Medical Imaging | Computer Vision

LICENSE
This project is licensed under the MIT License
