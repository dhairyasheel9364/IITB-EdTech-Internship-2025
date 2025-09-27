Cognitive Load Detection using EEG & GSR

Note: Due to GitHub storage restrictions, the raw dataset and large `.pkl` model files could not be uploaded.

This project implements a complete machine learning pipeline for detecting cognitive load (task difficulty) based on physiological data, specifically **Electroencephalography (EEG)** and **Galvanic Skin Response (GSR)**. The work leverages a multimodal dataset to design, train, and compare both traditional machine learning methods and state-of-the-art deep learning approaches.

---

**Table of Contents

* Project Objective
* Methodology
* Project Structure
* How to Run
* Results & Insights

---

**Project Objective

The goal is to build an accurate classifier that differentiates between **low, medium, and high levels of cognitive load** encountered by students while solving 3D mental rotation tasks. By analyzing synchronized EEG (brain activity) and GSR (skin conductance) signals, the project identifies physiological markers predictive of mental workload.

---

**Methodology

The workflow follows a systematic data science pipeline, from raw data preparation to final inference:

1. **Data Consolidation & Cleaning** (`00_consolidate_raw_data.ipynb`)

   * Raw data from 38 participants is merged into three master files (`EEG.csv`, `GSR.csv`, `PSY.csv`).
   * Noise removal, missing value handling, and selection of key sensor channels are performed.

2. **Preprocessing & Windowing** (`01_preprocessing.ipynb`)

   * Cleaned data is aligned with task logs (`PSY.csv`).
   * Signals are segmented into windows, with each window representing EEG and GSR recordings during a task attempt.

3. **Feature Engineering** (`02_feature_engineering.ipynb`)

   * Statistical descriptors are extracted from each window (mean, variance, etc.).
   * EEG features include power in standard frequency bands (Delta, Theta, Alpha, Beta, Gamma) and cognitive load ratios (e.g., Theta/Alpha).
   * GSR features include amplitude- and frequency-based measures.

4. **Baseline Modeling** (`03_modeling_baseline_classification.ipynb`)

   * A LightGBM model is trained on the engineered dataset.
   * Hyperparameters are tuned with `RandomizedSearchCV` for optimal accuracy.

5. **Deep Learning Approach** (`04_modeling_deep_timeseries.ipynb`)

   * Raw time-series data is transformed into spectrogram images.
   * A pre-trained EfficientNet architecture is fine-tuned via transfer learning for cognitive load classification.

6. **Analysis & Inference** (`05_analysis.ipynb`, `06_inference_example.ipynb`)

   * Performance of LightGBM vs. EfficientNet is compared.
   * Feature importance analysis highlights physiological patterns most relevant to workload.
   * A demo inference script shows how the saved model can be applied to new samples.

---

**Project Structure

```
project/
├── data/
│   ├── raw/
│   │   ├── All_raw_data/
│   │   │   ├── EEG.csv
│   │   │   ├── GSR.csv
│   │   │   └── PSY.csv
│   │   ├── 1_EEG.csv
│   │   ├── 1_GSR.csv
│   │   └── ... (all 38 participants)
│   └── processed/
│       ├── features_dataset.csv
│       └── task_windows.pkl
├── models/
│   ├── lgbm_model.pkl
│   └── cnn_lstm_model.pt
├── notebooks/
│   ├── 00_consolidate_raw_data.ipynb
│   ├── 01_preprocessing.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_modeling_baseline_classification.ipynb
│   ├── 04_modeling_deep_timeseries.ipynb
│   ├── 05_analysis.ipynb
│   └── 06_inference_example.ipynb
├── requirements.txt
└── README.md
```

---

**How to Run

1. **Prerequisites**

   * Python 3.8+
   * Git

2. **Clone the Repository**

   ```bash
   git clone <repo_url>
   cd project
   ```

3. **Set up Virtual Environment**

   ```bash
   python -m venv venv
   # Windows
   venv\Scripts\activate
   # macOS/Linux
   source venv/bin/activate
   ```

4. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```

Do you also want me to **shorten this into a polished README.md version** (GitHub-ready) or keep it as a **formal internship report write-up**?
