## AI, ML & Generative AI Concepts

---

### Template (copy/paste)

### 1️⃣ <Topic Name>

**What it is:**  
<1 sentence max>

**Used for:**
- <use case 1>
- <use case 2>
- <use case 3 (optional)>

**When NOT to use:**
- <anti-pattern / wrong fit>
- <constraint / limitation (optional)>

🧠 **Exam cue:**  
"<keyword / scenario>" → **<Topic Name>**

**Related links:**
- <link title> — <URL or relative path>
- <link title> — <URL or relative path>

---

### Notes (keep it consistent)
- **Keep it short**: 1 sentence for “What it is”, max 3 bullets for “Used for”
- **Keep “When NOT to use” strict**: max 2 bullets, only obvious anti-patterns
- **Make exam cues mechanical**: always `"signal"` → **answer**
- **Links over duplication**: prefer adding a link instead of extra explanation

---

### Guide (how we create each reviewer entry)

**Goal:** each bullet must be **verifiable from official AWS docs** and **fast to scan**.

**Source rules (to avoid hallucinations):**
- Use **official AWS documentation** (`docs.aws.amazon.com`) as primary source.
- Prefer **User Guide** for “what it is/how it works”, and **API Reference** for exact options/fields/valid values.
- If a claim can’t be found in docs, **don’t include it** (or rewrite to match doc wording).

**Workflow (repeat for every new topic):**
1. Find the **canonical doc page(s)** for the feature (User Guide + API Reference if applicable).
2. Extract only the **high-signal facts**: definition, available options, key constraints/warnings, and costs/limits (if explicitly stated).
3. Map facts into the template:
   - **What it is**: 1 sentence, written in AWS’s terms
   - **Used for**: 2–3 bullets, ideally each mapping to a doc section/option
   - **When NOT to use**: 1–2 bullets, only when AWS explicitly warns/limits/costs it
   - **Exam cue**: a short “if you see X → answer Y” pattern
   - **Related links**: add the exact AWS doc URLs you used

**Link policy:**
- Include at least **1 official doc link** per topic.
- If you mention a specific **API field** or **valid values**, include the **API Reference link**.

---

### 1️⃣ Chunking (Amazon Bedrock Knowledge Bases)

**What it is:**  
When ingesting data into Amazon Bedrock Knowledge Bases, Amazon Bedrock splits documents into chunks, converts chunks to embeddings, and writes them to a vector index while maintaining a mapping to the original document.

**Used for:**
- **Fixed-size chunking**: configure tokens per chunk and overlap percentage between consecutive chunks
- **Hierarchical chunking**: define parent/child chunk sizes + overlap tokens; retrieval can replace child chunks with parent chunks for more context
- **Semantic chunking**: split into meaningful chunks; configure max tokens, buffer size, and breakpoint percentile threshold

**When NOT to use:**
- **Hierarchical chunking + S3 vector bucket vector store**: AWS notes hierarchical chunking is not recommended in this case
- **Semantic chunking**: if you want to avoid additional costs (AWS notes extra cost due to its use of a foundation model)

🧠 **Exam cue:**  
"Knowledge Bases ingestion splits docs into chunks → embeddings → vector index" → **Chunking**

**Related links:**
- How content chunking works for knowledge bases — https://docs.aws.amazon.com/bedrock/latest/userguide/kb-chunking.html
- Customize ingestion for a data source (chunking strategy + default behavior + immutability) — https://docs.aws.amazon.com/bedrock/latest/userguide/kb-data-source-customize-ingestion.html
- `ChunkingConfiguration` (API reference: `chunkingStrategy` values) — https://docs.aws.amazon.com/bedrock/latest/APIReference/API_agent_ChunkingConfiguration.html

---

### 2️⃣ Temperature (Inference parameter)

**What it is:**  
An inference parameter that affects the shape of the probability distribution for the predicted output and influences the likelihood of selecting lower-probability outputs.

**Used for:**
- Increasing determinism: choose a **lower** value to influence the model to select higher-probability outputs
- Increasing variation: choose a **higher** value to influence the model to select lower-probability outputs
- Setting base inference parameters in Bedrock `Converse`/`ConverseStream` via `InferenceConfiguration.temperature` (valid range 0–1)

**When NOT to use:**
- If you want more deterministic responses, **don’t use a high temperature** (AWS describes higher values increasing selection of lower-probability outputs)
- For **Claude Sonnet 4.5 / Claude Haiku 4.5**, don’t specify **both** `temperature` and `top_p` in the same request (AWS warning)

🧠 **Exam cue:**  
"More deterministic vs more random output" → **Temperature**

**Related links:**
- Influence response generation with inference parameters — https://docs.aws.amazon.com/bedrock/latest/userguide/inference-parameters.html
- `InferenceConfiguration.temperature` (API reference; range 0–1) — https://docs.aws.amazon.com/bedrock/latest/APIReference/API_runtime_InferenceConfiguration.html
- Anthropic Claude Messages API request/response (warning about `temperature` vs `top_p`) — https://docs.aws.amazon.com/bedrock/latest/userguide/model-parameters-anthropic-claude-messages-request-response.html

---

### 3️⃣ Top P (Nucleus sampling / inference parameter)

**What it is:**  
An inference parameter that controls the percentage of most-likely candidates the model considers for the next token (nucleus sampling / top-\(p\)).

**Used for:**
- Reducing randomness: choose a **lower** value to decrease the pool and limit options to more likely outputs
- Increasing diversity: choose a **higher** value to increase the pool and allow less likely outputs
- Setting base inference parameters in Bedrock `Converse`/`ConverseStream` via `InferenceConfiguration.topP` (valid range 0–1)

**When NOT to use:**
- For **Claude Sonnet 4.5 / Claude Haiku 4.5**, don’t specify **both** `temperature` and `top_p` in the same request (AWS warning)
- For Anthropic Claude sampling, AWS notes: when adjusting sampling parameters, modify either `temperature` or `top_p` — **do not modify both at the same time**

🧠 **Exam cue:**  
"Select from top X% of probability distribution" → **Top P**

**Related links:**
- Influence response generation with inference parameters — https://docs.aws.amazon.com/bedrock/latest/userguide/inference-parameters.html
- `InferenceConfiguration.topP` (API reference; example 0.8 = top 80%) — https://docs.aws.amazon.com/bedrock/latest/APIReference/API_runtime_InferenceConfiguration.html
- Anthropic Claude Messages API request/response (`top_p` nucleus sampling + warning) — https://docs.aws.amazon.com/bedrock/latest/userguide/model-parameters-anthropic-claude-messages-request-response.html

---

### 4️⃣ Top K (Inference parameter)

**What it is:**  
An inference parameter that limits generation to the top \(K\) most-likely candidate tokens for the next token.

**Used for:**
- Reducing randomness: choose a **lower** value to decrease the pool and limit options to more likely outputs
- Increasing diversity: choose a **higher** value to increase the pool and allow less likely outputs
- For Anthropic Claude (Messages API), `top_k` is an optional request parameter used to “only sample from the top K options” and to “remove long tail low probability responses”

**When NOT to use:**
- If you want the model to consider a wider set of candidates, **don’t set Top K too low** (AWS: lower values reduce the pool)
- If you’re using Bedrock `Converse`/`ConverseStream`, note `topK` is **not** part of the base `InferenceConfiguration`; model-specific parameters must be passed via model-specific fields (for example, Claude uses `top_k` in its request body)

🧠 **Exam cue:**  
"Only sample from the top K options (e.g., K=50)" → **Top K**

**Related links:**
- Influence response generation with inference parameters — https://docs.aws.amazon.com/bedrock/latest/userguide/inference-parameters.html
- `InferenceConfiguration` (base params for `Converse`/`ConverseStream`; additional params via `additionalModelRequestFields`) — https://docs.aws.amazon.com/bedrock/latest/APIReference/API_runtime_InferenceConfiguration.html
- Anthropic Claude Messages API request/response (`top_k`) — https://docs.aws.amazon.com/bedrock/latest/userguide/model-parameters-anthropic-claude-messages-request-response.html

---

### 5️⃣ Inference (Amazon Bedrock)

**What it is:**  
Inference refers to the process of generating an output from an input provided to a model.

**Used for:**
- **Text**: provide text input and generate various types of text (chat, summarization, code generation, etc.)
- **Image / Video**: provide text (and sometimes images) to generate or modify images, or generate videos
- **Embeddings**: generate a vector of numeric values representing the input, for semantic/visual similarity use cases (including knowledge base creation)

**When NOT to use:**
- If the foundation model you selected doesn’t support the output modality you need, you can’t use it for that output (AWS points to checking supported models/modality support)

🧠 **Exam cue:**  
"Generate an output from an input prompt/image/etc." → **Inference**

**Related links:**
- Submit prompts and generate responses with model inference — https://docs.aws.amazon.com/bedrock/latest/userguide/inference.html
- Influence response generation with inference parameters — https://docs.aws.amazon.com/bedrock/latest/userguide/inference-parameters.html




