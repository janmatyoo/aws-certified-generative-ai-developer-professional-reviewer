# Model Evaluation

- Tests, compares, and evaluates foundation models (FMs) and RAG systems using automatic or human review
- Produces computed scores and metrics to assess the effectiveness of a model and knowledge base
- Assesses the sensitivity of generated responses based on small variations in input questions
- Human-based evaluations require a custom prompt dataset in JSONL format stored in an S3 bucket
- For jobs created through the console, update the CORS configuration in the S3 bucket

---

## Evaluation Methods

- **Automatic**: Uses curated or custom datasets to compute metrics like accuracy, robustness, and toxicity
- **LLM-as-a-Judge**: Uses high-performing models to evaluate outputs for quality, faithfulness, and safety
- **Human Evaluation**: Uses internal teams or AWS-managed teams for subjective metrics like relevance and brand voice

**References:**
- https://aws.amazon.com/bedrock/evaluations/
- https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-prompt-datasets.html#model-evaluation-prompt-datasets-custom
- https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-jobs-management-create-human.html

---

## CreateEvaluationJob API

- Runs managed evaluation jobs that can scale across large datasets with a consistent evaluator model
- Provides human-like judgment on nuanced conversational qualities including relevance, tone, factual accuracy, and responsible AI metrics with confidence intervals
- Lambda can analyze outputs using Spearman's rank correlation to statistically compare model performance
- Minimizes operational overhead by using the Amazon Bedrock managed evaluation framework

**Reference:** https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-tasks.html

---

## Limits

- Model evaluation jobs have a quota of **1,000 prompts per dataset**
- A 5,000-prompt dataset exceeds the quota and causes the job to fail
- Split large datasets into smaller ones (e.g., five datasets of 1,000 prompts each) and run separate evaluation jobs

**Reference:** https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-prompt-datasets.html
