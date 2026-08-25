# 🖼️ Image Preprocessing & Enhancement Pipeline

A multi-stage **computer vision preprocessing pipeline** built with **Python, OpenCV, and NumPy**, designed to restore and enhance noisy, low-contrast, or degraded images for downstream computer vision tasks.

---

## 📌 Pipeline Overview

Real-world images captured under low-light or high-ISO conditions can suffer from **noise, blur, and poor dynamic range**. This pipeline systematically improves image quality through a sequential three-stage workflow:

1. **Noise Reduction — Gaussian Denoising**
   Suppresses high-frequency noise while preserving important structural details using a Gaussian kernel.

2. **Contrast Enhancement — CLAHE in LAB Space**
   Converts the image to the **CIE LAB** color space and applies **Contrast Limited Adaptive Histogram Equalization (CLAHE)** exclusively to the **Luminance (L) channel**. This improves local contrast while reducing unwanted color distortion.

3. **Edge Sharpening — Unsharp Masking**
   Enhances fine details and edges by combining the enhanced image with a Gaussian-blurred version using weighted blending.

---

## 🛠️ Tech Stack & Libraries

* **Language:** Python 3
* **Computer Vision:** OpenCV (`cv2`)
* **Scientific Computing:** NumPy
* **Visualization:** Matplotlib
* **Image Processing:** Scikit-Image
* **Environment:** Jupyter Notebook / Google Colab

---

## 🔬 Processing Stages & Technical Specifications

| Stage       | Method            | Configuration / Parameters             | Objective                     |
| :---------- | :---------------- | :------------------------------------- | :---------------------------- |
| **Stage 1** | Gaussian Blur     | Kernel: `(3, 3)`, σ = `1`              | Noise reduction and smoothing |
| **Stage 2** | CLAHE (LAB Space) | `clipLimit=2.0`, `tileGridSize=(8, 8)` | Local contrast enhancement    |
| **Stage 3** | Unsharp Masking   | `1.5 × Enhanced − 0.5 × Blur`          | Edge and texture sharpening   |

---

## 🔄 Processing Pipeline

```text
Original Image
      │
      ▼
┌─────────────────────┐
│  Gaussian Denoising │
│     (3 × 3 Kernel)  │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│   LAB Conversion    │
│       + CLAHE       │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Unsharp Masking    │
│   Edge Sharpening   │
└──────────┬──────────┘
           │
           ▼
     Enhanced Image
```

---

## 📊 Analytical Evaluation

The pipeline includes several methods for evaluating the enhancement results:

### Luminance Histograms

Analyzes pixel intensity distributions **before and after CLAHE enhancement** to evaluate changes in luminance and contrast.

### Multi-Stage Visual Comparison

The pipeline generates a side-by-side comparison of the different processing stages:

```text
Original → Denoised → Enhanced → Final
```

This allows visual inspection of how each processing stage affects image quality.

---

## 🚀 Getting Started

### Prerequisites

Make sure Python 3 is installed on your system.

Install the required dependencies:

```bash
pip install opencv-python numpy matplotlib scikit-image
```

---

## ▶️ Running the Pipeline

### Using Jupyter Notebook

Launch Jupyter Notebook:

```bash
jupyter notebook pipeline_colab_2.ipynb
```

Then open and execute the notebook cells sequentially.

### Using Google Colab

The notebook can also be uploaded to **Google Colab** and executed directly without requiring a local Python environment.

---

## 📂 Project Structure

```text
Image-Preprocessing-Pipeline/
│
├── pipeline_colab_2.ipynb    # Main preprocessing notebook
├── README.md                 # Project documentation
└── requirements.txt          # Python dependencies
```

---

## 🎯 Project Objectives

The main objectives of this project are to:

* Reduce image noise.
* Improve local image contrast.
* Preserve natural color information.
* Enhance edges and fine details.
* Provide a clean preprocessing pipeline for downstream computer vision and machine learning tasks.

---

## 👥 Authors

* **Mohamed Yasser**
* **Yassin Hany**
* **Shahd Mohamed**
* **Merna Hesham**

**Faculty of Information Technology**
**Misr University for Science and Technology (MUST)**

---

## 📌 Technologies Used

```text
Python 3
OpenCV
NumPy
Matplotlib
Scikit-Image
Jupyter Notebook
Google Colab
```
