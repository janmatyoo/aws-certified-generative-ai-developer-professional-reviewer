# AWS Glue

## Glue Crawler

- Crawls a data source and infers the schema and metadata
- Stores the data in Data Catalog

---

## Glue ETL

- Provides serverless extract, transform, and load functionality

---

## Data Quality

- Provides both rule-based validation and ML-powered anomaly detection capabilities
- Evaluates data quality against custom rules written in DQDL
- Detects anomalies by analyzing data statistics over time
- Publishes results to EventBridge for automated alerting when quality issues are detected

**Reference:** https://docs.aws.amazon.com/glue/latest/dg/data-quality-anomaly-detection.html

---

## Data Quality Definition Language (DQDL)

- Rules that implement data validation during ETL processing
- Filters out low-quality data before it reaches Amazon Bedrock
- Prevents potential issues with model outputs
- Integrates validation directly into the data processing pipeline without requiring additional services or custom code

**References:**
- https://docs.aws.amazon.com/glue/latest/dg/dqdl.html
- https://docs.aws.amazon.com/glue/latest/dg/tutorial-data-quality.html
