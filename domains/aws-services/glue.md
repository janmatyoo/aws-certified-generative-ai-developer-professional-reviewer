Glue Crawler
- crawl a data source and infer the schema and metadata
- can store the data in Data Catalog

Glue ETL
- provides serverless extract, transform, and load functionality


Data Quality
- provides both rule-based validation and ML-powered anomaly detection capabilities
- can evaluate data quality against custom rules that are written in DQDL
- can detect anomalies by analyzing data statistics over time
- you can publish results to **EventBridge**
- **EventBridge** provides automated alerting when quality issues are detected
- this step provides custom validation rules and anomaly detection over time.

https://docs.aws.amazon.com/glue/latest/dg/data-quality-anomaly-detection.html


Data Quality with Data Quality Definition Language (DQDL) 
- rules that can be used to implement data validation during ETL processing
- this step can filter out low-quality data before the data reaches Amazon Bedrock
- this step prevents potential issues with model outputs
- this approach integrates validation directly into the data processing pipeline without requiring additional services or custom code

https://docs.aws.amazon.com/glue/latest/dg/dqdl.html
https://docs.aws.amazon.com/glue/latest/dg/tutorial-data-quality.html
