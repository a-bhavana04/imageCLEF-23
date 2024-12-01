# ImageCLEF 2023: Quality Control of Synthetic Medical Images via GANs

## Overview
This project addresses the **ImageCLEF 2023 Medical Task** of identifying the "fingerprints" of real images in synthetic biomedical images created by GANs. The objective is to classify synthetic images based on whether they were derived from specific real images and assess the relationship between real and synthetic datasets.

---

## Features
- **Dataset Analysis**: Analysis of real and synthetic lung CT images to detect fingerprints.
- **Model Implementations**:
  - **CNN Model**: Classifies images as "used" or "unused" in GAN training.
  - **SIFT + KNN Model**: Uses keypoint detection and feature matching for classification.
  - **Image Hashing**: Perceptual hashing (pHash) for mapping real images to synthetic counterparts.
- **Performance Metrics**: Evaluates models on F1 score, precision, recall, and accuracy.

---

## Dataset
- **Source**: Lung CT axial slices of 256×256 pixels.
- **Composition**:
  - 500 synthetic images.
  - 160 real images (used and unused for GAN training).
  - Test dataset with 10,000 synthetic and 200 real images.

---

## Dependencies
- Python 3.x
- Libraries:
  - `torch` (PyTorch for deep learning models)
  - `opencv-python` (Image processing and feature extraction)
  - `numpy` (Data manipulation)
  - `imagehash` (Hashing techniques)
  - `matplotlib` (Visualization)

Install dependencies using:

```bash
pip install torch opencv-python numpy imagehash matplotlib
```

---

## How to Use
1. **Load the Notebook**: Open the provided `.ipynb` file in Jupyter Notebook or an equivalent environment.
2. **Prepare Dataset**: Ensure the dataset is formatted and placed in the designated directories.
3. **Run Models**:
   - **CNN**: Preprocess images, train the CNN, and evaluate predictions.
   - **SIFT + KNN**: Extract keypoints using SIFT and classify using KNN.
   - **Hashing**: Compute image hashes and evaluate similarity using Hamming distance.
4. **Evaluate Results**: Use provided scripts to compute metrics and visualize results.

---

## Outputs
- **Model Metrics**: Accuracy, F1 score, precision, recall, specificity.
- **Image Mapping**: Pairs of real and synthetic images identified via hashing.

---

## Results
| Model      | Accuracy | Precision | Specificity | Recall | F1 Score |
|------------|----------|-----------|-------------|--------|----------|
| CNN        | 0.535    | 0.544     | 0.64        | 0.43   | 0.4804   |
| SIFT + KNN | 0.61     | 0.512     | 0.6         | 0.4    | 0.449    |

---

## System Requirements
- **Hardware**: NVIDIA GEFORCE RTX GPU, Intel processor (3.9GHz), 32GB RAM.
- **Environment**: Python 3.x with required libraries installed.

---

## Future Work
- Improve classification accuracy using one-shot or few-shot learning.
- Explore additional GAN architectures for synthetic data generation.
