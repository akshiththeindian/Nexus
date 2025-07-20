![Python](https://img.shields.io/badge/python-3.10+-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-Demonstrator-yellow)


# Nexus.ai - Multi-Model AI Aggregation Engine


# Table of Contents
## 1. [What is Nexus.ai?](#what-is-nexusai)
## 2. [Operational Mode](#-operational-note-demonstration-only-mode)
## 3. [Features](#-features)
## 4. [Getting Started](#getting-started)
## 5. [Architecture](#-architecture)
## 6. [Security Design](#security-design)
## 7. [Future Enhancements](#future-enhancements)
## 8. [Run Tests (Coming Soon)](#8-run-tests-coming-soon)
## 9. [License](#9-license)




1. # What is Nexus.ai?

Nexus.ai is a sophisticated AI engine designed to aggregate and analyze responses from multiple AI models and traditional search engines and media, providing a comprehensive and nuanced understanding 
of user queries.

It integrates web scraping capabilities for real-time data retrieval, supports secure data encryption, and offers advanced response aggregation techniques to deliver the best possible answers.

Nexus.ai is built to be extensible and infinitely scalable, allowing for easy integration of new AI models and data sources, making it a versatile tool for developers and researchers alike, but it is also designed to be user-friendly, with a focus on providing clear and actionable insights.

Nexus.ai is not just a tool for AI enthusiasts; it is a powerful platform that can be used in various applications, from academic research to business intelligence, and it aims to democratize access to advanced AI capabilities by making Gen AI replies more accurate and more correct. 

Nexus.ai is an advanced AI engine that aggregates and analyzes responses from multiple AI models and traditional search engines and media, providing a comprehensive and nuanced understanding of user queries. It also includes powerful 256-bit AES encryption for secure data handling, ensuring that 
sensitive information is protected throughout the process.

It combines the power of multiple AI models with the richness of web data, enabling users to gain deeper insights and make more informed decisions, using AI Model Debating you will get the best possible answer to your question, by combining the strengths of different AI models and traditional 
search engines and media.



2. # ⚠️ Operational Note: Demonstration-Only

This project is a secure **proof-of-concept** designed to demonstrate:
- Modular orchestration of external AI APIs
- Full stack encryption and key rotation logic
- Logging, security, and AWS-based archival infrastructure
- Response aggregation algorithms

## Warning: No live API keys are included. No external models are called.  
All orchestration logic is functional but locked under safety mode. Please do not run in production without adding your own keys and do not alter logic.

This approach ensures:
- Credential security
- Cost control
- Safety for demonstration and portfolio use

To “arm” the system, a future user would:
- Plug in valid API keys via secure vault or environment file
- Enable the active dispatch logic in `engine.py` and `api_secrets.py`
- Deploy to a secure environment with network access
This design prioritizes security and safety while showcasing the system's 
capabilities. 


3. # Features

- Multi-Model Integration:   
Connects with GPT-4o, Claude, Gemini, Perplexity, and any future model via pluggable connectors. As long as you have the API Keys and the Connectors for the code, you can add as many models as needed. 

- Real-Time Web Scraping:  
Enriches context using live search results from Google, Bing, or DuckDuckGo. 

- Secure Aggregation with AES-256: 
Nexus is built with safety and security in mind. We use 256 bit encryption to encrypt and decrypt all responses and to make sure that there is no data leakage. All prompts and results are encrypted using advanced symmetric encryption.

- Response Ranking Algorithms:   
Aggregates using TF-IDF, consensus scoring, and weighted preferences.

- Cloud-Native Deployment Ready:   
Compatible with AWS S3, Lambda, and DynamoDB for logs, backups, and scalability. Nexus is built with scalability in mind and to that degree can be made to be infinitely scalable using AWS. Nexus uses S3, EC2, Glacier, RDS, DynamoDB, Aurora, Athena and other AWS Services to ensure this is a viable product to the absolute highest standards.

- User Access Controls + Audit Logging:   
Nexus was built on the idea that comprehensive logging and auditing are essential for transparency and security. Nexus has Built-in key validation, scope enforcement, and audit trails with TTL retention.

- Webhook & Admin Extensibility: 
Lightweight admin tools and event-driven webhook support.

- Safe Demonstration Mode:  
No API calls until secrets are injected. All logic tested, dry-run friendly.



4. # Getting Started:
# 1. Clone repository
git clone https://github.com/akshiththeindian/nexus.git
cd nexus


# 2. Install dependencies
In the requirements.txt file,
pip install -r requirements.txt


# 3. Setup environment
cp .env.example .env
# Then open `.env` and insert your real API keys (or leave blank for demo mode)


# 4. Edit .env to add your API keys 

# 5. Run the app
python Nexus_FlaskApp.py



5. ## Architecture
Diagram:
                             
   <img width="1024" height="1536" alt="ChatGPT Image Jul 20, 2025, 02_01_38 AM" src="https://github.com/user-attachments/assets/bc333f15-e15a-44a0-9c3c-09fa6ee69fc1" />





6. # Security Design

Nexus.ai is built with zero-trust principles and multi-layered protection:
- Environment Variable Isolation: Secrets are never hardcoded.
- AES-256 Encryption: All input/output can be encrypted end-to-end.
- API Key Validation: All requests require scoped API keys.
- Rate Limiting: Flask-Limiter protects against abuse and denial-of-service.
- HTTPS Enforcement: Requests without HTTPS are denied.
- TTL Audit Logs: Every event is logged with retention controls via DynamoDB.
- Unarmed Demo Mode: No production calls are ever made until secrets are injected.


 7. # Future Enhancements

- Add support for OpenRouter and LM Studio custom endpoints
- Frontend dashboard with model voting visualizations
- Integration with HuggingFace Spaces for no-code UI
- CLI interface for headless queries
- Docker container for fast local testing




## ✅ Run Tests (Coming Soon)
This repo includes stubs for future pytest-based testing:

```bash
pytest tests/


# LICENSE (MIT)
MIT License

Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy.
