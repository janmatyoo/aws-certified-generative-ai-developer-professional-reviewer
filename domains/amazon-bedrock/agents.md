Agents
- every agent has a default pre-processing prompt that can determine if user input is safe to use
- you can enable default pre-processing prompts in Agents to add an additional layer of security
- a pre-processing prompt will evaluate user input before the input reaches the FM
- this action helps identify and filter potentially malicious prompts.


https://docs.aws.amazon.com/bedrock/latest/userguide/advanced-prompts.html



Supervisor Agent
- AI agents can connect to different systems, APIs, and data sources
- AI agents can automate tasks
- For an application that requires multiple agents to complete different tasks, you need a supervisor agent to manage the complex workflows of task-specific agents
- The task-specific agents are named sub-agents
- Amazon Bedrock Agents supports hierarchical agent systems with specialized roles
- You can use a **supervisor agent** to coordinate overall workflow and to **deploy specialized sub-agents** for **specific tasks**
- Task examples include quantitative analysis, news processing, and summarization
- This solution provides coherent output through centralized orchestration
- Each agent performs a specialized task
- This solution provides **consistent and coordinated analysis**

https://docs.aws.amazon.com/bedrock/latest/userguide/agents-multi-agent-collaboration.html
https://docs.aws.amazon.com/nova/latest/userguide/prompting-speech-speech.html
