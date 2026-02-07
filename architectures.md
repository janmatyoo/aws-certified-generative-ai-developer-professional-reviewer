Your application needs to dynamically select the most appropriate foundation model based on the type of user query.

Which architecture would best support this requirement without requiring code changes for each new model?

"API Gateway → Lambda (Router) → AppConfig (Model Configuration)
- It centralizes the routing logic in a single Lambda function that can be updated without changing the API
- AppConfig allows dynamic configuration updates without redeploying code
- The router can use sophisticated logic to select the appropriate model based on query content, user preferences, or other factors
- New models can be added by updating the configuration in AppConfig and adding a new Lambda function
- This architecture maintains a consistent API interface for clients regardless of which model is used




Which architectural patterns support dynamic model switching without code deployment when using Amazon Bedrock? 
- Using AWS AppConfig to store model configurations and AWS Lambda environment variables
    - AWS AppConfig enables runtime configuration changes and model switching without code deployments.
- Using Amazon API Gateway with AWS Lambda integration and feature flags in AWS AppConfig
    - his combination enables dynamic routing and configuration updates while supporting A/B testing.


Which combination of AWS services BEST supports Regional resilience for a mission-critical generative AI (GenAI) application?
- Amazon Bedrock with multi-Region deployment and Amazon Route 53 health checks
    - This approach combines Regional model availability with intelligent routing and automated health checking for maximum resilience.



When evaluating text summarization models in Amazon Bedrock for a production system that requires consistent performance, which evaluation result would indicate the BEST model selection?
- The model shows minimal variation with a robustness score of 8.5%, maintaining consistent summary quality even when input text has slight variations or noise.
    - A robustness score of 8.5% indicates strong model stability. This means that when the input text is slightly modified (perturbed), the model continues to produce consistently similar summaries. This level of consistency is crucial for production systems where reliability and predictability are essential.

