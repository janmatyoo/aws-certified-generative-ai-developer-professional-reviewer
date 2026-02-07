SageMaker Model Registry
- versioning customized models, tracking lineage, and managing approval workflows for model deployment
- provides centralized versioning and metadata for model artifacts
- supports an approval workflow to control which versions can be deployed
- track lineage from training datasets to deployed models

--

SageMaker asynchronous endpoints
- provide long-running inference workloads with processing times up to 15 minutes
- efficiently manage compute resources
- asynchronous endpoints efficiently manage compute resources
- this deployment strategy supports GPU instances for efficient processing, handles large datasets (up to 1 GB), and provides scaling based on actual usage

--

deployment guardrails
- provide controlled traffic shifting to a new model version
- can automatically roll back when CloudWatch alarms indicate failures or regressions

--

SageMaker Model Cards
- to provide structured documentation of FM metadata
- the metadata can include limitations, training context, and intended usage. 
- you can use EventBridge to capture model registration events and invoke Lambda to enforce compliance policies
- this step meets the requirement to centrally document compliance risks and model limitations

https://docs.aws.amazon.com/sagemaker/latest/dg/model-cards.html
https://docs.aws.amazon.com/sagemaker/latest/dg/automating-sagemaker-with-eventbridge.html

--

SageMaker AI shadow tests
- use to deploy a new model variant alongside your production variant on the same endpoint
- the shadow variant receives a copy of the production traffic but does not return responses to users
- you can use shadow tests to compare operational metrics including latency, error rates, and resource utilization without any risk to end users - you do not need to set up or manage separate infrastructure
- SageMaker AI automatically handles the traffic replication and metrics collection
- after the test period, you can promote the shadow variant to production if the new model performs well

--

SageMaker Clarify
- A tool for explaining model predictions and detecting bias.
- Bias detection in training and inference
- Feature importance and explainability
- Supporting responsible AI requirements
- provides comprehensive bias detection capabilities across different demographic groups
- can automatically identify potential unfairness in model responses
- You can use FMEval with CrowS-Pairs datasets to test for stereotypical biases
- CloudWatch metrics provide ongoing monitoring of demographic disparities
- This solution provides a robust framework to detect and measure bias across multiple dimensions by using built-in capabilities of Clarify

- https://docs.aws.amazon.com/sagemaker/latest/dg/clarify-prompt-stereotyping-evaluation.html
- https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/working_with_metrics.html
- https://docs.aws.amazon.com/sagemaker/latest/dg/clarify-foundation-model-evaluate-whatis.html

--

SageMaker Model Monitor
- a fully managed service that provides continuous monitoring of production ML models
- runs scheduled jobs by using custom images
- this approach can compute embedding-level drift metrics by comparing captured inference data (the data capture logs) against a baseline dataset
- storing the final violation reports in Amazon S3 ensures that you have an auditable record of drift events

https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html
https://aws.amazon.com/blogs/machine-learning/detect-nlp-data-drift-using-custom-amazon-sagemaker-model-monitor/

--

Data Capture
- a SageMaker AI feature that you can use to log actual production interactions on real-time or batch-transform endpoints
- reliably logs requests and responses to Amazon S3
- ensures that you can use responses for further drift detection and analysis
- The UpdateEndpoint API call shifts SageMaker AI endpoint traffic to the new instances with the updated endpoint configuration
- the call deletes the old instances by using the previous configuration
- this step maintains availability and creates an intrinsic blue/green deployment.

https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-data-capture.html
https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-data-quality.html
https://docs.aws.amazon.com/sagemaker/latest/APIReference/API_UpdateEndpoint.html

---

Amazon Cognito managed work team
- you can create a new one by using the Amazon Bedrock console
- you must manage **human evaluators as a work team**
- for the fashion experts to evaluate the models, you must organize the fashion experts into a work team

https://docs.aws.amazon.com/sagemaker/latest/dg/sms-workforce-management-private-cognito.html
https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-jobs-management-create-human.html

---

Ground Truth
- creates its own model as images are labeled by people
- As this model learns, only images the model isn’t sure about are sent to human labelers
- This can reduce the cost of labeling jobs by 70%

Human Labelers
- Mechanical Turk
- Your own internal team
- Professional labeling companies