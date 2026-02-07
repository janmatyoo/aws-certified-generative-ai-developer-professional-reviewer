DynamoDB
- Storing human feedback for model evaluations
- full conversation history
- provides fast, consistent access to processing status and results
    - this solution uses fully managed services that provide concurrent processing, audit trails, and result retrieval


DynamoDB with Global Secondary Indexes(GSI)
- single-table design provides a highly scalable solution for conversation storage
- this solution supports metadata-based queries by user ID, conversation ID, and date ranges
- you can use hierarchical sort keys to efficiently query conversation history while maintaining relationships between messages and metadata

DynamoDB Accelerator (DAX) 
- provides in-memory caching for sub-millisecond retrieval of recent conversation history
- this solution meets the low-latency requirement

DynamoDB TTL
- automatically deletes expired items to enforce data retention.


**Related links:**
- https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-modeling-nosql.html
- https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DAX.concepts.html
- https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Streams.html
