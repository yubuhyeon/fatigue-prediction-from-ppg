# fatigue-prediction-from-ppg
PPG bio-signal based fatigue prediction project.

\n--- README.md Content ---
Copy the text below and paste it into your README.md file on GitHub.\n

# PPG Signal Based Fatigue Prediction Model

## 1. Project Overview
This project aims to develop a machine learning model that predicts a user's 'fatigue' state by analyzing Photoplethysmography (PPG) bio-signals, typically measured by devices like smartwatches. The core of the analysis involves extracting Heart Rate Variability (HRV) features.

## 2. Data Used
- **Source:** PhysioNet - BIDMC PPG and Respiration Dataset
- **Signal Type:** PPG (Photoplethysmography)
- **Sampling Frequency:** 125Hz

## 3. Analysis Pipeline
1.  **Data Loading:** The raw `.dat` signal file was loaded using the `wfdb` library.
2.  **Preprocessing:** A Band-pass filter from `scipy` was applied to remove motion artifacts and other noise from the raw signal.
3.  **Feature Engineering:** The signal was segmented into 1-minute windows. In each window, peaks were detected to calculate RR-intervals, and from these, the key HRV features (`sdnn` and `mean_rr`) were computed.
4.  **Model Training:** The extracted features were used to train a `RandomForestClassifier` to classify each 1-minute segment as 'fatigue' (1) or 'normal' (0).
5.  **Evaluation:** The model achieved an accuracy of **100.00%** on the unseen test set.
## 4. Conclusion
- The analysis revealed that `sdnn`, a measure of the standard deviation of RR-intervals, was the most important feature for predicting the defined fatigue state.
- This project demonstrates a complete pipeline for processing raw bio-signal data to train a predictive machine learning model.
