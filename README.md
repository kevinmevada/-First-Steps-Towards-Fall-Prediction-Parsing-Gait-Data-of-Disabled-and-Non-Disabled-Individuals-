<h1>First Steps Towards Fall Prediction Using Gait Data</h1>

<p><b>AI-Powered Gait Analysis for Fall Risk and Mobility Assessment</b></p>
<p>Research-grade machine learning system for detecting biomechanical instability from 3D motion data</p>

<p>
  <img src="https://img.shields.io/badge/python-3.10+-blue">
  <img src="https://img.shields.io/badge/license-MIT-green">
  <img src="https://img.shields.io/badge/status-research--grade-orange">
  <img src="https://img.shields.io/badge/ML-Gait%20Analysis-purple">
</p>

</div>

## Overview

This project implements a machine learning system for predicting fall risk using human gait data.
The objective is to detect abnormal or unstable walking patterns that indicate an increased probability of falling.

Falls are a leading cause of injury among elderly individuals and patients with neurological or musculoskeletal conditions such as Parkinson’s disease, stroke, or mobility impairment. Instead of detecting falls after they occur, this system estimates biomechanical instability in advance using motion dynamics derived from 3D joint trajectories.

The system processes joint positions and velocities to learn gait patterns and detect deviations associated with fall risk.

---

## Dataset

This project uses a large-scale gait dataset published in *Scientific Data (Nature)*.

Dataset source:
[https://www.nature.com/articles/s41597-023-02767-y](https://www.nature.com/articles/s41597-023-02767-y)

Due to licensing restrictions and large file size, the dataset is not included in this repository.

### How to obtain the data

1. Visit the dataset link above
2. Download the provided `.mat` files
3. Place the files inside the following directory:

```
Dataset_Gait/
```

The system expects the dataset to be located in this folder.

---

## Project Structure

```
First-Steps-Towards-Fall-Prediction/
│
├── Dataset_Gait/               # External gait dataset (not tracked by Git)
│
├── Fall_Prediction/            # Main Python package
│   ├── pipeline/               # Training and inference pipelines
│   ├── components/             # Data ingestion, validation, training, evaluation
│   ├── utils/                  # Feature extraction and helper functions
│   ├── exception/              # Custom error handling
│   ├── logging/                # Logging configuration
│   ├── entity/                 # Data entities and models
│   ├── constants/              # Project constants
│   └── __init__.py
│
├── notebooks/                  # Exploratory analysis and experiments
├── artifacts/                  # Generated models and outputs (not tracked)
├── requirements.txt
├── setup.py
└── README.md
```

---

## What the model learns

From 3D joint trajectories, the system extracts:

* Walking rhythm
* Stride length and symmetry
* Joint coordination
* Velocity and acceleration patterns
* Stability and irregular motion

These features define a baseline for normal walking. Deviations from this baseline are treated as gait anomalies and interpreted as elevated fall risk.

---

## Installation

### Prerequisites

* Python 3.10 or higher
* Git

### Setup

```bash
git clone https://github.com/kevinmevada/First-Steps-Towards-Fall-Prediction.git
cd First-Steps-Towards-Fall-Prediction

conda create -n gait python=3.10
conda activate gait

pip install -e .
```

---

## Usage

### Train the model

```bash
python -m Fall_Prediction.pipeline.training_pipeline
```

### Run fall-risk prediction

```bash
python -m Fall_Prediction.pipeline.prediction_pipeline
```

---

## Outputs

The system produces:

* Trained machine learning models
* Gait anomaly scores
* Stability and risk metrics
* Evaluation reports

All outputs are stored in the `artifacts/` directory, which is excluded from version control.

---

## Research and clinical relevance

This system can be applied to:

* Fall risk screening
* Rehabilitation monitoring
* Parkinson’s and stroke gait analysis
* Mobility impairment assessment
* Assistive and wearable health technologies

It converts raw biomechanical motion data into clinically meaningful indicators of fall risk.

---

## Technical specifications

### Dependencies

* Python 3.10+
* numpy
* pandas
* python-dotenv
* certifi

### System requirements

* Minimum 8 GB RAM
* 2 GB free disk space for dataset and models
* GPU optional for faster training

---

## Citation

```
@software{mevada2026_fall_prediction,
  title={First Steps Towards Fall Prediction Using Gait Data},
  author={Mevada, Kevin},
  year={2026},
  publisher={GitHub},
  howpublished={https://github.com/kevinmevada/First-Steps-Towards-Fall-Prediction}
}
```

---

## Author

Kevin Mevada
MS in Computer Science (AI and Machine Learning)
Illinois Institute of Technology
Email: [kmevada@hawk.illinoistech.edu](mailto:kmevada@hawk.illinoistech.edu)

---

## Acknowledgments

* Dataset providers from Scientific Data (Nature)
* Illinois Institute of Technology research community
* Open-source contributors in machine learning and biomechanics

---
