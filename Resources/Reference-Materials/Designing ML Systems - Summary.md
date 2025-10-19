---
title: Designing ML Systems - Summary
author: Chip Huyen
type: book-summary
tags:
  - machine-learning
  - ml-systems
  - data-engineering
  - mlops
  - production-ml
project: "[[DEforAI]]"
created: 2025-10-18
source: ABUIABA9GAAghIK0ugYowM2h3QY_compressed.pdf
status: reference
---

# Designing ML Systems - Summary

**Author:** Chip Huyen
**Type:** Book Summary (Initial Chapters)
**Relevance:** Comprehensive deep dive into practical aspects of building, deploying, and maintaining ML systems in production

---

## Overview

This document, comprising the initial chapters of "Designing Machine Learning Systems" by Chip Huyen, offers a comprehensive deep dive into the practical aspects of building, deploying, and maintaining Machine Learning (ML) systems in production. It moves beyond theoretical ML algorithms, emphasizing the engineering challenges and iterative processes crucial for production-ready applications.

**Core Message:** For data engineers, the document provides highly actionable insights into managing the data lifecycle, designing robust data pipelines, and understanding the unique demands ML systems place on data infrastructure.

---

## 1. Main Topics Covered

### ML Systems Fundamentals

**Holistic View of ML Systems:**
An ML system is more than just algorithms; it encompasses:
- Interfaces
- Data stacks
- Hardware
- Infrastructure for development, deployment, monitoring, and updates

**ML Problem Suitability:**
Criteria for deciding when and when not to apply ML:
- Data availability
- Pattern complexity
- Repetitiveness
- Cost of errors
- Scale
- Changing patterns

**ML in Production vs. Research:**
Key differences in:
- Stakeholders
- Computational priorities (fast inference over fast training)
- Data characteristics (messy, shifting, biased vs. clean, static)
- Ethical considerations (fairness, interpretability)

### Data Engineering Fundamentals for ML

**Core Data Concepts:**
- Data sources
- Data formats
- Data models
- Storage engines
- Data processing paradigms (OLTP vs. OLAP, ETL/ELT)
- Dataflow modes (databases, services, real-time transports)

**Training Data Management:**
- Sampling techniques
- Challenges in labeling (cost, privacy, speed, multiplicity)
- Data lineage
- Handling lack of hand labels (weak supervision, semi-supervision, transfer learning, active learning)
- Class imbalance
- Data augmentation

**Feature Engineering:**
- The critical role of features
- Common operations:
  - Missing values
  - Scaling
  - Discretization
  - Categorical encoding
  - Feature crossing
  - Positional embeddings
- The pervasive problem of data leakage

### Model Development & Evaluation

**Development Process:**
- Framing ML problems
- Objective functions
- Decoupling objectives
- Model selection strategies
- Experiment tracking and versioning (code and data)
- Debugging ML models
- Distributed training (data, model, pipeline parallelism)
- AutoML

**Evaluation Methods:**
- Offline evaluation methods
- Baselines
- Perturbation testing
- Invariance testing
- Directional expectation tests
- Calibration
- Confidence measurement
- Slice-based evaluation

### Model Deployment

**Deployment Strategies:**
- Debunking deployment myths
- Contrasting batch vs. online prediction
- Unifying batch and streaming pipelines

**Model Compression:**
- Low-rank factorization
- Knowledge distillation
- Pruning
- Quantization

**Infrastructure:**
- ML on cloud vs. edge devices
- Optimization for edge hardware (IRs, compilers, autoTVM, WASM)

### ML System Failures in Production

**Failure Types:**
- Reasons for failure (software vs. ML-specific)
- Concept drift
- Covariate shift
- Label shift
- Feature change
- Label schema change
- Edge cases
- Degenerate feedback loops

**Detection and Correction:**
- Strategies for data distribution shifts

---

## 2. Key Concepts and Frameworks

### System Components

**ML System Components:**
- Interface
- Data
- Infrastructure
- Hardware
- ML Algorithms

**Data-Centric ML:**
- The emphasis on data quality and quantity as the primary driver of ML success
- Rather than solely algorithm innovation

### Data Formats & Storage

**Data Formats:**
- **JSON:** Flexible, human-readable
- **CSV:** Simple tabular format
- **Parquet:** Column-major, binary, efficient for reads
- **Avro:** Binary, schema evolution
- **Protobuf:** Binary, schema evolution
- **Pickle:** Python serialization

**Data Models:**
- **Relational:** Strict schema, SQL
- **Document:** Flexible schema, locality
- **Graph:** Relationships-focused

**Database Types:**
- **OLTP:** Transactional databases
- **OLAP:** Analytical databases

### Data Processing

**ETL/ELT:**
- Fundamental processes for data preparation

**Dataflow Modes:**
- Data passing via databases
- REST/RPC services
- Real-time transports (e.g., Apache Kafka, AWS Kinesis, RabbitMQ) for event-driven architectures

**Batch vs. Stream Processing:**
- Processing historical (static features) versus real-time (dynamic features) data
- Using engines like Apache Flink, KSQL, Spark Streaming

### Sampling and Labeling

**Sampling Techniques:**

**Non-probability:**
- Convenience
- Snowball
- Judgment
- Quota

**Probability:**
- Simple random
- Stratified
- Weighted
- Importance
- Reservoir sampling for streaming data

**Labeling Strategies:**
- Hand labeling challenges
- Weak supervision (Snorkel, labeling functions)
- Semi-supervision
- Transfer learning
- Active learning

### Feature Engineering

**Feature Engineering Operations:**

**Handling Missing Values:**
- Imputation
- Deletion
- Types: MNAR (Missing Not At Random), MAR (Missing At Random), MCAR (Missing Completely At Random)

**Scaling:**
- Normalization
- Standardization
- Log transformation

**Discretization:**
- Binning continuous features

**Categorical Encoding:**
- Hashing trick for high-cardinality/dynamic categories

**Feature Crossing:**
- Creating interaction features

**Positional Embeddings:**
- Encoding position information

**Data Leakage:**
- Critical concept where future/label information leaks into features during training

### MLOps Concepts

**Experiment Tracking:**
- Logging loss, metrics, system performance

**Data Versioning:**
- Using tools like DVC (Data Version Control)

**Distributed Training:**
- Data parallelism
- Model parallelism
- Pipeline parallelism
- Straggler mitigation

**AutoML:**
- Hyperparameter tuning
- Neural Architecture Search (NAS)

### Deployment and Optimization

**Model Deployment Paradigms:**
- **Batch prediction:** Asynchronous
- **Online prediction:** Synchronous/on-demand
- **Cloud vs. Edge computing**

**Model Optimization:**
- Model compression:
  - Low-rank factorization
  - Knowledge distillation
  - Pruning
  - **Quantization** (critical for production)
- Inference optimization
- Intermediate Representations (IRs)
- Compilers (autoTVM)
- WebAssembly (WASM)

### Production Challenges

**Data Distribution Shifts:**
- **Covariate shift:** P(X) changes
- **Label shift:** P(Y) changes
- **Concept drift:** P(Y|X) changes
- **Feature change:** Features themselves change
- **Label schema change:** Label definitions change
- **Train-serving skew:** Inconsistencies between training and serving

**Degenerate Feedback Loops:**
- System outputs influencing future inputs
- Leading to biases (e.g., popularity bias in recommenders)

---

## 3. Practical Applications and Examples

### Data Engineering Applications

**Data Source Integration:**
- Building pipelines to ingest and process data from diverse sources:
  - User input (e.g., malformed text in search queries)
  - System logs (for monitoring/debugging)
  - Internal databases (CRM, inventory)
  - Third-party providers

**Efficient Data Storage:**
- Choosing appropriate data formats:
  - Parquet for analytical workloads due to column-major storage and compression
  - JSON for unstructured data flexibility
- Data models:
  - Relational for structured data
  - Graph for relationship-heavy applications

**Real-time Data Pipelines:**
- Implementing event-driven architectures using Kafka/Kinesis
- Streaming features (e.g., current driver availability for a ridesharing app) to support online prediction
- Alongside batch pipelines for static features

**Training Data Curation:**
- Developing and maintaining pipelines for:
  - Data sampling (e.g., stratified sampling for imbalanced classes)
  - Managing data lineage to trace data origins and quality
  - Supporting programmatic labeling (weak supervision) to generate training data at scale

### Feature Engineering Pipelines

**Robust Feature Engineering:**
Building automated processes for:
- Handling missing values (imputation strategies)
- Scaling features (normalization using *only training set statistics* to prevent leakage)
- Discretizing continuous features
- Encoding dynamic categorical features (using techniques like hashing trick)

**Data Leakage Prevention:**
- Structuring data splits by time for time-correlated data
- Calculating scaling statistics only from the training set
- Implementing robust deduplication mechanisms within pipelines

### Infrastructure and Deployment

**Scalable ML Infrastructure:**
- Setting up distributed training environments for large models
- Managing data parallelism (e.g., handling stragglers and gradient staleness)
- Understanding model parallelism

**Model Deployment Architectures:**
Designing systems for:
- **Batch prediction:** Precomputing recommendations for Netflix
- **Online prediction:** Real-time translation for Google Translate
- Considering latency vs. throughput trade-offs

**Inference Optimization:**
Implementing strategies for:
- Model compression like **quantization**
  - Example: Converting 32-bit floats to 8-bit integers for significant latency reduction on CPUs (as seen in Roblox case study)
- Leveraging model compilers (autoTVM) for efficient execution on various hardware, including edge devices

### Monitoring and Maintenance

**Production Monitoring:**
Establishing data monitoring systems to:
- Detect various data distribution shifts (covariate, label, concept drift)
- Use statistical tests (K-S, MMD)
- Track metrics over different time windows (sliding vs. cumulative statistics)
- Alert on performance degradation and train-serving skew

**Feedback Loop Management:**
- Designing data capture and processing for feedback loops
- Implementing mechanisms to detect and correct for degenerate feedback loops
- Example: randomization in recommender systems

---

## 4. Target Audience and Purpose

### Target Audience

- ML engineers
- Data scientists transitioning from research/academia to production
- **Data engineers** who are responsible for building and maintaining the data infrastructure that powers ML systems

### Purpose

To provide a holistic understanding of designing, building, deploying, and maintaining production-ready ML systems. It aims to:
- Bridge the gap between theoretical ML knowledge and practical engineering challenges
- Emphasize data-centric approaches
- Highlight the iterative nature of ML development

**For data engineers specifically:**
- Clearly articulates their crucial role beyond just data storage
- Encompasses data quality, pipelines, monitoring, and performance optimization

---

## 5. Notable Insights - Actionable for Data Engineers

### Critical Insights

1. **Data is the Foundation, Not Just Algorithms**
   - The success of ML systems hinges critically on the quality and quantity of data
   - Data engineers are at the forefront of enabling this success
   - Ensure robust data collection, storage, and processing

2. **Production Data is Messy and Dynamic**
   - Unlike research datasets, real-world production data is:
     - Noisy
     - Biased
     - Unstructured
     - Constantly shifting
     - Often a mix of historical and streaming
   - Data engineers must design resilient systems that account for these realities

3. **Train-Serving Skew is a Major Pitfall**
   - Inconsistencies between training and inference data pipelines are a common source of ML system failures
   - Unifying batch and streaming pipelines is crucial to prevent this

4. **Data Versioning is Hard, But Essential**
   - Versioning large, constantly changing datasets is a significant challenge
   - More complex than code versioning
   - Data engineers need to explore and implement tools (like DVC)
   - Develop strategies for data reproducibility and auditability

5. **Latency Matters for Online ML**
   - For real-time applications, inference latency is paramount
   - Data engineers contribute by:
     - Designing efficient streaming feature pipelines
     - Optimizing data formats for fast reads

6. **Data Leakage is Insidious**
   - Subtle but dangerous problem
   - Can lead to models performing well in development but failing in production
   - Data engineers must proactively implement safeguards:
     - Time-based splitting
     - Using train-only statistics for scaling/imputation

7. **Monitoring Data Distribution Shifts is Key to Longevity**
   - ML models degrade over time due to changes in data distributions
   - Types of drift: covariate, label, concept drift
   - Data engineers are responsible for building sophisticated monitoring systems
   - Can detect these shifts and trigger necessary retraining or re-engineering

8. **Data Engineers' Role in MLOps is Central**
   - From setting up experiment tracking and data versioning
   - To optimizing distributed training and inference
   - The data engineer's expertise in scalable, reliable data infrastructure is indispensable for successful MLOps

### Best Practices for Data Engineers

1. **Prioritize Data Quality:** Implement comprehensive validation and cleaning
2. **Build Flexible Pipelines:** Support both batch and streaming workloads
3. **Prevent Leakage:** Design careful data splits and preprocessing steps
4. **Version Everything:** Track data, features, models, and code
5. **Monitor Continuously:** Track data drift, model performance, and business metrics
6. **Optimize for Production:** Consider latency, throughput, and resource constraints
7. **Design for Resilience:** Build fault-tolerant systems with fallbacks
8. **Enable Reproducibility:** Use DAGs and version control for all pipelines

---

## Related Notes

- [[DEforAI]]
- [[Machine Learning Engineering - Summary]]
- [[Building ML Powered Applications - Summary]]

---

## Key Takeaways for Data Engineers

This book emphasizes that successful ML systems depend on robust data infrastructure and engineering practices. Data engineers play a central role in:

1. **Data Lifecycle Management**
   - Collection and ingestion from diverse sources
   - Quality assurance and validation
   - Storage and versioning
   - Preprocessing and feature engineering

2. **Pipeline Architecture**
   - Designing unified batch and streaming pipelines
   - Preventing train-serving skew
   - Building reproducible, scalable systems
   - Implementing efficient data transformations

3. **Production Support**
   - Monitoring data distributions and model performance
   - Detecting and responding to data drift
   - Optimizing inference latency and throughput
   - Managing model and data versions

4. **Collaboration with ML Teams**
   - Understanding ML requirements and constraints
   - Implementing MLOps best practices
   - Supporting experimentation and iteration
   - Enabling safe deployment and rollback

The engineering aspects of ML—particularly data engineering—are what make or break production ML systems. Data engineers are not just supporting players but central architects of successful ML applications.
