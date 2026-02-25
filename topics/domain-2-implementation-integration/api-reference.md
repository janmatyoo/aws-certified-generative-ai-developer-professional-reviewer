# Amazon Bedrock API Reference

## Agent Traces

### PreProcessingTrace

- Details about the pre-processing step, in which the agent contextualizes and categorizes user inputs

### OrchestrationTrace

- Details about the orchestration step, in which the agent determines action order and which knowledge bases to retrieve

### PostProcessingTrace

- Details about the post-processing step, in which the agent shapes the response

All three traces together provide end-to-end visibility into the agent's reasoning process and complete coverage of the agent's processing pipeline.

**References:**
- https://docs.aws.amazon.com/bedrock/latest/APIReference/API_agent-runtime_PreProcessingTrace.html
- https://docs.aws.amazon.com/bedrock/latest/APIReference/API_agent-runtime_OrchestrationTrace.html
- https://docs.aws.amazon.com/bedrock/latest/APIReference/API_agent-runtime_PostProcessingTrace.html

---

## Human Evaluation Custom Metrics

- Create custom metrics for human evaluators to use when rating model responses
- Custom metrics specific to a domain (e.g., fashion recommendations) allow evaluators to rate responses meaningfully

**Reference:** https://docs.aws.amazon.com/bedrock/latest/APIReference/API_HumanEvaluationCustomMetric.html

---

## RetrieveAndGenerate API

- Combines vector embeddings for semantic search with response generation in a single call
- Automatically provides citations — essential for legal and compliance use cases
- Guardrails integration provides built-in content filtering and topic restriction without custom development or additional API orchestration

**Reference:** https://docs.aws.amazon.com/bedrock/latest/APIReference/API_agent-runtime_RetrieveAndGenerate.html
