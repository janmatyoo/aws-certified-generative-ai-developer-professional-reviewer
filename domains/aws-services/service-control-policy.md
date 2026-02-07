Service Control Policy (SCP)
- are an organization policy that you can use to manage permissions across accounts in an organization
- enforces this control **regardless of the IAM configuration** in the accounts
- this solution ensures that Amazon Bedrock actions are denied unless the requests originate from an approved VPC endpoint


https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html


- You can **apply SCPs at the OU level** to provide an organizational guardrail that blocks non-approved actions
- this solution enforces RBAC, least privilege, and centralized governance