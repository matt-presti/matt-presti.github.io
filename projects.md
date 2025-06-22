---
layout: page
title: Projects
subtitle: Portfolio of Technical Work & Development Projects
---

# Featured Project

## InvestaTrack: Investment Portfolio Tracker
**Status:** In Development | **Technologies:** Spring Boot, Java, PostgreSQL, Docker | **Timeline:** Fall 2025

### Project Overview
InvestaTrack is a full-stack investment portfolio tracking application built using Spring Boot and Java. The application enables users to create accounts, manage multiple stock portfolios, and monitor real-time portfolio performance through integration with financial data APIs. This project demonstrates enterprise Java development patterns and modern backend architecture principles.

### Architecture & Design
The application follows a multi-layered architecture utilizing Spring Boot's dependency injection and auto-configuration capabilities. The system implements RESTful API design with separate service, repository, and controller layers. Data persistence is managed through JPA/Hibernate with PostgreSQL, while Spring Security handles user authentication and authorization. The application integrates external financial APIs for real-time stock data and implements comprehensive error handling and validation.

### Technical Skills Demonstrated
- **Enterprise Java Development:** Spring Boot framework, dependency injection, Maven build management
- **Database Management:** PostgreSQL integration, JPA/Hibernate ORM, database schema design
- **Security Implementation:** Spring Security configuration, BCrypt encryption, database-based session authentication
- **DevOps & Testing:** Docker containerization, unit/integration testing with JUnit 5 and MockMvc

---

# Completed Projects

## WildFireCast: Predictive Analytics for Wildfire Risk Assessment
**Technologies:** Python, XGBoost, UMAP, HDBSCAN, NASA MODIS, NOAA Data | **Year:** 2024

### Project Overview
Developed a comprehensive machine learning system to predict wildfire intensity using weather pattern analysis and satellite data. The project integrated NOAA Global Surface Summary weather station data with NASA MODIS satellite wildfire detections across California from 2011-2020, implementing both supervised and unsupervised learning approaches to identify specific weather pattern signatures that precede high-intensity fire events.

### Technical Implementation & Results
Built an innovative data processing pipeline that transformed approximately 7.8 million individual satellite fire detections into coherent wildfire events through custom spatial-temporal clustering. Developed a sophisticated feature engineering approach extracting 30-day weather patterns preceding each fire event, including temperature metrics, precipitation totals, drought duration, and derived indices.

**Predictive Modeling Results:**
- **XGBoost Classification:** Achieved 80% accuracy in predicting fire intensity based on preceding weather conditions
- **Counter-intuitive Finding:** Wind speed showed surprisingly limited predictive value for fire intensity, contrary to conventional wisdom
- **Pattern Discovery:** UMAP and HDBSCAN clustering identified 55 distinct weather patterns, with high-risk clusters showing fire rates of 73% and 61%

**Spatial Integration Innovation:** Implemented a buffer-based methodology associating wildfire events with nearest weather stations within 50km radius, utilizing KDTree optimization for computational efficiency across 9,000+ weather stations.

### Technical Skills Demonstrated
- **Machine Learning:** XGBoost ensemble methods, UMAP dimensionality reduction, HDBSCAN clustering algorithms
- **Geospatial Analysis:** Custom spatial clustering algorithms, KDTree optimization, coordinate system transformations
- **Feature Engineering:** Time-series analysis, statistical aggregations, domain-specific metric creation
- **Scientific Computing:** NASA MODIS and NOAA dataset processing, statistical correlation analysis

### Impact & Applications
The methodology provides a framework for early warning systems and reveals that effective fire prediction requires monitoring a constellation of weather conditions rather than simplified metrics. Results demonstrate potential for 30-day advance warning systems and strategic resource allocation during high-risk periods.

---

## CodeDocGen: Automated Documentation Generator
**Technologies:** Python, CodeBERT, Transformers, PyTorch, Hugging Face | **Year:** 2024

### Project Overview
Developed an automated code documentation system using transformer-based models to generate Python function docstrings from source code. The project implemented CodeBERT as a sequence-to-sequence translation system, treating code documentation generation as a natural language processing task that translates between programming language syntax and human-readable descriptions.

### Technical Implementation & Constraints
Implemented an encoder-decoder architecture using CodeBERT from Hugging Face's transformers library, processing the CodeSearchNet dataset containing 412,178 Python functions with associated docstrings. Due to significant computational constraints (training performed locally on M2 MacBook Air without GPU acceleration), the study was limited to 100 training samples across 3 epochs with a batch size of 2.

**Architecture Details:**
- **Model Configuration:** CodeBERT-based encoder-decoder with cross-entropy loss optimization
- **Training Parameters:** Learning rate of 5e-5, AdamW optimizer with 0.01 weight decay
- **Data Pipeline:** Custom tokenization and preprocessing with 80/10/10 train/validation/test split
- **Hardware Limitations:** Local training without GPU acceleration significantly restricted model convergence potential

### Results & Technical Insights
Despite computational constraints, the system demonstrated moderate success in capturing code-documentation relationships:

**Performance Metrics:**
- **ROUGE-1 Score:** 0.24 (24% unigram overlap with reference documentation)
- **ROUGE-L Score:** 0.10 (indicating challenges in maintaining proper word sequences)
- **Parameter Identification:** 17% accuracy in correctly identifying function parameters in generated documentation
- **Coherence Analysis:** Generated text contained relevant technical vocabulary but lacked grammatical structure due to insufficient training data

**Key Technical Findings:** The project revealed the computational complexity and resource requirements for effective transformer-based code understanding. Results suggest that with adequate computational resources and full dataset training, the approach has potential for automated documentation generation. The experience provided valuable insights into the challenges of translating between formal programming languages and natural language while highlighting the critical importance of sufficient training data for transformer model convergence.

### Technical Skills Demonstrated
- **Natural Language Processing:** Transformer architecture implementation, sequence-to-sequence modeling, attention mechanisms
- **Deep Learning Frameworks:** PyTorch integration, Hugging Face transformers library, CodeBERT fine-tuning
- **Model Training & Optimization:** Custom dataset preprocessing, tokenization strategies, hyperparameter tuning
- **Research Implementation:** Academic paper replication, experimental design, computational constraint management

---

## GitHub Profile
**GitHub:** [@matt-presti](https://github.com/matt-presti)

All project repositories include comprehensive documentation, clean code architecture, and detailed setup instructions. View complete source code, technical documentation, and development progress on GitHub.

---

*This portfolio demonstrates practical application of enterprise development patterns, machine learning techniques, and modern software engineering practices. Each project showcases different aspects of full-stack development and data science capabilities.*
