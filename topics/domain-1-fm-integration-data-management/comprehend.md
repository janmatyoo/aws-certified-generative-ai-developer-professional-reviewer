# Amazon Comprehend

- Fully managed NLP service — requires no model hosting

---

## Custom Classification

- Trains a custom model to classify text into user-defined labels (e.g., billing, technical support)
- Detects and redacts sensitive information from text data in Amazon S3
- Enables dynamic routing to specialized Amazon Bedrock FMs based on the detected support topic

**Reference:** https://docs.aws.amazon.com/comprehend/latest/dg/concepts-custom.html

---

## Entity Recognition

- Extracts structured information from text and helps standardize product attributes
- Used via Lambda for integration into processing pipelines

**References:**
- https://docs.aws.amazon.com/comprehend/latest/dg/how-entities.html
- https://docs.aws.amazon.com/lambda/latest/dg/welcome.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-tasks-general-text.html
