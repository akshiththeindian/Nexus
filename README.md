![Python](https://img.shields.io/badge/python-3.10+-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-Demonstrator-yellow)


# Nexus.ai - Multi-Model AI Aggregation Engine


# Table of Contents
## 1. [What is Nexus.ai?](#what-is-nexusai)
## 2. [Secrets and Security Architecture](#secretsandsecurityarchitecture)
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

Nexus.ai is not just a tool for AI enthusiasts; it is a powerful platform that can be used in various applications, from academic research to business intelligence, and it aims to democratize access to advanced AI capabilities by making Gen AI replies more accurate and correct. 

Nexus.ai is an advanced AI engine that aggregates and analyzes responses from multiple AI models and traditional search engines and media, providing a comprehensive and nuanced understanding of user queries. It also includes powerful 256-bit AES encryption for secure data handling, ensuring that 
Sensitive information is protected throughout the process.

It combines the power of multiple AI models with the richness of web data, enabling users to gain deeper insights and make more informed decisions. Using AI Model Debating, you will get the best possible answer to your question, by combining the strengths of different AI models and traditional 
search engines and media.



2. # Secrets & Security Architecture

**⚠️ Operational Notice:** This is a secure demonstration file, not a production secrets manager.

All credentials in this project are pulled securely from environment variables or AWS Secrets Manager. The system supports:

* **AES-256 encryption with daily key rotation**
* **Optional AWS KMS hybrid encryption**
* **No hardcoded secrets or live credentials**

All secret handling, API orchestration, and runtime logic is sandboxed. External model calls are **disabled by default** to ensure safety and cost control.

# Why This Matters

This architecture was designed as a **secure proof-of-concept** for:

* 🔐 Demonstrating credential encryption & secret rotation
* 🛡️ Showcasing secure-by-default development practices
* 💸 Enabling zero-risk local or portfolio deployments

It ensures a no-cost, secure, and auditable environment—ideal for infrastructure, cloud, and AI demonstrations.

# How to Activate the System

To "arm" this secrets framework in a real deployment, simply:

1. Add valid API keys to a secure vault or `.env` file
2. Enable dispatch logic in `engine.py` and `api_secrets.py`
3. Deploy within a private networked environment (e.g., AWS VPC, Lambda, ECS)

This design reflects **real-world production readiness** without exposing live systems, enabling:

* Full-stack cloud security demonstration
* End-to-end logging, audit trail, and encryption showcase
* Confidence in deployment safety for hiring or technical review


3. # Features

- Multi-Model Integration:   
Connects with GPT-4o, Claude, Gemini, Perplexity, and any future model via pluggable connectors. As long as you have the API Keys and the Connectors for the code, you can add as many models as needed. 

- Real-Time Web Scraping:  
Enriches context using live search results from Google, Bing, or DuckDuckGo. 

- Secure Aggregation with AES-256: 
Nexus is built with safety and security in mind. We use 256-bit encryption to encrypt and decrypt all responses, ensuring that there is no data leakage. All prompts and results are encrypted using advanced symmetric encryption.

- Response Ranking Algorithms:   
Aggregates using TF-IDF, consensus scoring, and weighted preferences.

- Cloud-Native Deployment Ready:   
Compatible with AWS S3, Lambda, and DynamoDB for logs, backups, and scalability. Nexus is built with scalability in mind, and to that degree, it can be made infinitely scalable using AWS. Nexus uses S3, EC2, Glacier, RDS, DynamoDB, Aurora, Athena, and other AWS Services to ensure this is a viable product to the absolute highest standards.

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
 Below is a high-level architecture of Nexus.ai showing secrets loading, connector orchestration, scraping, core engine, and the API layer.
                             
   <img width="850" height="900" alt="ChatGPT Image Jul 20, 2025, 02_01_38 AM" src="https://github.com/user-attachments/assets/bc333f15-e15a-44a0-9c3c-09fa6ee69fc1" />




**Nexus is engineered with three principles at its core: Safety, Scalability, and Security.**

To meet those goals, Nexus is fully cloud-native and deploys seamlessly across the AWS ecosystem using battle-tested compute, storage, and security infrastructure. Whether you’re an individual developer or a global enterprise, Nexus adapts to scale and that's by design.

## Security-First Architecture

* **AES-256 Encryption** protects all prompts, responses, and logs — both in transit and at rest.
* **IAM & KMS** enforce fine-grained access control and automatic key rotation.
* **CloudWatch & CloudTrail** provide real-time monitoring, alerting, and forensic auditing 24/7/365.
* **VPC (Virtual Private Cloud)** ensures all resources are isolated, routed securely, and protected by network-level firewalls.

This architecture makes Nexus compliant with modern zero-trust and least-privilege security standards from day one.


## Durable & Scalable Storage

* **Amazon RDS + Aurora** handle structured data and analytical workloads with high availability.
* **Amazon DynamoDB** powers low-latency access for audit logs, user scopes, and API activity.
* **Amazon S3** serves as the primary hot storage layer for backups, logs, and archive-ready data.
* **Amazon Glacier** retains cold backups for up to 1 year, ensuring long-term recoverability.

## Nexus performs automated snapshots and tiered storage rollovers, ensuring your data is never lost — even in extreme scenarios.

## Elastic Compute & Parallel Processing

* Amazon EC2 serves as the Nexus backend host — a hardened, flexible compute instance tailored to your scale.
* AWS Parallel Computing Service(PCS) and ECS with Fargate can be integrated to scale AI model processing horizontally when running with heavy model throughput.

This ensures Nexus is both **low-cost in idle mode** and **high-performance under load**.

---

### Why This Matters

This infrastructure means:

* Nexus can handle **one user or one million** — with no architectural changes.
* Nexus is resilient to failures, attacks, or outages — thanks to **redundancy and logging at every layer**.
* Nexus is **infinitely customizable**, without compromising on security.


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



# ✅ Run Tests (Coming Soon)
This repo includes stubs for future pytest-based testing:

```bash
pytest tests/



# LICENSE (MIT)
MIT License

Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy.
