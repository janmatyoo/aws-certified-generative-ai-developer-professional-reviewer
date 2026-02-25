# IAM Identity Center

- Centralized service to manage user access and permissions across AWS accounts
- Provides centralized identity federation with Active Directory
- Provides consistent permissions across multiple accounts through permission sets
- Supports department-based access control to AWS resources including Amazon Bedrock models
- Supports Regional failover for resilience
- Provides centralized workforce access with support for SAML federation to enterprise IdPs
- Configure permission sets that enforce least privilege IAM policies to scope access to specific Amazon Bedrock model actions for each department

**References:**
- https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html
- https://docs.aws.amazon.com/singlesignon/latest/userguide/manage-your-identity-source-idp.html
- https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html

---

## SAML Federation

- Provides secure authentication and integration with the IdP
- Eliminates long-lived credentials by providing temporary security credentials
- Provides audit logging through AWS CloudTrail
- Integrates with the existing IdP while maintaining secure access control

---

## IAM Identity Center with Entra ID

- Centralized way to manage access to multiple AWS accounts and applications
- Supports federation with external IdPs, including SCIM or Entra ID through SAML
- Provides centralized access control and integrates with the company's existing Entra ID system
- Enforces job role-based access to Amazon Bedrock

**Reference:** https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_federated-users.html

---

## IAM SAML-Based Federation

- Allows Entra ID users to assume IAM roles using SAML
- Map IAM roles to Entra ID groups to enforce job role-based access policies
- Well-established pattern for enterprise identity federation
- Provides direct integration with the existing IdP
- Ensures only authorized employees can access Amazon Bedrock

**Reference:** https://docs.aws.amazon.com/singlesignon/latest/userguide/idp-microsoft-entra.html
