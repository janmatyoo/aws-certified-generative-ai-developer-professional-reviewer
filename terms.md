Bedrock

terms:
- temperature
- top-p
- top-k
- inference
- Model cascading

features:
- Bedrock Model Evaluations
- CountTokens API 
- ConverseStream API
- Converse API

OpenSearch
- vector database and applies topic-based segmentation by isolating content into per-topic indices

Knowledge Base
- store and search data by meaning
- use for retrieval-augmented generation (RAG)
- use for knowledge-based question answering
- use for summarization using proprietary data
- use for chatbots
- use for document-aware chatbots
- use for semantic document search
- use for matching queries to relevant content
- use for retrieval in RAG workflows

Guardrails
- PII masking/removal
- they do not satisfy a requirement for human review and approval
- help filter content and improve safety
- topic filtering and PII masking, and invoke the managed prompt from all applications.

Provisioned throughput 
- provide consistent
- higher throughput for a specific Bedrock model with minimal operational overhead
- reserved capacity
- reduce throttling during predictable peaks

Prompt Management
- create reusable, parameterized prompts with versioning and an approval workflow
- defines the agent role and includes explicit JSON output instructions (schema and example)

Strands API 


SageMaker

Model Registry
- provides centralized versioning and metadata for model artifacts
- supports an approval workflow to control which versions can be deployed

deployment guardrails
- provide controlled traffic shifting to a new model version
- can automatically roll back when CloudWatch alarms indicate failures or regressions


AWS

services:
- CodePipeline
- CodeBuild
- CodeDeploy
- API Gateway WebSocket API 
- Step Functions 
- Comprehend
- SQS
- Strands API 

CloudWatch Synthetics
- provides continuous, automated checks that simulate end-to-end usage

DynamoDB
- Storing human feedback for model evaluations
- full conversation history

Titan
multimodal embeddings model is designed to embed images, text, or both into vector representations that can be stored and queried in a vector database

Amplify
- accelerates delivery of a production-ready, accessible web interface and commonly used front-end capabilities (such as authentication)
- managed service for building and deploying web and mobile applications
- supports fullstack development with Amplify Studio
- includes features for authentication, storage, and deployment
- integrates with other AWS services for a comprehensive development environment

CloudFront
- content delivery network
- distributed network of servers that deliver content to users based on their location
- improves performance and reliability of web applications
- can be used to cache content and reduce load on origin servers
- can be used to secure content with HTTPS


AWS Glue Data Quality
- designed for automated, rule-based validation and can be embedded directly into Glue jobs