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
- **Backend Architecture:** Multi-layered application design, RESTful API development, service-oriented architecture
- **Database Management:** PostgreSQL integration, JPA/Hibernate ORM, database schema design and optimization
- **Security Implementation:** Spring Security configuration, BCrypt encryption, JWT authentication flows
- **API Integration:** External service consumption, rate limiting, caching strategies, error handling
- **DevOps & Testing:** Docker containerization, unit/integration testing with JUnit 5 and MockMvc, cloud deployment

---

# Completed Projects

## WildFireCast: Predictive Analytics for Wildfire Risk Assessment
**Technologies:** Python, XGBoost, UMAP, HDBSCAN, NASA MODIS, NOAA Data | **Year:** 2025

### Project Overview
Developed a machine learning system to predict wildfire intensity using weather pattern analysis and satellite data. The project integrated NOAA weather station data with NASA MODIS satellite wildfire detections across California from 2011-2020, implementing both supervised and unsupervised learning approaches to identify weather patterns that precede high-intensity fire events.

### Technical Implementation
Built a comprehensive data processing pipeline that transformed raw weather and satellite data into meaningful predictive features. Implemented a custom spatial clustering algorithm to aggregate individual satellite fire detections into coherent wildfire events, processing approximately 7.8 million detection points. Developed feature engineering techniques extracting 30-day weather patterns preceding fire events.

### Technical Skills Demonstrated
- **Data Science Pipeline:** Large-scale data processing and integration from multiple heterogeneous sources
- **Machine Learning:** XGBoost ensemble methods, UMAP dimensionality reduction, HDBSCAN clustering algorithms
- **Geospatial Analysis:** Custom spatial clustering algorithms, KDTree optimization, coordinate system transformations
- **Feature Engineering:** Time-series analysis, statistical aggregations, domain-specific metric creation
- **Model Evaluation:** SHAP interpretability analysis, cross-validation strategies, multi-metric assessment frameworks
- **Scientific Computing:** NASA MODIS and NOAA dataset processing, statistical correlation analysis, pattern discovery techniques

### Key Findings & Impact
The analysis revealed that no single weather factor dominates wildfire prediction—instead, combinations of extended drought periods, elevated temperatures, and low humidity create conditions for intense fires. Contrary to expectations, wind speed showed limited predictive value. The methodology provides a framework for early warning systems and could inform wildfire management strategies.

---

## CodeDocGen: Automated Documentation Generator
**Technologies:** Python, CodeBERT, Transformers, PyTorch, Hugging Face | **Year:** 2025

### Project Overview
Developed an automated code documentation system using transformer-based models to generate Python function docstrings. The project treated code documentation as a sequence-to-sequence translation problem, implementing CodeBERT for understanding code structure and generating natural language descriptions.

### Technical Architecture
Implemented an encoder-decoder architecture using CodeBERT from Hugging Face's transformers library. The system processes the CodeSearchNet dataset containing 412,178 Python functions with associated docstrings. Developed custom preprocessing pipelines for tokenization and data preparation, along with specialized evaluation metrics combining ROUGE scores with functional correctness measures.

### Technical Skills Demonstrated
- **Natural Language Processing:** Transformer architecture implementation, sequence-to-sequence modeling, attention mechanisms
- **Deep Learning Frameworks:** PyTorch integration, Hugging Face transformers library, CodeBERT fine-tuning
- **Model Training & Optimization:** Custom dataset preprocessing, tokenization strategies, hyperparameter tuning
- **Evaluation Methodologies:** ROUGE metric implementation, custom accuracy measures, multi-dimensional assessment
- **Code Analysis:** Abstract syntax tree processing, programming language tokenization, semantic code understanding
- **Research Implementation:** Academic paper replication, experimental design, computational constraint management

### Results & Technical Insights
Achieved ROUGE-1 scores of 0.24 with 17% parameter identification accuracy. The project highlighted the computational complexity of transformer-based code understanding and provided insights into the challenges of translating between programming languages and natural language. The framework demonstrates the potential for automated documentation tools while revealing areas for future optimization.

---

## GitHub Profile
**GitHub:** [@matt-presti](https://github.com/matt-presti)

All project repositories include comprehensive documentation, clean code architecture, and detailed setup instructions. View complete source code, technical documentation, and development progress on GitHub.

---

*This portfolio demonstrates practical application of enterprise development patterns, machine learning techniques, and modern software engineering practices. Each project showcases different aspects of full-stack development and data science capabilities.*
