# 📝 OCR Pipeline — Skew Detection, Deskewing & Text Extraction

## 📌 Overview
This project explores a complete OCR workflow involving **skew detection**, **deskewing**, and **text extraction** from scanned or photographed document images.  
The notebook demonstrates how different preprocessing strategies affect OCR performance and evaluates them across multiple document samples.  
All experimentation, visuals, and results are detailed in the accompanying notebook (`OCR.pdf`).  

---

## 🚀 What This Project Does

### **1. Image Preprocessing**
- Converted images to grayscale and applied threshold-based binarization.
- Computed negative images to better isolate text components.

### **2. Connected Components Analysis**
Extracted connected components to identify potential text pixels.  
Tested three strategies to select candidate points:
- **centers** – component centroids  
- **max_y** – lowest pixel in each component  
- **all** – every pixel in every component  

### **3. Skew Angle Estimation**
- Applied **Hough Transform** on selected candidate points.
- Compared detection accuracy and runtime across all strategies.
- Identified **Strategy = max_y** with **threshold = 15** as the most reliable configuration.

### **4. Deskewing**
- Used the computed skew angle to rotate and straighten document images.
- Evaluated improvements in readability and OCR output after deskewing.

### **5. OCR Extraction**
Performed OCR using Tesseract on:
- Original (skewed) images  
- Deskewed images  

Significant improvement was observed in text extraction accuracy after deskewing.

### **6. Extensive Testing**
The pipeline was tested across:
- Multiple document orientations  
- Multiple languages  
- Varying text densities and formats  

Visual comparisons highlight improvements after deskewing.

---

## 🧪 Key Findings Summary
- **Max-Y strategy** gave the most accurate text-line detection.
- **Threshold = 15** worked best for most cases.
- Deskewing noticeably improved OCR accuracy in every tested document.
- Threshold adjustments were required for some challenging cases.

---

## 📂 Repository Structure  
/OCR  
├── notebook.ipynb # Main experimentation notebook  
├── OCR.pdf # PDF export of the notebook  
├── sample_images/ # Test images used in evaluations  
├── outputs/ # Deskewed images, negatives, and visualizations  
└── README.md # Project documentation  

---

## 🛠️ Technologies Used
- Python  
- OpenCV  
- NumPy  
- SciPy  
- Pytesseract (Tesseract OCR)  
- Matplotlib  

---

## 📘 Notebook
The complete workflow, results, visualizations, and OCR comparisons are available inside the main notebook and its PDF export (`OCR.pdf`).

---
