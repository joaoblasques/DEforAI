---
title: Machine Learning Engineering - Summary
author: Andriy Burkov
type: book-summary
tags:
  - machine-learning
  - ml-engineering
  - data-engineering
  - mlops
project: "[[DEforAI]]"
created: 2025-10-18
source: Machine Learning Engineering (Andriy Burkov) (Z-Library)_compressed.pdf
status: reference
---

# Machine Learning Engineering - Summary

**Author:** Andriy Burkov
**Type:** Book Summary
**Relevance:** Practical guide for operationalizing ML models - essential for data engineers working with ML systems

---

## Overview

Andriy Burkov's "Machine Learning Engineering" serves as a practical guide for operationalizing machine learning models, bridging the gap between theoretical ML research and real-world implementation challenges. The book emphasizes actionable knowledge for engineers, particularly those involved in building and maintaining ML systems.

**Core Message:** ML is Engineering, Not Just Science. The hardest problems are often engineering (data infrastructure, reproducibility, deployment, monitoring) rather than scientific (algorithm innovation).

---

## 1. Main Topics and Chapters Covered (ML Project Lifecycle)

The book structures the Machine Learning Engineering discipline around a comprehensive **ML Project Life Cycle**, which includes the following nine stages:

1. **Goal Definition:** Translating business problems into well-defined ML goals
2. **Data Collection & Preparation:** Sourcing, cleaning, and structuring data for ML
3. **Feature Engineering:** Transforming raw data into informative features
4. **Model Training (Part 1 & 2):** Selecting algorithms, training models, hyperparameter tuning, and addressing common issues like bias-variance. Includes both shallow and deep learning strategies
5. **Model Evaluation:** Assessing model performance offline and online, including statistical bounds and fairness
6. **Model Deployment:** Making the trained model available for use in production
7. **Model Serving:** The runtime environment and modes of delivering predictions
8. **Model Monitoring:** Continuously tracking model performance and system health in production
9. **Model Maintenance:** Strategies for updating and improving models over time

The book also covers foundational concepts (Introduction) and strategic considerations *Before the Project Starts*, such as project prioritization, complexity estimation, and team structuring.

---

## 2. Key Concepts and Frameworks

### Data Terminology
- **Directly vs. Indirectly Used Data:** Data used to form examples directly versus data used to enrich features (e.g., dictionaries)
- **Raw vs. Tidy Data:** Raw data is in its natural form, while tidy data is structured (rows as examples, columns as attributes/features)
- **Training, Validation, and Test Sets:** The standard partitioning strategy for model development and evaluation
- **Holdout Sets:** Validation and test sets, unseen by the learning algorithm

### Core Concepts
- **Machine Learning Pipeline:** A sequence of transformations and model training stages that convert raw data into a deployable model
- **Parameters vs. Hyperparameters:** Parameters are learned by the model; hyperparameters are set by the analyst to control the learning process
- **Baselines:** Simple algorithms (random prediction, zero rule) used as a reference point for comparing model performance
- **Bias-Variance Tradeoff:** The fundamental conflict between a model's ability to fit training data well (low bias) and its ability to generalize to unseen data (low variance)

### Regularization Techniques
- L1, L2 regularization
- Dropout
- Early stopping
- Batch normalization

### Performance Metrics

**Regression:**
- Mean Squared Error (MSE)
- Median Absolute Error (MdAE)
- Almost Correct Predictions Error Rate (ACPER)

**Classification:**
- Confusion Matrix (TP, FP, FN, TN)
- Precision, Recall, F-measure (F1-score, Fβ)
- Accuracy, Per-class Accuracy
- Cohen's Kappa
- ROC Curve/AUC

**Ranking:**
- Discounted Cumulative Gain (DCG)
- Normalized Discounted Cumulative Gain (nDCG)

### Production Concepts
- **Model Calibration:** Ensuring a model's predicted probabilities align with actual likelihoods (Platt scaling, isotonic regression)
- **Distribution Shift:** Changes in data distribution between training and production environments (covariate shift, prior probability shift, concept drift)
- **Deployment Patterns:** Static, Dynamic (on device, server, browser), Serverless, Model Streaming
- **Deployment Strategies:** Single, Silent, Canary, Multi-Armed Bandit (MAB)
- **Data/Model Versioning:** Tracking changes to data, feature extractors, and models for reproducibility and rollback
- **Feature Store:** A centralized repository for managing and serving features
- **Error Analysis:** A systematic process to understand and fix model performance issues

---

## 3. Practical Applications and Examples

### Problem Framing
How to determine if ML is suitable for a business problem:
- Spam detection
- Loan repayment
- Image recognition
- Problems that are "too complex for coding," "constantly changing," "perceptive," or "unstudied phenomena"

### Data Labeling
- Using crowdsourcing (Mechanical Turk)
- Noisy pre-labeling with an initial model
- Designing efficient labeling tools to minimize manual effort and improve quality

### Feature Engineering Examples

**Text:**
- One-hot encoding
- Bag-of-Words, Bag-of-N-grams for movie title recognition in tweets
- Topic Modeling (LSA, LDA) to represent documents

**Categorical:**
- Mean encoding
- Log-odds ratio
- Sine-cosine transformation for cyclical features (e.g., days of the week)

**Time-Series:**
- Chunking observations
- Calculating statistics (mean, median, standard deviation, growth, outliers) within a sliding window for stock price prediction

**Relational Data:**
- Synthesizing features (e.g., mean order amount, standard deviation of call duration) from joined tables for churn analysis

**Embeddings:**
- Word2Vec, Doc2Vec
- General embeddings for images (CNN, AlexNet) as learned features

**Data Augmentation:**
- Image transformations (flip, rotate, crop, color shift, noise)
- Text augmentation (synonym replacement, back translation) to increase dataset size and improve model robustness

### Model Evaluation in Practice

**Baselines:**
- Setting a human-level performance or simple heuristic as a baseline

**Metrics Selection:**
- Choosing precision for spam detection (avoid false positives)
- Recall for fraud detection (avoid false negatives)
- F-score for a balance
- Using nDCG for ranking

**A/B Testing:**
- Using G-test (for yes/no outcomes) and Z-test (for continuous metrics like time spent) to statistically compare new models in production

**Multi-Armed Bandit (UCB1):**
- Dynamically routing users to the best-performing model to balance exploration and exploitation in online experiments

### Deployment Scenarios

**On-device ML:**
- Deploying models using TensorFlow Lite, Core ML for mobile apps to reduce latency and preserve privacy

**Web Services:**
- Building REST/gRPC APIs using Flask/FastAPI (Python) or Plumber (R) for server-side inference, with autoscaling groups

**Containers:**
- Deploying models in Docker containers orchestrated by Kubernetes for resource efficiency and scalability

**Serverless:**
- Using cloud functions (AWS Lambda, Azure Functions) for cost-efficiency and simplified management

**Model Streaming:**
- Integrating models into stream-processing engines (Apache Storm, Spark, Flink) for real-time inference on continuous data

### Operational Logging
Logging user context, model inputs/outputs, and user reactions to aid debugging and future model improvements.

**Examples:**
- Device malfunction (vibration, firmware, usage)
- Credit risk (age, salary, debts)
- Ad display (webpage title, user position)

### Abuse Prevention
Strategies like reputation scoring, classifying user behavior, payment models, and progressive delays for requests to prevent model manipulation or unauthorized data extraction.

---

## 4. Target Audience and Learning Objectives

### Target Audience
- **Data Analysts** who aspire to become Machine Learning Engineers
- **Machine Learning Engineers** looking to bring more structure and best practices to their work
- **Machine Learning Engineering Students** seeking a comprehensive overview of the field
- **Software Architects** who interact with or integrate ML models developed by others

### Prerequisites
Readers are expected to have a basic understanding of machine learning concepts and be capable of building a model given a properly formatted dataset (e.g., familiar with the content of "The Hundred-Page Machine Learning Book").

### Learning Objectives
The book aims to fill the gap left by most traditional ML books, which often focus on algorithms and theory. Its core objectives are to equip readers with the knowledge and best practices for the *engineering* aspects of ML projects, including:
- Defining clear ML project goals and estimating complexity
- Ensuring high-quality data collection, preparation, and feature engineering
- Selecting appropriate algorithms and tuning hyperparameters
- Rigorously evaluating model performance, both offline and in production
- Implementing robust and scalable model deployment, serving, and monitoring solutions
- Understanding and mitigating common failure points in ML projects
- Developing maintainable and reproducible ML systems

---

## 5. Notable Insights for Data Engineers

### Actionable Knowledge

1. **"Data First, Algorithm Second"**
   - Prioritize collecting high-quality, relevant, and sufficiently varied data over endlessly tweaking algorithms
   - Data augmentation is often more impactful than complex model architectures

2. **Embrace Imperfection**
   - ML models are not perfect and will make errors
   - Design systems to anticipate, detect, and gracefully handle these errors (e.g., fallbacks, "I don't know" responses)

3. **Reproducibility is Paramount**
   - Automate all data collection, preprocessing, feature engineering, and model training steps via scripts
   - Manual interventions are difficult to reproduce and scale

4. **Version Everything**
   - Data, feature extraction code, and models must be versioned and kept in sync
   - This is critical for debugging, rollbacks, and future improvements
   - Level 2 versioning (code + small data assets in Git, large files in object storage with unique IDs) is recommended for most projects

5. **Robust Data Infrastructure**
   - Invest in data infrastructure that provides accessible, sizeable, useable, understandable, and reliable data
   - This includes addressing data accessibility (legal, privacy, cost), quality (noise, bias, outliers, leakage), and storage (formats, levels, versioning, documentation)

6. **Beware of Data Leakage**
   - This is a major failure point
   - Always partition data (train/validation/test) *before* any feature engineering, imputation, or scaling steps that rely on global dataset statistics
   - Be vigilant for features that are functions of the target or "from the future"

7. **The Value of a Feature Store**
   - For large organizations, a feature store is a critical tool to ensure feature reuse, consistent definitions, efficient computation, synchronization between training and serving, and clear expiration policies

8. **Test Early and Often**
   - Test feature extractors thoroughly for correctness, speed, memory, and compatibility
   - Implement end-to-end and confidence tests for models during deployment

9. **Comprehensive Monitoring**
   - Don't just monitor model accuracy
   - Track data distribution shifts, prediction bias, numerical stability (NaNs), computational performance (latency, resource usage), and user engagement
   - Define alert thresholds carefully

10. **Iterative Refinement and Error Analysis**
    - Model development is iterative
    - Systematically analyze frequent error patterns (focused errors) on a small validation subset to guide feature engineering or data collection efforts

11. **Consider Business-Specific Metrics**
    - While standard ML metrics are useful, ultimately optimize for business objectives
    - Be prepared to tune hyperparameters to a business-specific performance measure, even if it slightly degrades a general ML metric

12. **Efficient Code is Key**
    - Write efficient, vectorized code (e.g., using NumPy) and leverage compiled libraries (C/C++)
    - Use specialized execution engines (MLeap)
    - Use profiling tools to identify bottlenecks
    - Parallelize training/inference where possible

13. **Manage Human Factors**
    - Account for human unpredictability, biases, expectations, and fatigue when designing ML systems
    - Gain user trust early, communicate model limitations, and provide options to report/undo errors

---

## Related Notes

- [[DEforAI]]
- [[Building ML Powered Applications - Summary]]
- [[Designing ML Systems - Summary]]

---

## Key Takeaways for Data Engineers

This book emphasizes that successful ML engineering depends heavily on robust data infrastructure, reproducible pipelines, comprehensive monitoring, and iterative refinement. For data engineers, the key is to:

1. Build flexible, version-controlled data pipelines
2. Implement rigorous data quality checks
3. Prevent data leakage through careful pipeline design
4. Monitor both data and model performance in production
5. Design systems for continuous improvement and maintenance

The engineering aspects of ML—not the algorithms—are what make or break production ML systems.
