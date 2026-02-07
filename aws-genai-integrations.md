# AWS GenAI Integrations

This document provides a curated list of AWS services and how they interact, specifically for Generative AI (GenAI) use cases. Each entry highlights the key service combination, its role, and a brief explanation of how the services work together to support GenAI workflows.

---

## LLM Prompt Template

Use this template to ask an LLM to generate a new entry. Replace the variables with your specific scenario:

```
You are an expert in AWS and Generative AI architectures.

Role of the LLM: <INSERT LLM ROLE HERE>
AWS Services Involved: <LIST AWS SERVICES HERE>
Context & Integration: <DESCRIBE HOW THE SERVICES ARE USED AND INTEGRATED IN THE GENAI WORKFLOW>

Generate a structured entry in the following Markdown-ready format:

### <SERVICE COMBINATION>
- **Role:**
  - <SERVICE 1>: <DESCRIBE THE FUNCTION OF THE SERVICE IN THE CONTEXT OF THE LLM>
  - <SERVICE 2>: <DESCRIBE THE FUNCTION OF THE SERVICE IN THE CONTEXT OF THE LLM>
  - ...
- **Integration:**
  - <EXPLAIN HOW THE SERVICES INTERACT OR COMPLEMENT EACH OTHER>
- **Use Case:**
  - <DESCRIBE THE PRACTICAL SCENARIO OR WORKFLOW>

Must Do (Positive Instructions)
- Use **simple, summarized explanations**
- Prefer **bullet points**
- Explain concepts in **plain language**
- Stay **focused on the provided context**
- Base explanations on **official AWS documentation or well-established AWS behavior**
- Optimize for **clarity and correctness**

Must Avoid (Negative Instructions)
- Do **not** use heavy jargon or walls of text
- Do **not** give generic cloud explanations
- Do **not** invent features, behaviors, or capabilities
- Do **not** assume missing requirements
- Do **not** over-explain beyond what is necessary
```

---

## Integrations

### Amazon S3 + Amazon Macie
- **Role:**
  - **Amazon S3:** Stores large datasets for GenAI model training.
  - **Amazon Macie:** Provides automated sensitive data discovery in S3.
- **Integration:**
  - Macie scans S3 objects to identify sensitive data.
  - S3 Lifecycle policies enforce retention limits for compliance.
- **Use Case:**
  - Ensures that training datasets for GenAI models comply with data privacy and regulatory requirements.

---

### AWS AppConfig + AWS Step Functions + Regional Endpoints
- **Role:**
  - **AWS AppConfig:** Provides dynamic configuration updates at runtime without redeploying applications.
  - **Step Functions:** Orchestrates serverless workflows with automatic error handling and failover.
  - **Regional Endpoints:** Enable reliable, cross-region support.
- **Integration:**
  - AppConfig delivers runtime configuration changes.
  - Step Functions coordinates tasks across services, ensuring resilience and retries.
  - Regional endpoints allow both services to operate consistently across multiple regions.
- **Use Case:**
  - Implement flexible and resilient GenAI applications with dynamic configuration and fault-tolerant workflows while minimizing operational overhead.

---

### AgentCore Identity + Microsoft Entra ID

- **Role:**
  - **AgentCore Identity:** Supports OIDC authentication as a service without requiring additional infrastructure.  
  - **Microsoft Entra ID:** Acts as the inbound identity provider (IdP) for OIDC authentication.  
- **Integration:**
  - Configure AgentCore Identity with the Microsoft v2.0 OIDC metadata discovery URL.  
  - Set allowed audiences to match the application ID from the Microsoft Entra ID registration.  
  - This built-in integration enables direct OIDC authentication without custom code.  
- **Use Case:**
  - Provides seamless and secure authentication for applications using Microsoft Entra ID with minimal operational overhead.

---

### AWS Step Functions + Amazon Bedrock
- **Role:**
  - **AWS Step Functions:** Orchestrates the LLM workflow using a state machine with clear steps, choices, and retries.
  - **Amazon Bedrock:** Provides access to foundation models (FMs) used for reasoning, planning, and generating responses.
- **Integration:**
  - Step Functions calls Bedrock model invocations as tasks within the state machine.
  - Each state represents a ReAct step (reason, act, observe).
  - Built-in error handling (Retry, Catch) manages model timeouts, throttling, or failures.
- **Use Case:**
  - Implements a reliable, multi-step GenAI reasoning workflow where the LLM breaks down a complex task, executes actions step by step, and recovers gracefully from errors.

---

### PreProcessingTrace + OrchestrationTrace + PostProcessingTrace

- **Role:**
  - **PreProcessingTrace:** Details about the pre-processing step, in which the agent contextualizes and categorizes user inputs.
  - **OrchestrationTrace:** Details about the orchestration step, in which the agent determines the order in which actions are executed and which knowledge bases are retrieved.
  - **PostProcessingTrace:** Details about the post-processing step, in which the agent shapes the response.

- **Integration:**
  - These traces form an end-to-end pipeline: **PreProcessingTrace → OrchestrationTrace → PostProcessingTrace**.
  - Each trace feeds structured metadata into the next stage, enabling systematic monitoring and debugging of the agent’s reasoning.
  - The golden dataset validation is integrated at the post-processing stage to detect inconsistencies or hallucinations, closing the feedback loop.

- **Use Case:**
  - Provides full visibility into LLM reasoning for enterprise applications requiring trust and auditability.
  - Helps developers and operators debug, validate, and improve prompts, model choices, and output transformations.
  - Enables detection of reasoning failures, ensuring higher reliability in automated decision-making or conversational agents.













Role of the LLM: You are an expert in AWS Services and Generative AI
AWS Services Involved: You automatically identify it based on the context and integration
Context & Integration: xxx

Generate a structured entry in the following Markdown-ready format:

### <SERVICE COMBINATION> - STRICTLY RETURN RESULT AS MARKDOWN SYNTAX
- **Role:**
  - <SERVICE 1>: <DESCRIBE THE FUNCTION OF THE SERVICE IN THE CONTEXT OF THE LLM>
  - <SERVICE 2>: <DESCRIBE THE FUNCTION OF THE SERVICE IN THE CONTEXT OF THE LLM>
  - ...
- **Integration:**
  - <EXPLAIN HOW THE SERVICES INTERACT OR COMPLEMENT EACH OTHER>
- **Use Case:**
  - <DESCRIBE THE PRACTICAL SCENARIO OR WORKFLOW>

STRICTLY! Must Do (Positive Instructions)
- Use **simple, summarized explanations**
- Prefer **bullet points**
- Explain concepts in **plain language**
- Stay **focused on the provided context**
- Base explanations on **official AWS documentation or well-established AWS behavior**
- Optimize for **clarity and correctness**

STRICTLY! Must Avoid (Negative Instructions)
- Do **not** use heavy jargon or walls of text
- Do **not** give generic cloud explanations
- Do **not** invent features, behaviors, or capabilities
- Do **not** assume missing requirements
- Do **not** over-explain beyond what is necessary








