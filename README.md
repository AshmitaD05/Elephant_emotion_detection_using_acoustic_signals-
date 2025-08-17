
# 🐘 Elephant Emotion Detection using Acoustic Signals
This project uses **Digital Signal Processing (DSP)** and **Machine Learning (ML)** techniques to detect elephant emotions from acoustic signals.  
The system extracts **MFCC, Chroma, and Mel-spectrogram features** from elephant sounds and classifies emotions using **Random Forest** and **Decision Tree** classifiers.

---
## 🚀 Features
- **FFT implementation (manual)** for frequency analysis
- **Custom high-pass Butterworth filter** for noise removal
- **Feature Extraction**:
  - MFCC (Mel-Frequency Cepstral Coefficients)
  - Chroma features
  - Mel-spectrogram
- **Classification Models**:
  - Random Forest
  - Decision Tree
- **Performance Evaluation**:
  - Confusion Matrix
  - Classification Report

---
## Project Flow

### Input
- The system takes an **elephant sound recording** (`.wav`) as input.
- Example: `inputs/input.wav`

---

### Preprocessing
- **High-pass Butterworth filter** is applied to remove background noise (cutoff = 50 Hz).
- **Manual FFT implementation** is used to analyze the frequency spectrum.
- Original and filtered signals are plotted for visualization.

---

### Feature Extraction
From the preprocessed signal, the following features are extracted using **Librosa**:
- **MFCC** (Mel-Frequency Cepstral Coefficients) → captures timbral characteristics
- **Chroma features** → represent tonal content
- **Mel-Spectrogram** → represents frequency distribution on a mel scale

All extracted features are saved in `audio_features.csv`.

---

### Classification
Two machine learning models are trained using a labeled dataset (`emotion_dataset_3.csv`):
- 🌳 **Random Forest Classifier**
- 🌲 **Decision Tree Classifier**

Training Dataset Format (`emotion_dataset_3.csv`)

### Evaluation
- Models are evaluated using:
  - **Confusion Matrix**
  - **Classification Report** (precision, recall, f1-score, accuracy)

---

### Prediction
- The trained models classify the **input audio file** into an emotion class.

## 📊 Example Results

### Confusion Matrix (Random Forest)
[[1 0 1 0]
[1 1 1 0]
[0 0 3 0]
[0 0 1 1]]

### Classification Report (Random Forest)
-
          precision    recall  f1-score   support

   blast       0.50      0.50      0.50         2
    roar       1.00      0.33      0.50         3
roar_rumble 0.50 1.00 0.67 3
trumpet 1.00 0.50 0.67 2


accuracy                           0.60        10
macro avg 0.75 0.58 0.58 10
weighted avg 0.75 0.60 0.58 10

---

### Confusion Matrix (Decision Tree)
[[1 0 1 0]
[1 1 1 0]
[0 0 3 0]
[0 0 1 1]]


### Classification Report (Decision Tree)
-
          precision    recall  f1-score   support

   blast       0.67      1.00      0.80         2
    roar       1.00      0.67      0.80         3
   roar_rumble 0.67      0.67      0.67         3
    trumpet    0.50      0.50      0.50         2


accuracy                           0.70        10
macro avg      0.71     0.71      0.69         10
weighted avg   0.73     0.70      0.70         10

---

### 🎯 Predictions
- The predicted class for the input audio (Decision Tree) is: baroo
- The predicted class for the input audio (Random Forest) is: roar_rumble

--- 
### Author
- Ashmita D
