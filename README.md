# First Steps Towards Fall Prediction Using Gait Data

## Overview

This project implements a machine learning system for predicting fall risk using human gait data. The goal is to detect abnormal or unstable walking patterns that are indicative of an increased probability of falling.

Falls are a major cause of injury among elderly individuals and patients with neurological or musculoskeletal conditions such as Parkinson's disease, stroke, or mobility impairments. Rather than detecting falls after they occur, this system aims to identify biomechanical instability in advance using motion dynamics.

The project uses three-dimensional joint position and velocity data to model human gait and detect anomalies that correlate with fall risk.

## Dataset

This project uses a large-scale gait dataset published in Scientific Data (Nature).

**Dataset source:** https://www.nature.com/articles/s41597-023-02767-y

Due to licensing restrictions and large file size, the dataset is not included in this repository.

### How to obtain the data

1. Visit the dataset link above
2. Download the provided .mat files
3. Place the files inside the following directory in this repository:
   ```
   Dataset_Gait/
   ```

The system expects the dataset to be located in this folder.

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

The architecture is designed to support reproducible research, modular training pipelines, and future deployment.

## What the Model Learns

From 3D joint trajectories, the system extracts information about:

- Walking rhythm
- Stride length and symmetry
- Joint coordination
- Velocity and acceleration patterns
- Stability and irregular motion

These features are used to model normal walking behavior. Deviations from this baseline are treated as gait anomalies and interpreted as indicators of elevated fall risk.

## Installation

### Prerequisites

- Python 3.10 or higher
- Git

### Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/kevinmevada/First-Steps-Towards-Fall-Prediction.git
   cd First-Steps-Towards-Fall-Prediction
   ```

2. **Create a clean environment (recommended):**
   ```bash
   conda create -n gait python=3.10
   conda activate gait
   ```

3. **Install the project:**
   ```bash
   pip install -e .
   ```

## Usage

### Train the Model

```bash
python -m Fall_Prediction.pipeline.training_pipeline
```

### Run Fall-Risk Prediction

```bash
python -m Fall_Prediction.pipeline.prediction_pipeline
```

## Outputs

The system produces:

- Trained machine learning models
- Gait anomaly scores
- Stability and risk metrics
- Evaluation reports

These outputs are stored in the `artifacts/` directory, which is excluded from version control.

## Research and Clinical Relevance

This project can be applied to:

- Fall risk screening
- Rehabilitation monitoring
- Parkinson's and stroke gait analysis
- Mobility impairment assessment
- Assistive and wearable health technologies

It provides a framework for converting raw biomechanical motion data into clinically meaningful indicators of fall risk.

## Technical Specifications

### Dependencies

- Python 3.10+
- pandas
- numpy
- python-dotenv
- certifi

### System Requirements

- Minimum 8GB RAM
- 2GB free disk space for dataset and models
- GPU support (optional, for enhanced training performance)

## Contributing

This project follows standard research software development practices. For contributions:

1. Fork the repository
2. Create a feature branch
3. Ensure all tests pass
4. Submit a pull request with detailed description

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Citation

If you use this work in your research, please cite:

```bibtex
@software{mevada2024_fall_prediction,
  title={First Steps Towards Fall Prediction Using Gait Data},
  author={Mevada, Kevin},
  year={2026},
  publisher={GitHub},
  howpublished={\url{https://github.com/kevinmevada/First-Steps-Towards-Fall-Prediction}}
}
```

## Author

**Kevin Mevada**  
MS in Computer Science (AI and Machine Learning)  
Illinois Institute of Technology  
Email: kmevada@hawk.illinoistech.edu

## Acknowledgments

- Dataset providers from Scientific Data (Nature)
- Illinois Institute of Technology research community
- Open-source contributors in the machine learning and biomechanics community
