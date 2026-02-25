# Service Control Policy (SCP)

- Organization policy used to manage permissions across accounts in an organization
- Enforces controls regardless of the IAM configuration in the accounts
- Ensures Amazon Bedrock actions are denied unless requests originate from an approved VPC endpoint

**Reference:** https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html

---

## OU-Level SCPs

- Apply SCPs at the OU level to provide an organizational guardrail that blocks non-approved actions
- Enforces RBAC, least privilege, and centralized governance
