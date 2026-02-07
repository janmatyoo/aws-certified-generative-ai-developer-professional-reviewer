Model Evaluation
- enables users to test, compare, and evaluate foundation models (FMs) and Retrieval-Augmented Generation (RAG) systems using automatic or human review
- can produce computed scores and metrics that help you assess the effectiveness of a model and knowledge base
- assesses the sensitivity of generated responses based on small variations in the input questions
- human-based model evaluations require a custom prompt dataset in JSONL format that is stored in an S3 bucket
- for jobs that you create through the console, you must update the CORS configuration in the S3 bucket.

**Evaluation Methods:**
- Support custom prompt datasets
- Automatic (Programmatic) Evaluation: Uses curated or custom datasets to compute metrics like accuracy, robustness, and toxicity.
- LLM-as-a-Judge: Uses high-performing models to evaluate outputs for quality, faithfulness, and safety.
- Human Evaluation: Allows using internal teams or AWS-managed teams for subjective metrics like relevance and brand voice.


- https://aws.amazon.com/bedrock/evaluations/
- https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-prompt-datasets.html#model-evaluation-prompt-datasets-custom
https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-jobs-management-create-human.html



CreateEvaluationJob API
- with a consistent evaluator model provides a mechanism to run managed evaluation jobs that can scale across large datasets
- by using a **consistent evaluator model**, Amazon Bedrock provides h**uman-like judgment** on **nuanced** conversational qualities
- the qualities include relevance, tone, factual accuracy, and generated built-in responsible AI metrics with confidence intervals
- Lambda can then analyze outputs by using **Spearman's rank correlation** to statistically **compare model performance**
- this solution uses the Amazon Bedrock managed evaluation framework.
- this solution minimizes operational overhead because you do not need to build a custom pipeline

https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-tasks.html


- model evaluation jobs have a **quota of 1,000 prompts for each dataset**
- the 5,000-prompt dataset exceeds the quota and causes the job to fail
- you can split the prompts into smaller datasets such as five datasets of 1,000 prompts each
- you can run separate evaluation jobs to resolve the issue

https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-prompt-datasets.html

















