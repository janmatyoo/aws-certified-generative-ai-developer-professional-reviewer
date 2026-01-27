Vector Search
- can be slowed by coordinating many shard-level searches and merging results. Using fewer, larger shards (appropriate shard sizing) reduces fan-out and coordination overhead, improving retrieval latency without changing the FM or the document set.


Smaller Embedding
- reduces storage and indexing costs


Metadata framework
- separates content from metadata (such as timestamps, authorship, and domain tags)
- improves precision and context awareness without changing the core RAG architecture


AgentCore Memory
- supports session-oriented context (events within a session) and longer-term memory records (such as preferences and summaries), reducing the need to build and operate custom state stores and coordination logic across multiple specialized agents.

Bedrock Batch inference
- designed for high-throughput, asynchronous processing by submitting many prompts together and writing results back to Amazon S3
- reduces orchestration overhead from per-item invocations and is well suited for nightly jobs where results are not required in real time.


Provisioned throughput
- designed to provide consistent, higher throughput for a specific Bedrock model with minimal operational overhead


DynamoDB
- well-suited to store structured feedback records (including model ID and prompt version) so the team can later analyze user satisfaction and trends per configuration and use that information to iterate on prompts or model selection

API Gateway + Lambda + DynamoDB
- a pattern provides a simple serverless feedback interface that can capture explicit user ratings and annotations at scale


Hierarchical chunking
- designed to balance precision and context for RAG.

Smaller child chunks
- improve semantic match quality for pinpoint clauses, and returning parent chunks provides the broader surrounding policy text needed for grounded, defensible answers

Lowering temperature and appropriately tuning top-p/top-k
- can make outputs more deterministic and reduce creative variation

Bedrock Data Automation
- asynchronously process the PDFs and JPEGs into structured JSON and to process the MP3 voicemails into transcripts and summaries

AWS Glue ETL job
- transform the CSV metadata into JSON and store all outputs in Amazon S3

AWS Lambda function
- assemble a single JSON case packet for the Amazon Bedrock multimodal model


Amazon Comprehend
- extract key entities (such as product names and case identifiers)
- normalize or redact noisy/sensitive content


AWS Amplify
- accelerates delivery of a production-ready, accessible web interface and commonly used front-end capabilities (such as authentication)

Amazon Bedrock Flows
- provide a managed, no-code/low-code way to chain prompts and models with conditional connections, so non-developers can update the workflow without changing and redeploying the UI or API code

EventBridge
- decouples producers from consumers with managed, event-driven fan-out

Cross-Region Inference
- enables Bedrock to distribute and fail over inference requests across multiple AWS Regions within the allowed geography (United States)

Step Functions
- can enforce explicit stopping conditions by tracking failure counts in state input and branching with a Choice state












