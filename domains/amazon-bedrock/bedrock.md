

Bedrock
- a fully managed service that provides access to FMs
- provides a built-in model invocation logging feature
- has text reformatting capabilities that ensure consistent input structure for FMs


Amazon Bedrock Model Invocation Logging 
- can be enabled to capture all model interactions for auditing purposes, including inputs and outputs
- provides detailed logs of model interactions, including prompt content and responses
- you can use this approach for direct analysis of cases where unexpected classifications occur
    - this approach helps identify patterns or specific conditions that led to anomalies despite the well-structured prompts and validation
    - this approach provides the most direct insight into intermittent model behavior issues.

https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/model-invocations.html



Temperature
- controls randomness in token selection
- A higher temperature increases variability for creative output
- A temperature of 0.5 provides creativity while maintaining reasonable control

Top P (nucleus sampling)
- selects tokens from the most likely subset to balance diversity and coherence
- Length penalties control verbosity
- A top-p of 0.8 ensures that the model considers a range of options and stays within acceptable probability bounds
- Length penalties help maintain consistency with the guidelines but permit some creative expression

Top K
- The number of most-likely candidates that the model considers for the next token

https://docs.aws.amazon.com/bedrock/latest/userguide/inference-parameters.html#inference-randomness
https://docs.aws.amazon.com/bedrock/latest/userguide/inference-parameters.html#inference-length




Custom Model Import
- supports importing Llama models in Hugging Face format from Amazon S3
- the Hugging Face format can include Safetensors weights, config.json files, and tokenizer files
- after importing the model, the company can purchase Provisioned Throughput to provide dedicated compute capacity and throughput for production workloads
- this approach meets both the import and throughput requirements.


https://docs.aws.amazon.com/bedrock/latest/userguide/model-customization-import-model.html
https://docs.aws.amazon.com/bedrock/latest/userguide/custom-model-use-pt.html



With continued pre-training
- a model can learn from large amounts of **unlabeled domain-specific data**
- this solution continues general language model training on new content
- the model can **develop a deeper understanding** of the domain's terminology, concepts, and relationships from the 3 TB of proprietary data

https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models.html



Reranking
- is a feature of Amazon Bedrock that **reorders chunks based on relevancy to the query**
- this strategy reflects the manual implementation of a reranking layer
- after retrieving documents from the vector store, you can use an Amazon Bedrock rerank model to reorder chunks based on semantic relevance to the query
- this strategy improves context selection **without re-training** the LLM or altering the embedding model.


https://docs.aws.amazon.com/bedrock/latest/userguide/rerank.html



Amazon Bedrock application **inference profiles**
- are specifically designed to **manage and track** FM costs in **multi-tenant** environments
- this step efficiently handles cost attribution
- the summarization Lambda can select the appropriate profile based on the clinic ID from the **S3 key prefix**
- this step achieves per-clinic cost tracking with minimal additional configuration logic

https://docs.aws.amazon.com/bedrock/latest/userguide/inference-profiles-use.html

---

Pricing:

- On-Demand
    - Early stage, testing, experimentation
    - Unpredictable traffic
    - Don’t want any commitment or reserving resources
    - Pay only for tokens processed
    - Great for POCs or variable use cases

-Provisioned Throughput
    - Production workloads with predictable traffic
    - Performance-sensitive applications
    - Custom model inference (often requires it)
    - Avoiding throttling when large volumes of tokens/minute are needed
    - Provides cost predictability and performance guarantees at the expense of upfront resource

---

features:
- CountTokens API 
    - returns the number of tokens that would be used by a specific input (like a prompt) before you actually send it to a model 
    - estimate costs before running inference
    - see token limits for your prompt
    - optimize prompt length so you don’t exceed model limits


- Converse API
    - sends your conversation (or prompt) to a model and returns a response (a complete message)
    - this is the main API for building chat apps, assistants, multi-turn conversations, or structured prompts


- ConverseStream API
    - is just like Converse, but instead of waiting for the whole message to be generated before returning it, it streams the response back piece by piece
    - ideal for real-time apps or live UI updates

---
