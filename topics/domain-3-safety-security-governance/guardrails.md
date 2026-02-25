# Amazon Bedrock Guardrails

Safety layer for generative AI applications that filters harmful content, blocks restricted topics, and masks sensitive data in both user inputs and model responses.

---

## Content Filtering

- Filters harmful content in inputs and outputs
- Applies configurable policies that automatically block unsafe generations
- Provides built-in support to detect harmful content, protect sensitive data, and block illegal content
- Configure word filters to block specific words, tokens, or characters (e.g., emoji glyphs)
- Set denied topics to prohibit informal or noncompliant language during model inference
- Provides built-in protection against prompt injection and jailbreaks
- Can be used with SageMaker AI models, not just Amazon Bedrock

---

## PII Masking

- Masks PII in user prompts before they reach the model
- Reduces privacy risk at inference
- Ensures unredacted PII does not persist in logs or stored outputs
- Use sensitive information filters to detect and redact PII
- Supports tagging for organizational purposes and context-based filtering

---

## Contextual Grounding Checks

- Detects and filters hallucinations in model responses
- Verifies outputs against retrieval sources
- Use automated reasoning checks to demonstrate the factual basis for an LLM's response in regulated industries (e.g., healthcare)
- Helps reduce the risk of incorrect medical information and ensures compliance with factual accuracy requirements
- Provides immediate detection and prevention of policy violations with minimal setup

---

## Monitoring

- `GuardrailPolicyType` provides detailed information on which policy intervened
- Use this data to make informed decisions based on specific metrics

**References:**
- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/monitoring-guardrails-cw-metrics.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-denied-topics.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-injection.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-word-filters.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-sensitive-filters.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-prompt-attack.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-contextual-grounding-check.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-automated-reasoning-checks.html
- https://aws.amazon.com/blogs/machine-learning/automate-building-guardrails-for-amazon-bedrock-using-test-driven-development/
- https://docs.aws.amazon.com/cli/latest/reference/bedrock-runtime/converse.html
- https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/bedrock-runtime/client/converse.html
