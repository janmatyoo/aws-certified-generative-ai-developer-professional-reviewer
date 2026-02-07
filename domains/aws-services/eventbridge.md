EventBridge
- to validate model outputs after inference, you can configure an application workflow or an EventBridge rule to trigger the function based on inference-related events
- this step provides output filtering and enforcement during inference.
- after inference, this step provides automated compliance workflows programmatically.

https://docs.aws.amazon.com/bedrock/latest/userguide/monitoring-eventbridge-how-it-works.html


- provides **built-in time-based event handling** capabilities
- this solution effectively uses these built-in features
- you can configure guardrails with appropriate tags for different contexts
- you can use EventBridge to **handle time-based guardrail** selection automatically
- this solution provides the least operational overhead by using built-in AWS services without requiring additional databases or complex orchestration


- provides serverless **event routing** that directly integrates with **Step Functions**
- can consume S3 events
- supports advanced **prefix-based filtering**
- this step provides clinic-specific routing without additional code
- this step minimizes cost by eliminating intermediary Lambda functions (no per-invocation charges) and by providing direct state machine triggering.
- pricing is based on the number of published events and matched rules.
- this step provides pricing that is far lower than maintaining and invoking a Lambda for every event

https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html
https://docs.aws.amazon.com/step-functions/latest/dg/eventbridge-integration.html#eventbridge-stepfunctions-as-target
