# VPC Endpoints / AWS PrivateLink

- Creates a private connection between your VPC and Amazon Bedrock
- Allows Lambda functions in private subnets to access Amazon Bedrock APIs without internet connectivity
- The Runtime service requires the `com.amazonaws.region.bedrock-runtime` endpoint for model invocation operations
- Security groups must allow outbound HTTPS traffic on port 443 from Lambda to the VPC endpoint
- The endpoint's security group must allow inbound HTTPS traffic
- Private DNS is enabled by default, so existing Lambda code can continue to work without modification
- AWS automatically routes API calls through the VPC endpoint
- Provides private connectivity to Amazon Bedrock within the AWS network
- API calls remain within the AWS network without internet access
- Supports logging through VPC Flow Logs and CloudTrail

**References:**
- https://docs.aws.amazon.com/bedrock/latest/userguide/vpc-interface-endpoints.html
- https://docs.aws.amazon.com/vpc/latest/privatelink/create-interface-endpoint.html
