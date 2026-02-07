Prompt Management
- centralized feature within AWS Bedrock that streamlines the development lifecycle of generative AI applications by enabling developers to create, test, version, and share prompt templates
- create reusable, parameterized prompts with versioning and an approval workflow
- defines the agent role and includes explicit JSON output instructions (schema and example)
- securely create, parameterize, version, and approve prompt templates within the Amazon Bedrock managed environment
- clearly define boundaries and limitations to help prevent prompt injection
- establishes strict behavioral constraints for the [AI Agents](ai-agents.md)
- creates a strong foundation for secure operation when combined with other protective measures
- Newer models differentiate between system and user prompts
- System prompts can define the scope of what an agent can and cannot do
- to create, store, and manage reusable, parameterized prompt templates
- can define system instructions to establish an assistant's role and add parameterized variables
    - the variables can include company name and document content
- provides built-in versioning and review workflows
- can help ensure that new prompt versions are reviewed and approved before activation
- provides lifecycle control for prompts
- provides version-control and role-aware templates with built-in approval workflows



- https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-management.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-management-create.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-management-view.html
- https://docs.aws.amazon.com/awscloudtrail/latest/userguide/how-cloudtrail-works.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html




- you can update the **system prompt** to clearly define boundaries and limitations to help prevent prompt injection
- this action establishes strict behavioral constraints for the agent
- this action creates a strong foundation for secure operation when combined with other protective measures
- newer models differentiate between system and user prompts
- define the scope of what an **agent** can and cannot do

https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-management-create.html



- provides a centralized service to store, catalog, and manage prompts
- supports p**arameterized templates with variables** and system instructions to control the model's role and tone
- this solution offers built-in capabilities for prompt versioning, testing, and deployment without requiring custom infrastructure
- the **compare versions feature** provides prompt testing and side-by-side evaluation without deployment
- prompt versioning ensures that you can lock and execute the selected prompts through Amazon Bedrock APIs


https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-management-version-compare.html
https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-management.html





