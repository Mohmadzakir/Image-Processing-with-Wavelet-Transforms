# 📷 Image Processing with Wavelet Transforms

## 📌 Project Overview
This project implements and evaluates **image processing techniques**, including:
- **Image reading & visualization**
- **Wavelet-based decomposition & reconstruction**
- **Image denoising using wavelet transforms**  
The study leverages **wavelet transforms**, particularly the **Haar wavelet**, for efficient image representation and noise reduction. Performance is assessed using **Mean Squared Error (MSE)** and **Structural Similarity Index (SSIM)**.

## 📊 Dataset & Input Format
- The input images are in **Portable Gray Map (PGM)** format.
- Both **ASCII (P2)** and **binary (P5)** formats are supported.
- Example image: **Boat.pgm** (used for testing).

## 🏗 Methodology

### 1️⃣ **Image Reading & Display**
- A **custom image reader** processes **PGM (P2/P5)** files.
- Ensures robust **error handling** for missing files & invalid formats.
- **Displays grayscale images** using Matplotlib.

### 2️⃣ **Wavelet Decomposition & Reconstruction**
- **3-level Haar wavelet decomposition** extracts low & high-frequency components.
- **Inverse Discrete Wavelet Transform (IDWT)** reconstructs the image.
- Validation: **MSE should be close to zero** if reconstruction is lossless.

### 3️⃣ **Image Denoising**
- **Wavelet-based denoising** with soft/hard thresholding.
- Compared against:
  - **Mean filtering**
  - **Median filtering**
  - **VisuShrink & BayesShrink wavelet methods**
- **Evaluation Metrics**:
  - **MSE (Mean Squared Error)**
  - **SSIM (Structural Similarity Index)**

## 📈 Results

### 🔹 **Wavelet Transform Accuracy**
| **Metric** | **Value** |
|------------|----------|
| **MSE (Reconstruction)** | **0.000** ✅ |
| **SSIM (Reconstruction)** | **1.000** ✅ |

### 🔹 **Denoising Performance**
| **Method** | **MSE** | **SSIM** |
|------------|--------|---------|
| **Wavelet Denoising** | 16558.42 ❌ | 0.00037 ❌ |
| **Mean Filter** | 0.256 ⚠️ | 0.0035 ⚠️ |
| **Median Filter** | **0.003 ✅** | **0.811 ✅** |

- **Wavelet thresholding performed poorly due to suboptimal tuning.**
- **Median filter provided the best balance of noise reduction & detail preservation.**
- **Future work**: Optimize wavelet denoising with adaptive thresholding.
