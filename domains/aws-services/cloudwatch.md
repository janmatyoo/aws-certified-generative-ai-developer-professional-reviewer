CloudWatch
- solution to monitor the built-in Guardrails metric InvocationsIntervened
    - this solution uses EventBridge with Lambda for automated compliance workflows
    - this solution minimizes operational overhead by using built-in service features and integrations


CloudWatch Logs
- can capture full prompt and response data


CloudWatch Synthetics
- provides continuous, automated checks that simulate end-to-end usage



CloudWatch dashboards
- provide a customizable view of metrics and alarms
- provide a visual correlation of data from multiple sources
- you can combine context-retrieval latency metrics from OpenSearch with operation counts to find a direct correlation between vector search performance and overall response times
- you can analyze Amazon Bedrock invocation logs to help identify specific knowledge base queries that are causing issues
- Amazon Bedrock invocation logs contain detailed information about model interactions
- This solution uses built-in metrics and logs with the least operational overhead.

https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/create_dashboard.html


