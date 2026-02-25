# Amazon SageMaker

## Model Registry

- Versions customized models, tracks lineage, and manages approval workflows for model deployment
- Provides centralized versioning and metadata for model artifacts
- Supports an approval workflow to control which versions can be deployed
- Tracks lineage from training datasets to deployed models

---

## Asynchronous Endpoints

- Designed for long-running inference workloads with processing times up to 15 minutes
- Supports GPU instances for efficient processing
- Handles large datasets (up to 1 GB)
- Scales based on actual usage

---

## Deployment Guardrails

- Provides controlled traffic shifting to a new model version
- Automatically rolls back when CloudWatch alarms indicate failures or regressions

---

## Model Cards

- Provides structured documentation of FM metadata including limitations, training context, and intended usage
- Use EventBridge to capture model registration events and invoke Lambda to enforce compliance policies
- Centralizes documentation of compliance risks and model limitations

**References:**
- https://docs.aws.amazon.com/sagemaker/latest/dg/model-cards.html
- https://docs.aws.amazon.com/sagemaker/latest/dg/automating-sagemaker-with-eventbridge.html

---

## Shadow Tests

- Deploys a new model variant alongside the production variant on the same endpoint
- The shadow variant receives a copy of production traffic but does not return responses to users
- Compare operational metrics (latency, error rates, resource utilization) without risk to end users
- No need to set up or manage separate infrastructure — SageMaker handles traffic replication and metrics collection
- After the test period, the shadow variant can be promoted to production if the new model performs well

---

## Clarify

- Detects bias in training and inference
- Provides feature importance and explainability
- Supports responsible AI requirements
- Provides comprehensive bias detection across different demographic groups
- Automatically identifies potential unfairness in model responses
- Use FMEval with CrowS-Pairs datasets to test for stereotypical biases
- CloudWatch metrics provide ongoing monitoring of demographic disparities

**References:**
- https://docs.aws.amazon.com/sagemaker/latest/dg/clarify-prompt-stereotyping-evaluation.html
- https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/working_with_metrics.html
- https://docs.aws.amazon.com/sagemaker/latest/dg/clarify-foundation-model-evaluate-whatis.html

---

## Model Monitor

- Fully managed service for continuous monitoring of production ML models
- Runs scheduled jobs using custom images
- Computes embedding-level drift metrics by comparing captured inference data against a baseline dataset
- Stores final violation reports in Amazon S3 for an auditable record of drift events

**References:**
- https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html
- https://aws.amazon.com/blogs/machine-learning/detect-nlp-data-drift-using-custom-amazon-sagemaker-model-monitor/

---

## Data Capture

- Logs actual production interactions on real-time or batch-transform endpoints
- Reliably logs requests and responses to Amazon S3
- Ensures responses can be used for drift detection and analysis
- The `UpdateEndpoint` API call shifts endpoint traffic to new instances with the updated configuration, deletes old instances, and creates an intrinsic blue/green deployment

**References:**
- https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-data-capture.html
- https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-data-quality.html
- https://docs.aws.amazon.com/sagemaker/latest/APIReference/API_UpdateEndpoint.html

---

## Cognito Managed Work Team

- Create a new work team using the Amazon Bedrock console
- Human evaluators must be organized as a work team for model evaluation

**References:**
- https://docs.aws.amazon.com/sagemaker/latest/dg/sms-workforce-management-private-cognito.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-jobs-management-create-human.html

---

## Ground Truth

- Creates its own model as images are labeled by people
- As the model learns, only images it is unsure about are sent to human labelers
- Can reduce the cost of labeling jobs by 70%

### Human Labelers

- Amazon Mechanical Turk
- Your own internal team
- Professional labeling companies
