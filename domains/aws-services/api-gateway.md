API Gateway WebSocket APIs
- provide managed, bidirectional communication channels that are suitable to stream data
- The InvokeModelWithResponseStream API provides token-by-token streaming of model responses
- Lambda functions can efficiently process the streams and forward tokens through WebSocket connections to clients
- This solution provides real-time streaming with minimal latency and development effort
- This solution maintains scalable, persistent connections.

https://docs.aws.amazon.com/bedrock/latest/APIReference/API_runtime_InvokeModelWithResponseStream.html
https://docs.aws.amazon.com/bedrock/latest/userguide/inference-invoke.html#inference-examples-stream
https://docs.aws.amazon.com/bedrock/latest/userguide/latency-optimized-inference.html
https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-websocket-api.html



API Gateway **non-proxy integrations** with mapping templates
- provide request and response transformation without code changes
- you can combine header-based routing with stage variables for dynamic provider selection
- mapping templates
    - can be configured to transform request and responses to be consistent
    - ensure consistent response formatting across different providers
- secrets Manager provides secure API key storage
- the API Gateway built-in caching capabilities optimize costs by caching responses when appropriate

https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-mapping-template-reference.html
