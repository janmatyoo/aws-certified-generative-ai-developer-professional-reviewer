Lambda function
- requires specific IAM permissions to both invoke Amazon Bedrock models with streaming and to manage WebSocket connections
- the resource ARNs must include the specific API Gateway WebSocket API ID to properly scope the permissions.
- uses the API Gateway Management API to stream Amazon Bedrock responses back to clients in real time.
- is a serverless compute service that you can use for data processing tasks


https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-websocket-api-overview.html
https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-websocket-api-integration-requests.html




- Configuring **exponential backoff with jitter** in the AWS SDK
- is the recommended client-side pattern to handle transient errors such as **ThrottlingException**
- Exponential backoff with jitter a**voids overwhelming the API with retries**
- **Configuring throttling limits** in API Gateway is a server-side protection mechanism that **manages request bursts** from clients
- This solution ensures that the backend services remain stable and responsive for all users
- This solution **improves reliability** without breaking the synchronous, low-latency user experience.

https://docs.aws.amazon.com/sdkref/latest/guide/feature-retry-behavior.html
https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-request-throttling.html
https://docs.aws.amazon.com/bedrock/latest/userguide/troubleshooting-api-error-codes.html#ts-throttling-exception



