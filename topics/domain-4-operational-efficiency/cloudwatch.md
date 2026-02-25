# Amazon CloudWatch

- Monitors the built-in Guardrails metric `InvocationsIntervened`
  - Uses EventBridge with Lambda for automated compliance workflows
  - Minimizes operational overhead using built-in service features and integrations

---

## CloudWatch Logs

- Captures full prompt and response data

---

## CloudWatch Synthetics

- Provides continuous, automated checks that simulate end-to-end usage

---

## CloudWatch Dashboards

- Provide a customizable view of metrics and alarms
- Provide a visual correlation of data from multiple sources
- Combine context-retrieval latency metrics from OpenSearch with operation counts to find a direct correlation between vector search performance and overall response times
- Analyze Amazon Bedrock invocation logs to identify specific knowledge base queries causing issues
- Amazon Bedrock invocation logs contain detailed information about model interactions

**Reference:** https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/create_dashboard.html
