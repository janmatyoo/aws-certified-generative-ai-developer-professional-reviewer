## 📋 AWS Certified GenAI Developer – Professional: Exam Domains

---

### 🔹 Domain 1: Foundation Model Integration, Data Management, and Compliance (31%)

**What it covers:**  
This domain focuses on selecting and integrating foundation models, managing data pipelines for GenAI applications, and ensuring compliance with data governance requirements.

**Key areas:**
- Foundation model selection and integration
- Data ingestion and preprocessing
- Vector databases and embeddings
- Knowledge base design
- Data compliance and governance
- Prompt engineering fundamentals

---

#### 1️⃣ Amazon Bedrock Data Automation

**What it is:**  
A managed AWS service that automates transforming unstructured multimodal content (documents, images, video, audio) into structured formats using generative AI. Provides a unified API-driven interface, eliminating the need to orchestrate multiple AI models. Includes built-in safeguards like confidence scores and visual grounding to ensure accuracy and trustworthiness.

**Used for:**
- **Intelligent Document Processing (IDP):** Automatically classify, extract, normalize, and validate business-specific data from PDFs, images, forms, and documents without building custom pipelines
- **Media analysis:** Scene summaries from video, content moderation (unsafe/explicit content detection), text extraction from video frames or images, brand/advertisement recognition
- **Audio insights:** Extract sentiments, intents, summaries, and topics from audio conversations (meetings, calls, earnings reports)
- **RAG workflows and AI assistants:** Acts as a parsing layer to convert raw multimodal data into structured insights for retrieval-augmented generation pipelines and knowledge bases
- **Multi-agent collaboration:** Used in investment research assistants where BDA processes unstructured data (earnings calls, documents) to feed structured insights to specialized agents

**When to use it:**
- ✅ Large volumes of unstructured/multimodal content need automated conversion to structured formats
- ✅ Building RAG systems or AI assistants where structured data improves search and context quality
- ✅ Need unified API for all modalities (documents, images, video, audio) without orchestrating multiple services
- ✅ Require confidence scores and visual grounding for quality assurance and human-in-the-loop workflows
- ✅ Fast time-to-value without building and maintaining custom extraction pipelines

**When NOT to use it:**
- ❌ Data is already strictly structured (CSV, JSON) and no multimodal extraction required
- ❌ Need ultra-low latency synchronous processing (BDA uses asynchronous job model for some tasks)
- ❌ Simple OCR-only needs that don't require GenAI-powered understanding
- ❌ Extremely custom models/extractions beyond BDA's capabilities that require specialized pipelines

🧠 **Exam cue:**  
"Transform unstructured multimodal content into structured data with unified API" → **Bedrock Data Automation**  
"IDP workflows with confidence scores, visual grounding, and safeguards" → **Bedrock Data Automation**  
"Multi-agent systems needing structured insights from raw documents/media" → **Bedrock Data Automation**

**📚 References:**
- [AWS Documentation: Transform unstructured data using Amazon Bedrock Data Automation](https://docs.aws.amazon.com/bedrock/latest/userguide/bda.html)
- [AWS Blog: Building an AI-powered assistant for investment research with multi-agent collaboration](https://aws.amazon.com/blogs/machine-learning/part-3-building-an-ai-powered-assistant-for-investment-research-with-multi-agent-collaboration-in-amazon-bedrock-and-amazon-bedrock-data-automation/)

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
