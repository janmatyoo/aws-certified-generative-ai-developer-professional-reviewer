## 📋 AWS Certified GenAI Developer – Professional: Exam Domains

---

### 🔹 Domain 1: Foundation Model Integration, Data Management, and Compliance (31%)

**What it covers:**  
This domain aligns to the day-to-day work of a GenAI developer across the AI lifecycle: **choose the right foundation model (FM)**, **build data workflows**, **implement vector stores + retrieval**, **engineer prompts**, and **maintain governance/compliance** so the system stays reliable in production.

**How this shows up in real projects (high level):**
- **FM integration**: pick an FM that matches the use case, configure inference behavior, and integrate it safely into an app workflow.
- **Data management**: ingest, clean, transform, and validate data so downstream retrieval and generation is trustworthy.
- **RAG foundations**: create embeddings, store them in a vector index, and design retrieval that returns the *right* context quickly.
- **Prompt systems**: build prompts/templates and guard against brittleness with versioning, testing, and iteration.
- **Governance + compliance**: apply data controls (classification, access, retention) and quality controls (traceability, evaluation signals).

**For this content domain, make sure you can do the following:**
- **Select and configure FMs** based on business needs (quality, latency, cost, modalities, context window, tooling constraints).
- **Build data processing and validation pipelines** (dedupe, chunking, metadata, schema/quality checks).
- **Implement efficient vector databases and retrieval systems** (indexing strategy, filtering, reranking, hybrid search when needed).
- **Create effective prompt engineering strategies** (prompt structure, examples, tool-use patterns, prompt versioning).
- **Maintain governance and quality control** across the AI system (data access controls, auditability, evaluation and feedback loops).

**Key areas (exam-style):**
- **Foundation model selection & integration**
  - Model fit (task + modality), inference configuration, and integration patterns
- **Data ingestion, preprocessing, and validation**
  - ETL/ELT workflows, document parsing, chunking strategies, metadata hygiene
- **Embeddings, vector stores, and retrieval design**
  - Embedding choices, index design, similarity search, filters, reranking, hybrid retrieval
- **Prompt engineering fundamentals**
  - Prompt templates, few-shot patterns, tool calling/function calling patterns, prompt management
- **Compliance, governance, and quality**
  - Data classification, access control, encryption, retention, lineage, and quality monitoring signals

**AWS services/features you’ll likely see in Domain 1 scenarios (examples):**
- **Amazon Bedrock**
  - Model access & inference, embeddings, and managed GenAI building blocks (e.g., knowledge base/RAG features)
- **Amazon SageMaker**
  - Model hosting and customization workflows where Bedrock-managed models aren’t the right fit
- **Amazon S3 + AWS Glue**
  - Storage and data transformation pipelines for documents and datasets
- **AWS Lake Formation + AWS KMS**
  - Data governance controls and encryption foundations for compliance requirements
- **Vector stores (common options)**
  - Amazon OpenSearch (vector search), relational options with vector support, or purpose-built vector databases

🧠 **Exam cues (what the question is really asking):**
- “Choose the best FM for business constraints (cost/latency/quality/modality)” → **FM selection & configuration**
- “Ingest and validate documents before RAG” → **Data processing + chunking + metadata + quality checks**
- “Improve retrieval quality / reduce irrelevant context” → **Indexing + filters + reranking + hybrid search**
- “Standardize prompts across teams and releases” → **Prompt templates + versioning + evaluation**
- “Meet compliance requirements for training/RAG data” → **Governance (access, encryption, retention, auditability)**

**📚 References (official docs):**
- [Amazon Bedrock User Guide](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html)
- [Amazon Bedrock Knowledge Bases (RAG)](https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html)
- [Amazon S3 Security](https://docs.aws.amazon.com/AmazonS3/latest/userguide/security.html)
- [AWS Lake Formation — Data governance](https://docs.aws.amazon.com/lake-formation/latest/dg/what-is-lake-formation.html)

---

### 🔹 Domain 2: Implementation and Integration (26%)

**What it covers:**  
This domain covers building and integrating GenAI applications with AWS services, implementing RAG architectures, and orchestrating multi-step workflows.

**Key areas:**
- RAG implementation patterns
- Agent development and orchestration
- API and service integration
- Multi-model workflows
- Event-driven architectures
- Frontend and backend integration

---

### 🔹 Domain 3: AI Safety, Security, and Governance (20%)

**What it covers:**  
This domain addresses security best practices, responsible AI principles, governance frameworks, and safeguards for GenAI applications.

**Key areas:**
- IAM policies and access control
- Encryption and data protection
- Network security and VPC isolation
- Responsible AI principles
- Bias detection and mitigation
- Content moderation and guardrails
- Audit logging and compliance

---

#### 1️⃣ Amazon Bedrock Guardrails

**What it is:**  
Amazon Bedrock Guardrails is a configurable safeguard framework that helps you build responsible and safe generative AI applications. It provides policies to filter harmful content, protect privacy, block undesired topics, and reduce hallucinations. Guardrails work at both input (prompt) and output (response) levels and can be applied across multiple foundation models—including third-party models outside Bedrock—using the `ApplyGuardrail` API.

**Used for:**
- **Content filtering:** Detect and block harmful content (hate speech, violence, sexual content, insults, misconduct, prompt attacks) with adjustable sensitivity thresholds
- **Denied topics:** Block specific topics that are off-limits for your application (e.g., legal advice, medical diagnosis, competitor mentions)
- **Word filters:** Block profanity, competitor names, or any custom words/phrases you define
- **Sensitive information protection:** Redact or block PII (names, emails, SSNs, credit cards) using both ML-based detection and custom regex patterns
- **Hallucination detection:** Use contextual grounding checks to ensure model outputs are grounded in source documents (critical for RAG applications)
- **Automated reasoning checks:** Detect and prevent logical errors, mathematical mistakes, or factual inconsistencies
- **IAM-based enforcement:** Mandate guardrail usage across all model invocations through IAM policies for organizational compliance

**When to use it:**
- ✅ Building user-facing applications (chatbots, assistants) requiring safety and content moderation
- ✅ Regulated industries (healthcare, finance, legal) where PII exposure or misinformation has serious consequences
- ✅ RAG or knowledge base applications where responses must be grounded in source content
- ✅ Need consistent safety policies across multiple models (Bedrock models, SageMaker models, third-party like OpenAI or Gemini)
- ✅ Organizational compliance requires mandatory guardrails enforced through IAM policies
- ✅ Early in development to proactively prevent safety issues before production

**When NOT to use it:**
- ❌ Creative or exploratory applications where strict filtering hampers flexibility (creative writing, brainstorming)
- ❌ Internal trusted environments with minimal safety requirements where unconstrained outputs are acceptable
- ❌ Extremely latency-sensitive applications where guardrail overhead is unacceptable (though most checks are fast)
- ❌ When false positives would severely harm user experience—consider "detect-only" mode first to calibrate
- ❌ Content or languages not supported by guardrails (verify regional and language support)

🧠 **Exam cue:**  
"Prevent hallucinations in RAG applications" → **Contextual Grounding Checks** in **Guardrails**  
"Block PII or sensitive data in model outputs" → **Sensitive Information Filters** in **Guardrails**  
"Enforce safety policies across all model invocations" → **IAM-based Guardrail enforcement**  
"Detect prompt injection attacks" → **Prompt Attack filtering** in **Guardrails**  
"Apply same safety policies to third-party models" → **ApplyGuardrail API**

**📚 References:**
- [AWS Documentation: Guardrails for Amazon Bedrock User Guide](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html)
- [AWS Product Page: Amazon Bedrock Guardrails](https://aws.amazon.com/bedrock/guardrails/)
- [AWS Blog: Safeguard generative AI applications with Amazon Bedrock Guardrails](https://aws.amazon.com/blogs/machine-learning/safeguard-generative-ai-applications-with-amazon-bedrock-guardrails/)
- [AWS Blog: IAM Policy-based enforcement to deliver safe AI interactions](https://aws.amazon.com/blogs/machine-learning/amazon-bedrock-guardrails-announces-iam-policy-based-enforcement-to-deliver-safe-ai-interactions/)
- [AWS Blog: Protect against encoding-based attacks with Guardrails](https://aws.amazon.com/blogs/security/protect-your-generative-ai-applications-against-encoding-based-attacks-with-amazon-bedrock-guardrails/)

---

### 🔹 Domain 4: Operational Efficiency and Optimization for Generative AI Applications (12%)

**What it covers:**  
This domain focuses on optimizing GenAI applications for cost, performance, latency, and scalability in production environments.

**Key areas:**
- Token usage optimization
- Caching strategies
- Model selection for cost-performance balance
- Throughput and concurrency management
- Resource allocation and scaling
- Latency reduction techniques

---

### 🔹 Domain 5: Testing, Validation, and Troubleshooting (11%)

**What it covers:**  
This domain covers evaluation methodologies, testing strategies, quality assurance, and troubleshooting techniques for GenAI applications.

**Key areas:**
- Model evaluation metrics
- Prompt testing and validation
- A/B testing and experimentation
- Performance benchmarking
- Debugging and error analysis
- Quality monitoring in production
- Remediation strategies

---

## 📊 Domain Weight Summary

| Domain | Weight | Priority |
|--------|--------|----------|
| Domain 1: Foundation Model Integration, Data Management, and Compliance | 31% | 🔴 Highest |
| Domain 2: Implementation and Integration | 26% | 🔴 High |
| Domain 3: AI Safety, Security, and Governance | 20% | 🟡 Medium-High |
| Domain 4: Operational Efficiency and Optimization | 12% | 🟢 Medium |
| Domain 5: Testing, Validation, and Troubleshooting | 11% | 🟢 Medium |

---

## 📝 Notes

- **Total exam questions:** 85 (multiple choice and multiple response)
- **Exam duration:** 205 minutes
- **Beta exam cost:** $150 USD
- **Languages available:** English and Japanese
- **Exam code:** AIP-C01

---
