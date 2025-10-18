# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Repository Overview

This is **DEforAI** - a comprehensive self-paced educational course focused on Data Engineering for AI/ML systems. The repository is structured as a learning resource with 15 chapters covering the complete ML data pipeline lifecycle, from foundational concepts to production-grade MLOps integration.

## Key Architecture & Structure

### Learning-Focused Repository Structure
```
DEforAI/
├── README.md                    # Main project overview and curriculum
├── Research/                    # 15 chapters of course content (Ch 0-15)
│   ├── 00. Overview/           # Course structure and reference materials
│   ├── 01. Introduction to DE for AI-ML/
│   ├── 02. ML Data Pipeline Lifecycle/
│   ├── 03. Data Architecture for ML Systems/
│   └── ... (through Chapter 15)
├── Exercises/                   # Hands-on exercises for each chapter
│   ├── Chapter-01/ through Chapter-15/
│   └── README.md               # Exercise guidelines and setup
├── Projects/                    # Implementation projects
│   ├── Capstone-Project/      # End-to-end ML data pipeline
│   ├── Mini-Projects/         # Focused, smaller projects
│   └── README.md              # Project approach and guidelines
├── Resources/                   # Reference materials and templates
│   ├── Code-Templates/        # Reusable code snippets
│   ├── Architecture-Diagrams/ # System architecture references
│   └── Reference-Materials/   # Papers, articles, documentation
├── Chats/                      # AI conversations and brainstorming
└── Daily Progress/             # Learning journal and progress tracking
```

### Course Curriculum Overview
The course follows a progressive 5-part structure:
1. **Foundations (Ch 1-3)**: Concepts, lifecycle, architecture patterns
2. **Data Infrastructure (Ch 4-6)**: Storage, warehouses, vector databases
3. **Data Pipelines (Ch 7-9)**: Batch processing, streaming, feature engineering
4. **ML-Specific Components (Ch 10-12)**: Feature stores, versioning, training data
5. **Operations & Quality (Ch 13-15)**: MLOps, data quality, monitoring

## Technology Stack Context

This is an **educational repository** covering a wide range of ML data engineering technologies:
- **Languages**: Python, SQL, PySpark
- **Processing**: Apache Spark, Apache Flink, Kafka
- **Storage**: S3, GCS, Snowflake, BigQuery, Delta Lake
- **ML Tools**: Feast (feature stores), Great Expectations, MLflow
- **Orchestration**: Apache Airflow, Dagster, Prefect
- **Infrastructure**: Docker, Kubernetes, Terraform

## Common Development Commands

### Environment Setup
```bash
# Create and activate virtual environment
python3 -m venv deforai-env
source deforai-env/bin/activate

# Install common ML data engineering dependencies
pip install pandas numpy scikit-learn jupyter
pip install pyspark apache-airflow feast
pip install great-expectations dvc mlflow
```

### Navigation and Progress Tracking
```bash
# View course structure
ls Research/

# Check exercise status
ls Exercises/Chapter-*/

# View project templates
ls Projects/

# Check available resources
ls Resources/
```

### Working with Course Content
Since this is primarily a markdown-based educational repository:
- Course content is in `Research/` directory (numbered 00-15)
- Each chapter has a README.md with learning objectives and topics
- Exercises are in corresponding `Exercises/Chapter-XX/` directories
- Progress tracking is done via markdown tables in README files

## File Patterns & Conventions

- **README Files**: Each directory contains a README.md with overview and structure
- **Chapter Numbering**: Consistent `00-15` numbering for sequential learning
- **Progress Tracking**: Markdown tables with status emojis (🔜 🟡 ✅)
- **Cross-References**: Internal links using `[[path/file.md|Display Name]]` format
- **Documentation Style**: Structured with learning objectives, topics, and notes sections

## Learning Context

This repository is designed for:
- Self-paced learning of ML data engineering concepts
- Hands-on practice through exercises and projects  
- Building a personal knowledge base
- Progressive skill development from foundations to production

### Key Learning Approach
1. **Sequential**: Chapters build upon each other
2. **Hands-on**: Each chapter includes practical exercises
3. **Project-based**: Mini-projects and capstone for integration
4. **Documentation-focused**: Progress tracking and reflection

## Working with This Repository

When helping with this repository, consider:
- This is an **educational/learning repository**, not a production codebase
- Focus on learning objectives and skill development
- Respect the structured, progressive curriculum approach
- Maintain consistency with existing documentation patterns
- Help track progress and maintain organization
- Support both theoretical understanding and practical implementation

The repository owner is João Blasques (Jonas), working through a comprehensive ML data engineering curriculum started October 18, 2025.