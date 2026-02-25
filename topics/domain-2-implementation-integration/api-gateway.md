# Amazon API Gateway

## WebSocket APIs

- Provide managed, bidirectional communication channels suitable for streaming data
- The `InvokeModelWithResponseStream` API provides token-by-token streaming of model responses
- Lambda functions can process streams and forward tokens through WebSocket connections to clients
- Provides real-time streaming with minimal latency and development effort
- Maintains scalable, persistent connections

**References:**
- https://docs.aws.amazon.com/bedrock/latest/APIReference/API_runtime_InvokeModelWithResponseStream.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/inference-invoke.html#inference-examples-stream
- https://docs.aws.amazon.com/bedrock/latest/userguide/latency-optimized-inference.html
- https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-websocket-api.html

---

## Non-Proxy Integrations with Mapping Templates

- Provide request and response transformation without code changes
- Combine header-based routing with stage variables for dynamic provider selection
- Mapping templates can be configured to transform requests and responses for consistent formatting across different providers
- Secrets Manager provides secure API key storage
- Built-in caching capabilities optimize costs by caching responses when appropriate

**Reference:** https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-mapping-template-reference.html
