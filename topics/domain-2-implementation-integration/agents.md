# Amazon Bedrock Agents

- Every agent has a default pre-processing prompt that determines if user input is safe
- Pre-processing prompts evaluate user input before it reaches the FM
- Helps identify and filter potentially malicious prompts

**Reference:** https://docs.aws.amazon.com/bedrock/latest/userguide/advanced-prompts.html

---

## Supervisor Agent

- AI agents can connect to different systems, APIs, and data sources to automate tasks
- For applications requiring multiple agents, a supervisor agent manages complex workflows of task-specific agents
- Task-specific agents are called sub-agents
- Amazon Bedrock Agents supports hierarchical agent systems with specialized roles
- A supervisor agent coordinates the overall workflow and deploys specialized sub-agents for specific tasks
- Task examples include quantitative analysis, news processing, and summarization
- Provides coherent, consistent, and coordinated output through centralized orchestration

**References:**
- https://docs.aws.amazon.com/bedrock/latest/userguide/agents-multi-agent-collaboration.html
- https://docs.aws.amazon.com/nova/latest/userguide/prompting-speech-speech.html
