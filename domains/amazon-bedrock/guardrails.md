### Guardrails

**What it is:**  
Safety layer for generative AI applications, filtering harmful content, blocking restricted topics, and masking sensitive data (PII) in both user inputs and model responses


**Used for:**
- PII masking/removal
- they do not satisfy a requirement for human review and approval
- help filter content and improve safety
- topic filtering and PII masking, and invoke the managed prompt from all applications
- provide built-in protection against prompt injection
- provide content filtering and enforce topic boundaries
- validates and filters inputs before the inputs reach the FM
- configure guardrails to protect against prompt attacks, including jailbreaks and prompt injection
- To enforce style and content rules
- can configure word filters to block specific words, tokens, or characters. For example, you can block emoji glyphs
- can set denied topics to prohibit informal or noncompliant language
- to define denied topics and blocked keywords to enforce content during model inference
- can use Guardrails for models that you deploy on SageMaker AI
- can mask PII in user prompts before the prompts reach the model
- can reduce privacy risk at inference
- ensure that unredacted PII does not persist in logs or stored outputs
- apply configurable policies that automatically block unsafe generations
- provide built-in support to detect harmful content, protect sensitive data, and block illegal content
- can configure guardrails with content filters for harmful responses and word filters for prohibited terms
- can use sensitive information filters in Guardrails to detect and redact PII
- can use denied topics to block model engagement on specific subjects
    - this configuration complies with healthcare regulations by protecting PII
    - this configuration prevents the discussion of unauthorized medical topics


**Key Features:**
GuardrailPolicyType
- provides detailed information on which policy intervened in the guardrail
- the GenAI developer can use this configuration to make an informed decision based on specific metrics


Contextual Grounding Checks
- support contextual grounding checks to detect and filter hallucinations in model responses
- can configure guardrails with **contextual grounding checks** to reduce hallucinations and prevent the leakage of sensitive data
- can use automated guardrail checks and contextual grounding checks in Guardrails to ensure that responses are accurate and not hallucinated
- these checks verify outputs against retrieval sources
- automated reasoning checks are useful when you need to demonstrate the factual basis for an LLM's response in regulated industries such as healthcare
- this configuration helps reduce the risk of incorrect medical information
- this configuration helps ensure compliance with factual accuracy requirements
- provide built-in content filtering capabilities for text and multimodal content
- provide immediate detection and prevention of policy violations with minimal setup
    - this solution uses Amazon S3 for version-controlled model card documentation
- supports tagging for organizational purposes and context-based filtering.

https://aws.amazon.com/blogs/machine-learning/automate-building-guardrails-for-amazon-bedrock-using-test-driven-development/
https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html


    
- https://docs.aws.amazon.com/bedrock/latest/userguide/monitoring-guardrails-cw-metrics.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html

- https://docs.aws.amazon.com/bedrock/latest/userguide/monitoring-guardrails-cw-metrics.html
- https://docs.aws.amazon.com/cli/latest/reference/bedrock-runtime/converse.html
- https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/bedrock-runtime/client/converse.html

- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-denied-topics.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-injection.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-word-filters.html

- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-sensitive-filters.html
- https://docs.aws.amazon.com/macie/latest/user/data-classification.html
- https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html

- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-prompt-attack.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-contextual-grounding-check.html

- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html

- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-sensitive-filters.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-automated-reasoning-checks.html
