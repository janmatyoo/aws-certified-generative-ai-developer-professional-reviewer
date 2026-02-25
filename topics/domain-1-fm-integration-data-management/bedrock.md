# Amazon Bedrock

- Fully managed service that provides access to FMs
- Provides a built-in model invocation logging feature
- Has text reformatting capabilities that ensure consistent input structure for FMs

---

## Model Invocation Logging

- Captures all model interactions for auditing purposes, including inputs and outputs
- Provides detailed logs of model interactions, including prompt content and responses
- Use for direct analysis of cases where unexpected classifications occur
  - Helps identify patterns or specific conditions that led to anomalies despite well-structured prompts
  - Provides the most direct insight into intermittent model behavior issues

**Reference:** https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/model-invocations.html

---

## Inference Parameters

### Temperature

- Controls randomness in token selection
- Higher temperature increases variability for creative output
- A temperature of 0.5 provides creativity while maintaining reasonable control

### Top P (Nucleus Sampling)

- Selects tokens from the most likely subset to balance diversity and coherence
- A top-p of 0.8 ensures the model considers a range of options within acceptable probability bounds
- Length penalties control verbosity and help maintain consistency while permitting some creative expression

### Top K

- The number of most-likely candidates the model considers for the next token

**References:**
- https://docs.aws.amazon.com/bedrock/latest/userguide/inference-parameters.html#inference-randomness
- https://docs.aws.amazon.com/bedrock/latest/userguide/inference-parameters.html#inference-length

---

## Custom Model Import

- Supports importing Llama models in Hugging Face format from Amazon S3
- The Hugging Face format can include Safetensors weights, config.json files, and tokenizer files
- After importing, purchase Provisioned Throughput to provide dedicated compute capacity and throughput for production

**References:**
- https://docs.aws.amazon.com/bedrock/latest/userguide/model-customization-import-model.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/custom-model-use-pt.html

---

## Continued Pre-training

- Trains a model on large amounts of unlabeled domain-specific data
- Continues general language model training on new content
- Allows the model to develop a deeper understanding of a domain's terminology, concepts, and relationships

**Reference:** https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models.html

---

## Reranking

- Reorders retrieved chunks based on relevancy to the query
- Runs after retrieval, before generation — no re-training or embedding changes needed
- Use an Amazon Bedrock rerank model to reorder chunks based on semantic relevance to the query
- Improves context selection without re-training the LLM or altering the embedding model

**Reference:** https://docs.aws.amazon.com/bedrock/latest/userguide/rerank.html

---

## Inference Profiles

- Designed to manage and track FM costs in multi-tenant environments
- The Lambda function can select the appropriate profile based on the tenant ID from the S3 key prefix
- Achieves per-tenant cost tracking with minimal additional configuration logic

**Reference:** https://docs.aws.amazon.com/bedrock/latest/userguide/inference-profiles-use.html

---

## Pricing

### On-Demand

- Early stage, testing, and experimentation
- Unpredictable traffic
- No commitment or reserved resources
- Pay only for tokens processed
- Suitable for POCs or variable use cases

### Provisioned Throughput

- Production workloads with predictable traffic
- Performance-sensitive applications
- Required for custom model inference
- Avoids throttling when large volumes of tokens per minute are needed
- Provides cost predictability and performance guarantees

---

## APIs

### CountTokens API

- Returns the number of tokens a specific input would use before sending it to a model
- Use to estimate costs before running inference
- Use to check token limits for your prompt
- Use to optimize prompt length to avoid exceeding model limits

### Converse API

- Sends your conversation or prompt to a model and returns a complete response
- The main API for building chat apps, assistants, multi-turn conversations, or structured prompts

### ConverseStream API

- Like Converse, but streams the response back piece by piece instead of waiting for the full message
- Ideal for real-time apps or live UI updates
