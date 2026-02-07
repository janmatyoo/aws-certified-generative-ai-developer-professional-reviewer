Knowledge Base
- store and search data by meaning
- use for retrieval-augmented generation (RAG)
- use for knowledge-based question answering
- use for summarization using proprietary data
- use for chatbots
- use for document-aware chatbots
- use for semantic document search
- use for matching queries to relevant content
- use for retrieval in RAG workflows
- provides built-in capabilities to **integrate multiple document sources** through standardized connectors
- handles authentication, synchronization, and content updates automatically
- this solution requires the least operational overhead
- this solution provides **consistent access patterns** across all document sources
- this solution **maintains data freshness** through **automated synchronization**

- can incorporate an up-to-date product catalog and customer data
- this configuration improves response accuracy and relevance by providing context from the company's specific information
- regularly removing outdated product data ensures that the knowledge base remains current

- a fully managed end-to-end RAG workflow
- integrates with OpenSearch Serverless as a vector store
- supports Amazon S3 as a data source
- supports **hierarchical chunking** as a chunking strategy
- This solution provides a fully managed end-to-end RAG workflow
- a managed RAG service that you can use to securely connect an LLM to enterprise data

https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html


- You can use the metadata filter modification_time to restrict the source documents based on timestamps
- You can add a metadata filter to ensure that the model retrieves only recently updated documents

https://docs.aws.amazon.com/bedrock/latest/userguide/kb-test-config.html

https://docs.aws.amazon.com/prescriptive-guidance/latest/retrieval-augmented-generation-options/rag-fully-managed-bedrock.html
https://docs.aws.amazon.com/bedrock/latest/userguide/kb-chunking.html#kb-hiearchical-chunking


- support reranker models that can reorder retrieval results to improve precision
- you can enable reranking and limit the retrieval set to the top five ranked documents
- this solution maintains accuracy while reducing the tokens that pass to the LLM
- this solution requires minimal effort because you can directly make a change in the knowledge base to improve search precision and reduce token costs

https://docs.aws.amazon.com/bedrock/latest/userguide/rerank.html



- **supports custom chunking** through Lambda functions
- this solution can process documents with highly variable lengths
- a custom Lambda function with **LangChain** provides a **specialized chunking strategy**
- this solution can properly handle articles and paragraphs of any length **(HTML)**
- this solution can preserve the hierarchical relationships in the articles and paragraphs
- this solution provides the control and flexibility that you need for **complex document structures**

https://docs.aws.amazon.com/bedrock/latest/userguide/kb-custom-transformation.html


- supports **semantic chunking**
- Semantic chunking resolves the issue of missing information from longer documents by intelligently segmenting the text into coherent parts
- the model can summarize the segments individually


https://docs.aws.amazon.com/bedrock/latest/userguide/kb-chunking.html#kb-semantic-chunking

- semantic chunking can group content into chunks that follow natural boundaries
    - For example, natural boundaries include paragraphs, tables, or section
- semantic chunking provides meaningful content divisions while **minimizing token waste**
- semantic chunking can **prevent the fragmentation** of financial data across chunks
- you c**an adjust retrieval token limits** to ensure that o**nly the most relevant information passes** to the model
- this solution lowers costs while preserving comprehension
- you can **optimize the maximum tokens parameter** to achieve the right balance between **retrieval accuracy and token usage**

https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html
https://docs.aws.amazon.com/bedrock/latest/userguide/kb-chunking.html#kb-semantic-chunking
https://aws.amazon.com/blogs/machine-learning/contextual-retrieval-in-anthropic-using-amazon-bedrock-knowledge-bases/





- provides **built-in reranking mechanisms** that **improve contextual relevance**
- you can **migrate** to an Amazon Bedrock knowledge base to **offload** relevance scoring
    - this strategy avoids manual reranking





