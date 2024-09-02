# Digit Recognition with MNIST Dataset

## Overview

This project implements a digit recognition system using the MNIST dataset. It explores dimensionality reduction techniques and classification methods to accurately identify handwritten digits. The main focus is on using Singular Value Decomposition (SVD) for feature extraction and a simple nearest neighbor approach for classification.

## Key Features

- Data preprocessing and normalization
- Dimensionality reduction using SVD
- Implementation of various techniques to determine the optimal number of principal components:
  - Scree plot
  - Cumulative percentage of total variation
  - Kaiser rule
  - Entropy
  - Approximation (Eckhart-Young theorem)
- Classification of digits using nearest neighbor approach
- Evaluation metrics including confusion matrix and classification report

## Installation

To set up the project environment:

1. Clone the repository:
```
git clone https://github.com/yourusername/digit-recognition-mnist.git
cd digit-recognition-mnist
```

2. Create a virtual environment (optional but recommended):
```
python -m venv venv
source venv/bin/activate # On Windows use venv\Scripts\activate
```

3. Install the required packages:
```
pip install -r requirements.txt
```

## Usage

The main analysis is contained in the Jupyter notebook `notebooks/digit_recognition_mnist.ipynb`. To run the notebook:

1. Ensure you have Jupyter installed (`pip install jupyter` if not)
2. Navigate to the `notebooks/` directory
3. Run `jupyter notebook`
4. Open `digit_recognition_mnist.ipynb`

The notebook contains detailed comments and explanations for each step of the process.

## Results

The project achieves digit classification using a reduced feature space. Key findings include:

- Optimal number of principal components determined by various methods
- Visualization of the scree plot and cumulative variance explained
- Confusion matrix showing classification performance
- Detailed classification report with precision, recall, and F1-score for each digit

For a comprehensive analysis of the results, please refer to the `docs/report.md` file.