# Anomaly Detection Using Gaussian Model

## Project Overview
This project implements an anomaly detection algorithm using a Gaussian distribution model. The goal is to detect failing servers based on two key features: throughput (mb/s) and latency (ms) of server responses. The dataset includes normal server behavior, and the algorithm identifies anomalous behaviors that deviate from this norm.

**Key Techniques:**
- Gaussian distribution fitting for anomaly detection.
- Selection of an optimal threshold for classifying anomalies using F1 score.
- Application to both 2D and high-dimensional datasets.

## Objectives
1. Fit a Gaussian distribution to the dataset to model normal behavior.
2. Select an appropriate threshold (ε) to detect anomalies.
3. Apply the model to a higher-dimensional dataset for more complex anomaly detection.

## Methodology
1. **Gaussian Distribution Fitting:**
   We fit a Gaussian model to each feature in the dataset and compute the mean (µ) and variance (σ²) for each feature. The probability density function of the Gaussian model is then used to estimate the likelihood of each data point.

2. **Selecting a Threshold (ε):**
   The algorithm selects a threshold based on the F1 score, balancing precision and recall. Points with a probability lower than the threshold are classified as anomalies.

3. **High Dimensional Dataset:**
   The model is applied to a high-dimensional dataset containing 11 features. We use the same approach to detect anomalies in this more complex environment.

## Key MATLAB Functions
- **anomaly_detection.m:** Implements the overall anomaly detection workflow.
- **multivariateGaussian.m:** Computes the probability density function for the Gaussian distribution.
- **estimateGaussian.m:** Estimates the Gaussian parameters (mean and variance) for the dataset.
- **visualizeFit.m:** Plots the fitted Gaussian distribution and dataset.
- **selectThreshold.m:** Selects the best threshold ε based on F1 score.

## Results
### Example 1: 2D Dataset
- **Input Data:** 307 server throughput and latency measurements.
- **Output:** Identified anomalous server behaviors based on low-probability regions in the Gaussian distribution.

### Example 2: High Dimensional Dataset
- **Input Data:** 11 features capturing more detailed server performance data.
- **Output:** Detected 117 anomalies with a threshold of ε = 1.38e-18.

## Tools and Technologies
- **Programming Language:** MATLAB
- **Data Files:** 
  - `data1.mat`: First dataset (2D).
  - `data2.mat`: Second dataset (multidimensional).
- **Techniques:** Anomaly Detection, Gaussian Distribution, F1 Score, Precision and Recall

## Visualizations
### 2D Dataset Visualization
- **Gaussian Distribution Contours:** The contours show the regions of high probability (normal behavior) and low probability (anomalous behavior).
- **Anomaly Detection:** Marked anomalies in the dataset based on the selected threshold.

### Limitations
- Assumes features are independent and normally distributed.
- Threshold selection depends on labeled cross-validation data.

## Conclusion
This project successfully implements anomaly detection using Gaussian models. By fitting a Gaussian distribution to the data, we can identify low-probability events that signal potential server failures. The threshold selection via the F1 score allows for fine-tuning of the anomaly detection process, balancing false positives and false negatives.

## Team Members and Contributions
- **Lead Developer:** Handled Gaussian model implementation and anomaly detection.
- **Data Preparation:** Curated server throughput and latency datasets for analysis.
- **Debugging and Testing:** Ensured proper implementation of the anomaly detection algorithm and conducted testing on high-dimensional datasets.
