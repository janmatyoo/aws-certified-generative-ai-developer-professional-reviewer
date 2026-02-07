Step Functions
- can enforce explicit stopping conditions by tracking failure counts in state input and branching with a Choice state
-  circuit breaker patterns to detect model failures and automatically route requests to fallback models or degraded service modes
- Implement circuit breaker patterns using Step Functions to detect FM failures and automatically route requests to fallback options.
-  Step Functions Choice states provide state management across executions, enabling proper threshold monitoring and automatic circuit breaking based on error patterns.
- is a serverless workflow service that orchestrates multiple AWS services by using state machines with built-in error handling
- provides resilient failover patterns
- to define state machines that implement complex logic through a series of steps and branches
- use built-in error handling ensures reliability in model invocation
- **Step Functions standard workflows** can run for up to 1 year and maintain detailed execution histories for auditing
- can handle the orchestration of multiple Amazon Bedrock model calls
- Implement **circuit breaker patterns** using Step Functions to detect FM failures and automatically route requests to fallback options

https://docs.aws.amazon.com/step-functions/latest/dg/connect-bedrock.html
https://docs.aws.amazon.com/step-functions/latest/dg/concepts-statemachines.html


Prompt Chaining
- you can use prompt chaining for tasks that **exceed a single model call's context** or reasoning depth
- outputs from one step (summaries of individual chunks) pass as structured input into a **follow-up prompt** (a final summarization request)
- this solution **prevents context window overflow** and **ensures complete input coverage**

https://docs.aws.amazon.com/step-functions/latest/dg/sample-bedrock-prompt-chaining.html
https://docs.aws.amazon.com/prescriptive-guidance/latest/agentic-ai-patterns/workflow-for-prompt-chaining.html