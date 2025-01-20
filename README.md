# Advanced Image Processing Pipelines for Object Detection

## **Project Overview**
This repository contains advanced image processing pipelines utilizing spatial and morphological filters for real-world applications in computer vision. These pipelines have been designed to solve four distinct problems:

1. **License Plate Detection**
2. **Fingerprint Isolation**
3. **Waste Detection in Natural Environments**
4. **Planet Recognition (e.g., Venus)**

The project showcases the versatility of image processing techniques, including Gaussian filtering, median filtering, Canny edge detection, dilation, and morphological closing, to enhance image quality, reduce noise, and extract relevant features for analysis.

---

## **Techniques and Tools Used**

### **Programming Environment**
- **Python 3.12.7**: Implementation of all pipelines.
- **IDE**: PyCharm for structured development.

### **Libraries**
- **NumPy (v1.26.4)**: Efficient mathematical operations on pixel arrays.
- **Matplotlib (v3.9.2)**: Visualization of processed images and comparisons.
- **OpenCV (v4.10)**: Core library for image loading, manipulation, and morphological operations.

---

## **Pipelines Description**

### **1. License Plate Detection**
This pipeline identifies European-standard license plates in grayscale images. It uses morphological opening and closing operations to preprocess the image, followed by:
- Generating **Standard Deviation Maps (MROI)** for feature extraction.
- **Binarization** and **Radial Filtering** to isolate license plate regions.
- Final detection via contour analysis, considering aspect ratios between 1.5 and 6.

#### **Key Conclusions:**
- The pipeline effectively detects license plates near the image center.
- Optimal results depend on appropriate image quality, contrast, and standard format compliance.

### **2. Fingerprint Isolation**
This pipeline isolates fingerprints from noisy grayscale images for feature extraction. Steps include:
- **Median Filtering**: Removes salt-and-pepper noise while preserving edges.
- **Morphological Erosion**: Refines the fingerprint by removing small imperfections.
- **Histogram Equalization**: Enhances contrast for better thresholding.
- **Otsu Binarization**: Generates a binary image to isolate the fingerprint.
- **Contour Filtering**: Extracts and highlights key fingerprint regions.

#### **Key Conclusions:**
- Works best when the image contains a single, centrally located fingerprint.
- Eliminates noise and enhances clarity for feature extraction.

### **3. Waste Detection in Natural Environments**
This pipeline identifies objects (e.g., bottles, cans) with prominent colors in outdoor images. Steps include:
- **Color Filtering**: Isolates objects based on HSV color ranges.
- **Gaussian Smoothing**: Reduces noise to improve edge detection.
- **Canny Edge Detection**: Identifies object boundaries.
- **Morphological Closing**: Unites fragmented edges for cohesive object outlines.
- **Contour Analysis**: Detects and marks waste objects in the image.

#### **Key Conclusions:**
- Effective when the waste object has a distinct color compared to the background.
- Struggles in environments where the object’s color blends with surroundings.

### **4. Planet Recognition**
This pipeline classifies planets based on their color and shape, with a focus on detecting Venus. Steps include:
- **Noise Addition (Salt and Pepper)**: Simulates real-world imperfections.
- **Median Filtering**: Removes noise without distorting planetary edges.
- **Grayscale Conversion and Edge Detection**: Highlights planetary contours.
- **Contour Analysis**: Segments the largest region corresponding to the planet.
- **Color Extraction**: Determines the dominant color for classification.

#### **Key Conclusions:**
- Venus is identified based on its dominant hue (12–20 in HSV).
- The system is robust to noise and adaptable to other planets with simple adjustments.

---

## **How to Run**
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/image-processing-pipelines.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the individual pipelines in the provided notebook or scripts:
   ```bash
   python pipeline_name.py
   ```

---

## **Future Work**
- Extend the pipelines to handle more complex and diverse datasets.
- Optimize computational performance for real-time applications.
- Incorporate machine learning models for feature extraction and classification.

---

## **Authors**
- Araceli Ruiz Vallecillo
- Fernando Jesús Fuentes Carrasco
- Javier Jordán Luque
- Teodoro Hidalgo Guerrero

---

## **References**
- [Car License Plate Detection Dataset](https://www.kaggle.com/datasets/andrewmvd/car-plate-detection)
- [Solar System Planets Dataset](https://www.kaggle.com/datasets/fernandosanfielreyes/solar-system-planets)
- Kim, T., & Kim, E. (2017). A Vehicle License Plate Recognition System Using Morphological ROI Map. *Journal of Physics: Conference Series, 806(1), 012004*. [https://doi.org/10.1088/1742-6596/806/1/012004](https://doi.org/10.1088/1742-6596/806/1/012004)
