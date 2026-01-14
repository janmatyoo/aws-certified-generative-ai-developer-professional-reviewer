# AWS Certified Generative AI Developer – Professional (AIP-C01) Study Guide

This repository contains structured study notes and references for the  
**AWS Certified Generative AI Developer – Professional** certification.

The goal is to understand **how to design, build, secure, deploy, and optimize**
production-ready Generative AI applications on AWS.

---

## Contents
- [Exam Overview](#exam-overview)
- [Amazon Bedrock](#amazon-bedrock)
- [Foundation Models](#foundation-models)
- [Prompt Engineering](#prompt-engineering)
- [Retrieval-Augmented Generation (RAG)](#retrieval-augmented-generation-rag)
- [Embeddings and Vector Stores](#embeddings-and-vector-stores)
- [Amazon SageMaker](#amazon-sagemaker)
- [Generative AI Application Architecture](#generative-ai-application-architecture)
- [Security, Governance, and Responsible AI](#security-governance-and-responsible-ai)
- [Monitoring, Evaluation, and Optimization](#monitoring-evaluation-and-optimization)
- [Deployment and DevOps](#deployment-and-devops)
- [Cost Optimization](#cost-optimization)
- [Exam Strategy Notes](#exam-strategy-notes)

---

## Exam Overview
- **Exam level:** Professional
- **Exam format:** 85 multiple-choice and multiple-response questions
- **Duration:** ~205 minutes
- **Delivery:** Pearson VUE (online proctored or test center)
- **Language:** English (Japanese available)

- **Target audience:** Developers with hands-on experience building and deploying
  production-grade Generative AI applications on AWS

- **Primary services covered:**
  - Amazon Bedrock
  - Amazon SageMaker
  - IAM, KMS, VPC
  - OpenSearch, S3, Lambda, API Gateway
  - Monitoring and deployment services

- **Exam focus:**
  - Designing end-to-end Generative AI architectures
  - Making tradeoffs between cost, latency, scalability, and model quality
  - Choosing between managed services (Bedrock) and custom solutions (SageMaker)
  - Applying security, governance, and responsible AI principles

- **Question style:**
  - Long, scenario-based questions
  - Multiple constraints (security, cost, performance, compliance)
  - Emphasis on “best” or “most appropriate” solution, not just what works


---

## Amazon Bedrock
- Purpose of Amazon Bedrock and supported use cases
- Available foundation model providers and model types
- Model invocation patterns and request flow
- Agents and Knowledge Bases architecture
- Provisioned throughput vs on-demand inference
- IAM permissions and resource access control

---

## Foundation Models
- Characteristics of foundation models
- Text, image, and multimodal model capabilities
- Model selection criteria: quality, latency, cost
- Prompt engineering vs fine-tuning decision points
- Limitations and risks of foundation models

---

## Prompt Engineering
- Prompt structure and roles
- Zero-shot and few-shot prompting strategies
- Prompt templates and parameter tuning
- Guardrails for output control
- Techniques for reducing hallucinations
- Prompt versioning and testing approaches

---

## Retrieval-Augmented Generation (RAG)
- Purpose of RAG in enterprise applications
- End-to-end RAG architecture on AWS
- Data ingestion and preprocessing workflows
- Chunking strategies and retrieval relevance
- Query orchestration and response synthesis
- Managed RAG with Bedrock Knowledge Bases vs custom implementations

---

## Embeddings and Vector Stores
- What embeddings represent and how they are generated
- Similarity search concepts and distance metrics
- Vector indexing and retrieval strategies
- AWS-supported vector store options
- Performance, scalability, and accuracy tradeoffs

---

## Amazon SageMaker
- When to use SageMaker vs Amazon Bedrock
- Training, tuning, and hosting generative models
- Real-time vs asynchronous inference
- Endpoint scaling and availability
- Model monitoring and observability

---

## Generative AI Application Architecture
- Reference architectures for GenAI applications
- Stateless and stateful design considerations
- API-based and event-driven integration patterns
- Multi-model orchestration
- Error handling, retries, and fallback strategies

---

## Security, Governance, and Responsible AI
- IAM best practices for GenAI workloads
- Data privacy and isolation strategies
- Encryption in transit and at rest
- Responsible AI principles and safeguards
- Content moderation and policy enforcement
- Audit logging and compliance controls

---

## Monitoring, Evaluation, and Optimization
- Measuring model quality and relevance
- Prompt and response evaluation techniques
- Latency, throughput, and error monitoring
- Logging inputs, outputs, and metadata
- Continuous improvement feedback loops

---

## Deployment and DevOps
- CI/CD pipelines for GenAI applications
- Infrastructure as Code approaches
- Versioning models, prompts, and datasets
- Deployment strategies and rollback mechanisms

---

## Cost Optimization
- Primary cost drivers in GenAI solutions
- Token usage and prompt efficiency
- Model selection based on cost constraints
- Caching and reuse strategies
- Tradeoffs between managed and custom solutions

---

## Exam Strategy Notes
- Identifying key requirements in scenario questions
- Mapping business needs to AWS services
- Recognizing common distractors
- Prioritizing security, scalability, and cost efficiency
