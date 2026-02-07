Bedrock Data Automation (BDA)
- extracts insights from unstructured multimodal content including documents, forms, and A/V recordings
- streamlines the processing of diverse financial data sources
- can automatically create knowledge bases for RAG workflows
- this solution automatically handles the processing of different data types and the integration with Knowledge Bases
- this solution requires the least operational overhead


https://docs.aws.amazon.com/bedrock/latest/userguide/bda.html
https://aws.amazon.com/blogs/machine-learning/part-3-building-an-ai-powered-assistant-for-investment-research-with-multi-agent-collaboration-in-amazon-bedrock-and-amazon-bedrock-data-automation/


- transformation can split complex fields into structured components
- transformation can split full names
- you can use a custom type to define and reuse this structure across fields such as AuthorizedSigner or ReviewerName.

https://docs.aws.amazon.com/bedrock/latest/userguide/idp-cases-transformation.html



- is a fully managed document processing service that automates the extraction of data from documents by using AI
- **BDA blueprints** are templates that define the structure and **rules to process specific document types**
- you can use a **single project with multiple blueprints** to streamline management while maintaining functionality
- BDA a**utomatically detects the blueprint** to use based on the document type
- BDA handles field extraction, This solution **does not require custom code maintenance** or **multiple service orchestration**

https://docs.aws.amazon.com/bedrock/latest/userguide/bda.html
