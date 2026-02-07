Comprehend
- detects and redacts sensitive information from text data in Amazon S3
- custom classification to train a custom model to classify text into labels
- this solution can detect user-defined categories, such as billing and technical support
- is fully managed and requires no model hosting
- this solution provides dynamic routing to specialized Amazon Bedrock FMs depending on the detected support topic

https://docs.aws.amazon.com/comprehend/latest/dg/concepts-custom.html


- (use through lambda) has entity recognition capabilities that extract structured information from text and help standardize product attributes


https://docs.aws.amazon.com/comprehend/latest/dg/how-entities.html
https://docs.aws.amazon.com/lambda/latest/dg/welcome.html
https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-tasks-general-text.html