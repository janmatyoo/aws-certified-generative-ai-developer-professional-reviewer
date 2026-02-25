# AWS Step Functions

- Serverless workflow service that orchestrates multiple AWS services using state machines with built-in error handling
- Enforces explicit stopping conditions by tracking failure counts in state input and branching with a Choice state
- Detects model failures and automatically routes requests to fallback models or degraded service modes
- Choice states provide state management across executions, enabling threshold monitoring and automatic circuit breaking based on error patterns
- Provides resilient failover patterns
- Defines state machines that implement complex logic through a series of steps and branches
- Built-in error handling ensures reliability in model invocation
- Standard workflows can run for up to 1 year and maintain detailed execution histories for auditing
- Handles the orchestration of multiple Amazon Bedrock model calls

**References:**
- https://docs.aws.amazon.com/step-functions/latest/dg/connect-bedrock.html
- https://docs.aws.amazon.com/step-functions/latest/dg/concepts-statemachines.html

---

## Prompt Chaining

- Use prompt chaining for tasks that exceed a single model call's context or reasoning depth
- Outputs from one step pass as structured input into a follow-up prompt
- Prevents context window overflow and ensures complete input coverage

**References:**
- https://docs.aws.amazon.com/step-functions/latest/dg/sample-bedrock-prompt-chaining.html
- https://docs.aws.amazon.com/prescriptive-guidance/latest/agentic-ai-patterns/workflow-for-prompt-chaining.html
