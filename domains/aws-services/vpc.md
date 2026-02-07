Interface VPC endpoints or AWS PrivateLink
- create a private connection between your VPC and Amazon Bedrock
- allow Lambda functions in private subnets to access Amazon Bedrock APIs without internet connectivity
- the Runtime service requires the com.amazonaws.region.bedrock-runtime endpoint for model invocation operations
- security groups must allow outbound HTTPS traffic on port 443 from Lambda to the VPC endpoint
- the endpoint's security group must allow inbound HTTPS traffic
- private DNS is enabled by default, so existing Lambda code can continue to work without modification
- AWS automatically routes API calls through the VPC endpoint.
- provide private connectivity to Amazon Bedrock within the AWS network



https://docs.aws.amazon.com/bedrock/latest/userguide/vpc-interface-endpoints.html



- can create a VPC endpoint for the Runtime service to provide secure, **private access** to Amazon Bedrock directly through the AWS network
    - this solution provides API calls **without internet access**
    - This solution maintains security through **private networking**
    - This solution **supports logging through VPC Flow Logs and CloudTrail**

https://docs.aws.amazon.com/bedrock/latest/userguide/vpc-interface-endpoints.html
https://docs.aws.amazon.com/vpc/latest/privatelink/create-interface-endpoint.html
