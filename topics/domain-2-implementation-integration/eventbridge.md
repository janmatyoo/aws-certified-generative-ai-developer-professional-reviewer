# Amazon EventBridge

## Post-Inference Output Validation

- Configure an EventBridge rule to trigger a function based on inference-related events to validate model outputs after inference
- Provides output filtering and enforcement during inference
- Enables automated compliance workflows programmatically after inference

**Reference:** https://docs.aws.amazon.com/bedrock/latest/userguide/monitoring-eventbridge-how-it-works.html

---

## Time-Based Guardrail Selection

- Provides built-in time-based event handling capabilities
- Configure guardrails with appropriate tags for different contexts
- Use EventBridge to handle time-based guardrail selection automatically
- Provides the least operational overhead using built-in AWS services without requiring additional databases or complex orchestration

---

## Prefix-Based Event Routing

- Provides serverless event routing that directly integrates with Step Functions
- Consumes S3 events and supports advanced prefix-based filtering
- Enables clinic-specific routing without additional code
- Eliminates intermediary Lambda functions, reducing per-invocation charges by directly triggering state machines
- Pricing is based on the number of published events and matched rules

**References:**
- https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html
- https://docs.aws.amazon.com/step-functions/latest/dg/eventbridge-integration.html#eventbridge-stepfunctions-as-target
