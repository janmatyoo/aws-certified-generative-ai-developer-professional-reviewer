PreProcessingTrace
- details about the pre-processing step, in which the agent contextualizes and categorizes user inputs

OrchestrationTrace
- details about the orchestration step, in which the agent determines the order in which actions are executed and which knowledge bases are retrieved

PostProcessingTrace
- details about the post-processing step, in which the agent shapes the response


This solution provides end-to-end visibility into the agent's reasoning process. Each step in the console or trace in the API includes these three essential components. Together these components provide complete coverage of the agent's processing pipeline. Additionally, the golden dataset validation provides systematic detection of hallucinations and reasoning failures.

https://docs.aws.amazon.com/bedrock/latest/APIReference/API_agent-runtime_PreProcessingTrace.html
https://docs.aws.amazon.com/bedrock/latest/APIReference/API_agent-runtime_OrchestrationTrace.html
https://docs.aws.amazon.com/bedrock/latest/APIReference/API_agent-runtime_PostProcessingTrace.html



- You can create **custom metrics** for **human evaluators** to use when rating model responses
- creating **custom metrics** that are specific to fashion recommendations would be suitable for the fashion experts to use when evaluating the models.

https://docs.aws.amazon.com/bedrock/latest/APIReference/API_HumanEvaluationCustomMetric.html



RetrieveAndGenerate API
- a solution combines vector embeddings for semantic search capabilities with RetrieveAndGenerate API
- this solution provides document retrieval with response generation in a single call.
- this solution automatically **provides citations** that are essential for legal compliance
    - Guardrails integration provides built-in content filtering and topic restriction capabilities that are specifically designed for AI safety - The system can prevent inappropriate legal advice generation and filter sensitive information without custom development or additional API orchestration.

https://docs.aws.amazon.com/bedrock/latest/APIReference/API_agent-runtime_RetrieveAndGenerate.html
