Prompt Management
- provides version-control and role-aware templates with built-in approval workflows



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
- designed to balance precision and context for RAG
- most suitable for documents with hierarchical structures such as technical repair manuals
- provides high retrieval accuracy

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




Continued pre-training
- a model can learn from large amounts of unlabeled domain-specific data
- this solution continues general language model training on new content
- the model can develop a deeper understanding of the domain's terminology, concepts, and relationships from the 3 TB of proprietary data





Stop Sequences Parameters
- stop the model from generating a response
- stop the model after generating certain key phrases
- this solution provides a built-in mechanism in the model's API to directly control output generation

https://docs.aws.amazon.com/bedrock/latest/userguide/model-parameters-anthropic-claude-messages-request-response.html



Amazon Bedrock Cross-Region Inference
- to ensure high availability by routing requests to alternative AWS Regions when primary Regions experience disruptions



Implement parameter-efficient adaptation techniques like Low-Rank Adaptation (LoRA) and adapters to reduce computational requirements while achieving comparable performance to full fine-tuning.




Implement comprehensive rollback strategies using blue/green deployments and canary releases to quickly revert to previous model versions when issues are detected.


Design an abstraction layer using Lambda functions that separates business logic from model-specific implementation details.

Implement a model router component using Lambda that dynamically selects the appropriate FM based on request characteristics and configuration settings.


Implement standardized request and response formats in API Gateway to help ensure consistent interfaces, regardless of the underlying FM.


Configure AWS AppConfig to externalize model selection parameters, enabling runtime configuration changes without code deployments

Set up feature flags in AWS AppConfig to enable gradual rollout of new models, A/B testing between models, and quick rollbacks if performance issues arise.




Low-Rank Adaptation (LoRA)
- Parameter-efficient fine-tuning technique that adds small, trainable rank decomposition matrices to existing model weights
- It requires significantly less computational resources than full model fine-tuning
- Preserves most of the foundation model's general knowledge while adapting it to the medical domain
- It results in smaller adapter modules that can be easily swapped or combined
- Typically requires less training data than full fine-tuning, which is valuable for specialized domains with limited data


Exponential backoff is a retry mechanism that does not maintain system-wide failure state or implement true circuit breaking.


Which methods effectively support graceful degradation in a generative AI (GenAI) system?
- Fallback to more basic models ensures service continuity while gracefully reducing capabilities based on system conditions.
- Multiple model versions with capability tiering enables systematic degradation while maintaining critical functionalities.





Amazon ECS on Fargate
- This approach provides the most suitable architecture for a complex, stateful, and long-running tool
- can run persistent containerized applications without server management
- the large risk model can be loaded into memory when the container starts
- this approach avoids unacceptable latency on each call
- this approach supports the required long-lived WebSocket connection for the real-time data stream.



Effective cross-region resilience (for entire application stack)
- Correct: Create separate, independent deployments in multiple regions with DNS-based routing
    - It ensures complete isolation between regional deployments, so a failure in one region doesn't affect others
    - DNS-based routing (like Amazon Route 53) can detect regional outages and automatically direct traffic to healthy regions
    - Each regional deployment can operate independently with its own resources and foundation model endpoints
    - This approach provides true disaster recovery capabilities in case of a complete regional outage

Incorrect:
- Amazon Bedrock Cross-Region Inference helps with model availability but doesn't address the resilience of the entire application stack
- AWS Global Accelerator improves network performance but requires healthy endpoints in multiple regions to route to, which this option doesn't specify

**Exam cue:**  
“Explain predictions and detect bias” → **Clarify**





A human-validated dataset ensures an accurate representation of enterprise-specific use cases, terminology, and content patterns. Using LLM-as-a-judge with custom metrics provides an automated, consistent, and scalable evaluation. You can design custom metrics to assess formality scale and company-specific tone and style with consistent criteria. 

https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base-evaluation-prompt.html
https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base-evaluation-metrics.html
https://docs.aws.amazon.com/bedrock/latest/userguide/kb-evaluation-custom-metrics-prompt-formats.html




WebSocket API in API Gateway
- to maintain persistent client connections.
- you must configure the API with the appropriate route selection expressions
- the route selection expressions include $connect, $disconnect, and custom routes such as chat
- you must integrate with a Lambda function. These routes provide proper connection lifecycle handling
- API Gateway WebSocket APIs provide connection IDs but do not persist the connection IDs


Session management across multi-step interactions
- you must use a database to store connection IDs and session metadata
- you can use DynamoDB as the database
- the $connect and $disconnect routes can update DynamoDB when clients join or leave
- this step enables retries
- this step provides multiple Lambda workflows and the cleanup of stale connections.



Model cascading through sequential model invocation provides an efficient way to handle query complexity.
First, you can use a small model to determine complexity and then invoke the larger model only when necessary.
This solution optimizes both cost and performance.
The smaller model quickly handles simple queries.
Complex queries get the full capabilities of a larger model.




Uploading video using presigned url
- this solution implements secure video uploads by using S3 presigned URLs
- this solution follows the principle of least privilege
- EventBridge is a serverless event bus service that efficiently routes S3 events to Step Functions for workflow orchestration
- Step Functions has direct service integration that eliminates the need for intermediate Lambda functions
- this solution reduces operational overhead
- This solution uses Amazon Rekognition for video analysis tasks including celebrity recognition and object detection
- This solution uses Amazon Bedrock FMs for content summarization and transcript generation
- this solution maximizes the use of managed capabilities and minimizes custom code requirements



Enabling PDF page splitting in the BDA project
- provides proper processing for multipage PDF files
- this built-in feature automatically handles page segmentation
- all pages are processed correctly, without requiring additional custom code or services
- if this feature is not turned on, the best matching blueprint will be used for the entire PDF file.

https://docs.aws.amazon.com/bedrock/latest/userguide/bda-document-splitting.html


You can refine blueprint names and definitions. You can use one clear blueprint for each document type. This step can improve the accuracy and consistency of document classification. This step reduces potential conflicts in document type identification. This step ensures that each page is correctly categorized. When you combine this step with document splitting, you have a comprehensive solution to process multipage PDF files with minimal operational overhead. One well-defined blueprint for each content type follows BDA best practices. Multiple blueprints of the same type in a project could lead to worse performance.

https://docs.aws.amazon.com/bedrock/latest/userguide/bda-document-splitting.html#bda-blueprint-best-practices

