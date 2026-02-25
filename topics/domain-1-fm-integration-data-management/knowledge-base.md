# Amazon Bedrock Knowledge Base

- Fully managed end-to-end RAG workflow
- Managed RAG service that securely connects an LLM to enterprise data
- Stores and searches data by meaning
- Integrates with OpenSearch Serverless as a vector store
- Supports Amazon S3 as a data source
- Provides built-in capabilities to integrate multiple document sources through standardized connectors
- Handles authentication, synchronization, and content updates automatically
- Maintains data freshness through automated synchronization
- Provides consistent access patterns across all document sources

**Use cases:**
- Retrieval-augmented generation (RAG)
- Knowledge-based question answering
- Summarization using proprietary data
- Chatbots and document-aware assistants
- Semantic document search and matching queries to relevant content

**Reference:** https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html

---

## Data Sources

- Can incorporate an up-to-date product catalog and customer data
- Improves response accuracy and relevance by providing context from company-specific information
- Regularly removing outdated product data ensures the knowledge base remains current

---

## Metadata Filters

- Use the `modification_time` metadata filter to restrict source documents based on timestamps
- Add a metadata filter to ensure only recently updated documents are retrieved

**Reference:** https://docs.aws.amazon.com/bedrock/latest/userguide/kb-test-config.html

---

## Chunking Strategies

### Hierarchical Chunking

- Supports hierarchical chunking as a chunking strategy

**Reference:** https://docs.aws.amazon.com/bedrock/latest/userguide/kb-chunking.html#kb-hiearchical-chunking

### Semantic Chunking

- Resolves the issue of missing information from longer documents by intelligently segmenting text into coherent parts
- Groups content into chunks that follow natural boundaries (e.g., paragraphs, tables, or sections)
- Provides meaningful content divisions while minimizing token waste
- Prevents the fragmentation of financial data across chunks
- The model can summarize the segments individually
- Adjust retrieval token limits to ensure only the most relevant information passes to the model
- Optimize the maximum tokens parameter to achieve the right balance between retrieval accuracy and token usage

**References:**
- https://docs.aws.amazon.com/bedrock/latest/userguide/kb-chunking.html#kb-semantic-chunking
- https://aws.amazon.com/blogs/machine-learning/contextual-retrieval-in-anthropic-using-amazon-bedrock-knowledge-bases/

### Custom Lambda Chunking

- Supports custom chunking through Lambda functions
- Processes documents with highly variable lengths
- A custom Lambda function with LangChain provides a specialized chunking strategy
- Can handle articles and paragraphs of any length, including HTML
- Preserves hierarchical relationships in articles and paragraphs
- Provides control and flexibility for complex document structures

**Reference:** https://docs.aws.amazon.com/bedrock/latest/userguide/kb-custom-transformation.html

---

## Reranking

- Supports reranker models that can reorder retrieval results to improve precision
- Enable reranking and limit the retrieval set to the top-ranked documents
- Maintains accuracy while reducing the tokens passed to the LLM
- Requires minimal effort — change the knowledge base settings directly to improve search precision and reduce token costs
- Provides built-in reranking mechanisms that improve contextual relevance
- Migrate to an Amazon Bedrock knowledge base to offload relevance scoring and avoid manual reranking

**References:**
- https://docs.aws.amazon.com/bedrock/latest/userguide/rerank.html
- https://docs.aws.amazon.com/prescriptive-guidance/latest/retrieval-augmented-generation-options/rag-fully-managed-bedrock.html
