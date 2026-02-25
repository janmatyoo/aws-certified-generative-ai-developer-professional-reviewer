# Bedrock Data Automation (BDA)

- Extracts insights from unstructured multimodal content including documents, forms, and A/V recordings
- Streamlines the processing of diverse financial data sources
- Can automatically create knowledge bases for RAG workflows
- Automatically handles the processing of different data types and their integration with Knowledge Bases
- Requires the least operational overhead

**References:**
- https://docs.aws.amazon.com/bedrock/latest/userguide/bda.html
- https://aws.amazon.com/blogs/machine-learning/part-3-building-an-ai-powered-assistant-for-investment-research-with-multi-agent-collaboration-in-amazon-bedrock-and-amazon-bedrock-data-automation/

---

## Transformations

- Can split complex fields into structured components (e.g., splitting full names)
- Use a custom type to define and reuse field structures such as AuthorizedSigner or ReviewerName across fields

**Reference:** https://docs.aws.amazon.com/bedrock/latest/userguide/idp-cases-transformation.html

---

## Blueprints

- Fully managed document processing service that automates data extraction from documents using AI
- Blueprints are templates that define the structure and rules to process specific document types
- Use a single project with multiple blueprints to streamline management while maintaining functionality
- BDA automatically detects which blueprint to apply based on the document type
- Handles field extraction without requiring custom code maintenance or multiple service orchestration

**Reference:** https://docs.aws.amazon.com/bedrock/latest/userguide/bda.html
