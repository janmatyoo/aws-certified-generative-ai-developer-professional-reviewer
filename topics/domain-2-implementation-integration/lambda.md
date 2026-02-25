# AWS Lambda

- Serverless compute service for data processing tasks

---

## WebSocket Streaming

- Requires specific IAM permissions to invoke Amazon Bedrock models with streaming and to manage WebSocket connections
- Resource ARNs must include the specific API Gateway WebSocket API ID to properly scope the permissions
- Uses the API Gateway Management API to stream Amazon Bedrock responses back to clients in real time

**References:**
- https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-websocket-api-overview.html
- https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-websocket-api-integration-requests.html

---

## Throttling & Retry Handling

- Configure exponential backoff with jitter in the AWS SDK — the recommended client-side pattern for handling transient errors such as `ThrottlingException`
- Exponential backoff with jitter avoids overwhelming the API with retries
- Configure throttling limits in API Gateway as a server-side protection mechanism to manage request bursts from clients
- Improves reliability without breaking the synchronous, low-latency user experience

**References:**
- https://docs.aws.amazon.com/sdkref/latest/guide/feature-retry-behavior.html
- https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-request-throttling.html
- https://docs.aws.amazon.com/bedrock/latest/userguide/troubleshooting-api-error-codes.html#ts-throttling-exception
