# Network Anomaly Detection using Unsupervised Learning

## Project Overview

This project focuses on detecting unusual network traffic patterns without using labeled attack data. In real-world cybersecurity, attacks often appear as slightly strange versions of normal behavior rather than obvious threats. The goal was to build a machine learning system that can automatically identify suspicious activity by learning what normal traffic looks like.

---

## Problem Statement

Detect abnormal network traffic patterns without labeled attack data.

---

## Dataset

I used the **KDD Cup 1999 Data dataset**, which contains hundreds of thousands of connection records with different features such as protocol type, bytes transferred, connection duration, and more.

To simulate a real-world scenario where attack labels are not available, the label column was removed before training the model.

---

## Approach

The project follows a simple machine learning pipeline:

1. **Load Data** – Read dataset into Python
2. **Preprocess Data**

   * removed label column
   * converted text features to numbers
   * scaled all values
3. **Train Model** – Used Isolation Forest algorithm
4. **Detect Anomalies** – Model predicts which traffic looks unusual
5. **Visualize Results** – Used PCA to visualize normal vs anomalous points

---

## Model Used

**Isolation Forest**

Why this model?

* Designed specifically for anomaly detection
* Works without labeled data
* Efficient for large datasets
* Detects rare patterns well

---

## Results

* The model detected about **5% of network traffic as anomalous**
* Visualization showed normal traffic forming dense clusters
* Anomalies appeared scattered away from normal points
* This indicates the model successfully learned normal behavior and flagged unusual patterns

---

## Evaluation Method

Since this is an unsupervised problem, traditional accuracy is not the main metric. Instead, evaluation was based on:

* anomaly percentage detected
* distribution of anomaly scores
* visualization of clusters
* comparison with hidden labels (for validation only)

---

## Key Learnings

This project helped me understand:

* how anomaly detection works
* difference between supervised and unsupervised learning
* importance of preprocessing
* why evaluation depends on problem type
* how ML is applied in real cybersecurity systems

---

## Challenges Faced

Some challenges I encountered:

* handling text-based network features
* understanding evaluation for unsupervised models
* choosing correct model settings
* working with a large dataset

---

## Future Improvements

Possible extensions for this project:

* try other anomaly detection models
* compare their performance
* tune model parameters
* simulate real-time traffic detection

---

## How to Run

Install dependencies:

```
pip install pandas numpy scikit-learn matplotlib
```

Run notebook:

```
jupyter notebook
```

---

## Conclusion

This project demonstrates how machine learning can detect unusual behavior in network traffic without needing labeled attack data. It shows how unsupervised models can be useful in real-world cybersecurity scenarios where labeled data is limited or unavailable.

---
