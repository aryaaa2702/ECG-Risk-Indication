# ECG Arrhythmia Detection Using HRV Features and Machine Learning

## Overview
This project presents an ECG-based arrhythmia detection pipeline using the MIT-BIH Arrhythmia Dataset. The ECG signals are accessed directly from PhysioNet using the `wfdb` library, preprocessed using signal filtering techniques, and analyzed through R-peak detection and RR interval extraction.

From the RR intervals, heart rate variability (HRV)-based statistical features are extracted and used to train a Random Forest classifier for arrhythmia classification.

The project demonstrates how ECG signal processing and machine learning can be combined to identify rhythm abnormalities from cardiac recordings.

---

## Objective
The main objective of this project is to detect and classify ECG rhythm patterns by:
- preprocessing ECG signals
- detecting R-peaks
- calculating RR intervals
- extracting HRV-based features
- training a machine learning model for classification

---

## Dataset
This project uses the **MIT-BIH Arrhythmia Dataset** from PhysioNet.

**Dataset Source:**  
https://physionet.org/content/mitdb/1.0.0/

### Note
The dataset is accessed directly from PhysioNet using the `wfdb` library, so no local dataset files are stored in this repository.

To run the notebook successfully, an internet connection is required.

---

## Technologies Used
- Python
- NumPy
- Pandas
- Matplotlib
- SciPy
- Scikit-learn
- WFDB
- Joblib
- Seaborn
- Jupyter Notebook

---

## Methodology

### 1. ECG Signal Acquisition
ECG records were loaded from the MIT-BIH Arrhythmia Dataset using the `wfdb` library.

### 2. Signal Preprocessing
A Butterworth bandpass filter (0.5 Hz to 40 Hz) was applied to remove baseline wander and high-frequency noise from the ECG signal.

### 3. R-Peak Detection
R-peaks were detected from the filtered ECG waveform using amplitude thresholding and minimum distance constraints.

### 4. RR Interval Calculation
The time difference between consecutive R-peaks was calculated to obtain RR intervals, which represent beat-to-beat heart rhythm variation.

### 5. Feature Extraction
The following HRV-based statistical features were extracted:
- Mean RR interval
- Standard deviation of RR intervals
- Mean heart rate
- Standard deviation of heart rate

### 6. Classification
A **Random Forest Classifier** was trained using the extracted features to classify ECG rhythm categories.

### 7. Evaluation
The model was evaluated using:
- Classification Report
- Precision
- Recall
- F1-score
- Confusion Matrix
- Feature Importance Analysis

---

## Project Structure

```bash
ECG-Heart-Detection/
│
├── data/
│   ├── raw/
│   ├── processed/
│   └── dataset_info.txt
│
├── notebooks/
│   └── ecg_detection.ipynb
│
├── results/
│   ├── raw_ecg_plot.png
│   ├── rawvsfiltered_ecg_plot.png
│   ├── r_peak_detection.png
│   ├── rr_interval_plot.png
│   ├── confusion_matrix.png
│   ├── feature_importance.png
│   ├── classification_report.txt
│   └── sample_predictions.txt
│
├── models/
│   └── random_forest_model.pkl
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Results
The project successfully demonstrates a complete ECG analysis and classification workflow.

### Key outputs include:
- Raw ECG signal visualization
- Filtered ECG signal
- R-peak detection verification
- RR interval series
- HRV-based feature extraction
- Random Forest classification results
- Confusion matrix
- Feature importance analysis
- Sample ECG record predictions

The model was able to classify ECG records based on extracted rhythm-related features.

---

## How to Run

### 1. Download or clone the project
Download or clone the project folder to your system.

### 2. Install the required libraries
Open terminal / command prompt inside the project folder and run:

```bash
pip install -r requirements.txt
```

### 3. Make sure internet is available
The project uses the **MIT-BIH Arrhythmia Dataset** directly from **PhysioNet** through the `wfdb` library, so an internet connection is required while running the notebook.

### 4. Open Jupyter Notebook
Run:

```bash
jupyter notebook
```

### 5. Open the notebook
Open:

```bash
notebooks/ecg_detection.ipynb
```

---

## Limitations
- The classification was performed at the **record level** rather than the **beat level**, resulting in a relatively small dataset.
- Some arrhythmia classes were underrepresented, which may affect generalization.
- The project uses statistical HRV features rather than deep learning-based waveform learning.

---

## Future Scope
Possible future improvements include:
- Beat-level ECG segmentation for larger sample size
- Use of deep learning models such as **1D CNN** or **CNN-LSTM**
- Improved arrhythmia class balancing
- Real-time ECG monitoring and deployment
- Integration into a web-based or healthcare monitoring system

---

## Conclusion
This project successfully implements an ECG arrhythmia detection pipeline using ECG signal preprocessing, R-peak detection, RR interval analysis, HRV-based feature extraction, and machine learning classification.

It demonstrates the practical application of biomedical signal processing and machine learning in the healthcare domain.

---

## Author
Arya Shrivastava