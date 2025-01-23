# Hand Segmentation and Background Removal with DeepLabV3+ and ResNet-101

This repository demonstrates a computer vision pipeline for segmenting hands from images and removing their backgrounds using a U-Net and DeepLabV3+ architecture. The project integrates a Jupyter Notebook for training and evaluation and a Streamlit application for real-time testing and visualization.

## Features

- **Deep Learning Models**: Utilizes DeepLabV3+ with ResNet-101 as the backbone for precise hand segmentation.
- **Data Preprocessing**: Includes resizing, normalization, and mask binarization.
- **Post-processing**: Improves mask quality with dilation and erosion for refined results.
- **Interactive Streamlit App**: Upload images to visualize segmentation results and background removal in real-time.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
  - [Jupyter Notebook](#jupyter-notebook)
  - [Streamlit Application](#streamlit-application)
- [Model Training](#model-training)
- [Streamlit Application Workflow](#streamlit-application-workflow)
- [Results](#results)
- [Future Improvements](#future-improvements)
- [Acknowledgments](#acknowledgments)

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/migueleven/hands_background_removal.git
   cd hand-segmentation-app
   ```

2. Set up the Python environment:
   ```bash
   conda create -n hand_segmentation python=3.10 -y
   conda activate hand_segmentation
   pip install -r requirements.txt
   ```

---

## Usage

### Jupyter Notebook

1. Run all the notebooks in order

### Streamlit Application
0. Run all notebooks to save the models before running the streamlit app
1. Start the Streamlit app:
   ```bash
   streamlit run app.py
   ```
2. Upload an image of a hand and view the processed output with the background removed.

---

## Model Training

The model is trained on a dataset of hand images with corresponding segmentation masks. The architecture used is DeepLabV3+ with ResNet-101. Key configurations include:

- **Optimizer**: Adam
- **Loss Function**: Binary Cross-Entropy with Logits
- **Data Augmentation**: Random flips, rotations, and color shifts
- **Metrics**: Intersection over Union (IoU) and accuracy

---

## Streamlit Application Workflow

1. Load the pre-trained model from `best_model_resnet101.pth`.
2. Preprocess uploaded images (resize, normalize).
3. Predict the mask using the DeepLabV3+ model.
4. Post-process the mask with morphological operations (dilation, erosion).
5. Overlay the mask on the original image to remove the background.

---

## Results

### Examples

#### Input vs. Predicted Output
| Original Image | Predicted Mask | Background Removed |
|----------------|----------------|---------------------|
| ![Captura de pantalla 2025-01-23 201951](https://github.com/user-attachments/assets/db1189d0-c503-4e6e-b406-f0a0c2b83219) | ![Captura de pantalla 2025-01-23 202012](https://github.com/user-attachments/assets/0c76ceec-a351-4710-9eee-be709dcb0f53) | ![Captura de pantalla 2025-01-23 202037](https://github.com/user-attachments/assets/17c5d3ae-aaa9-422b-9c77-bccaa74897ad) |

---

## Future Improvements

- Extend dataset for better generalization.
- Explore lightweight models for faster inference.

---
