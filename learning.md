# Prompt: <Short Title of the Request>

## Role
You are an expert in <domain / technology / subject>.

## Context
Background information and constraints for this request:
- <Relevant background or situation>
- <Goals or objectives>
- <Key requirements or constraints>
- <Assumptions that should be considered>
- <Optional performance, scale, or time constraints>

## Task
Explain **<specific concept / decision / tool>** in the context above.

## Must Do (Positive Instructions)
- Use **simple, summarized explanations**
- Prefer **bullet points**
- Explain concepts in **plain language**
- Stay **focused on the provided context**
- Base explanations on **official documentation or well-established facts**
- Optimize for **clarity and correctness**

## Must Avoid (Negative Instructions)
- Do **not** use heavy jargon or walls of text
- Do **not** give generic or boilerplate explanations
- Do **not** invent features, behaviors, or capabilities
- Do **not** assume missing requirements
- Do **not** over-explain beyond what is necessary




# Example
# Prompt: Explain Amazon ECS on Fargate for a Stateful GenAI Service

## Role
You are an expert in AWS and GenAI.

## Context
Background information and constraints for this request:
- A containerized GenAI service that runs continuously
- The service loads a large ML risk model into memory at startup
- Low latency is required for each request
- The system maintains long-lived WebSocket connections for real-time streaming
- Infrastructure management overhead should be minimal

## Task
Explain **Amazon ECS on Fargate** and why it is suitable for this use case.

## Must Do (Positive Instructions)
- Use **simple, summarized explanations**
- Prefer **bullet points**
- Explain concepts in **plain language**
- Stay **focused on the provided context**
- Base explanations on **official AWS documentation or well-established AWS behavior**
- Optimize for **clarity and correctness**

## Must Avoid (Negative Instructions)
- Do **not** use heavy jargon or walls of text
- Do **not** give generic cloud explanations
- Do **not** invent features, behaviors, or capabilities
- Do **not** assume missing requirements
- Do **not** over-explain beyond what is necessary
