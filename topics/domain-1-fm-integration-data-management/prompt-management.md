# Prompt Management

- Centralized feature for creating, testing, versioning, and sharing prompt templates
- Creates reusable, parameterized prompts with versioning and an approval workflow
- Defines the agent role and includes explicit JSON output instructions (schema and example)
- Supports parameterized templates with variables and system instructions to control the model's role and tone
- Offers built-in capabilities for prompt versioning, testing, and deployment without custom infrastructure
- Provides lifecycle control for prompts with version-control and role-aware templates

**References:**
- https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-management.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-management-create.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-management-view.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-management-version-compare.html
- https://docs.aws.amazon.com/awscloudtrail/latest/userguide/how-cloudtrail-works.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html

---

## Versioning & Approval

- Provides built-in versioning and review workflows
- New prompt versions are reviewed and approved before activation
- The compare versions feature provides prompt testing and side-by-side evaluation without deployment
- Prompt versioning allows you to lock and execute selected prompts through Amazon Bedrock APIs

---

## System Prompts

- Newer models differentiate between system and user prompts
- System prompts define the scope of what an agent can and cannot do
- Update the system prompt to clearly define boundaries and limitations to help prevent prompt injection
- Establishes strict behavioral constraints for agents
- Creates a strong foundation for secure operation when combined with other protective measures
- Define system instructions to establish an assistant's role and add parameterized variables (e.g., company name, document content)
