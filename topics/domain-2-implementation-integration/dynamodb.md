# Amazon DynamoDB

- Used for storing human feedback for model evaluations
- Stores full conversation history
- Provides fast, consistent access to processing status and results using fully managed services with concurrent processing, audit trails, and result retrieval

---

## Global Secondary Indexes (GSI)

- Single-table design provides a highly scalable solution for conversation storage
- Supports metadata-based queries by user ID, conversation ID, and date ranges
- Use hierarchical sort keys to efficiently query conversation history while maintaining relationships between messages and metadata

---

## DynamoDB Accelerator (DAX)

- Provides in-memory caching for sub-millisecond retrieval of recent conversation history
- Meets low-latency requirements

---

## DynamoDB TTL

- Automatically deletes expired items to enforce data retention

**References:**
- https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-modeling-nosql.html
- https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DAX.concepts.html
- https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Streams.html
