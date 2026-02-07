IAM Identity Center
- provides centralized identity federation **with Active Directory**
- provides consistent **permissions across multiple account**s through permission sets
- this solution supports **department-based access control** to AWS resources including Amazon Bedrock models
- this solution supports **Regional failover for resilience**
- is a centralized service to **manage user access and permissions across AWS accounts**

https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html

- provides centralized workforce access with support for SAML federation to enterprise IdPs
- you can configure permissions sets that **enforce least privilege** IAM policies to scope access to specific Amazon Bedrock model actions for each department


https://docs.aws.amazon.com/singlesignon/latest/userguide/manage-your-identity-source-idp.html
https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html



---

IAM Identity Center with SAML federation
- can provide secure authentication and integration with the IdP
- eliminates long-lived credentials by providing temporary security credentials
- provides audit logging through AWS CloudTrail
- meets all the requirements by integrating with the existing IdP while maintaining secure access control

---

IAM Identity Center 
- can be use as a centralized way to manage access to multiple AWS accounts and applications
- supports federation with external IdPs, including SCIM or Entra ID through SAML
- this step provides centralized access control
- this step integrates with the company's existing Entra ID system
- this step provides support to enforce job role–based access to Amazon Bedrock.

https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_federated-users.html


IAM SAML Based federation
- allows Entra ID users to assume IAM roles by using SAML
- you can map IAM roles to Entra ID groups to enforce job role–based access policies
- IAM SAML-based federation between Entra ID and IAM is a well-established pattern for enterprise identity federation
- this step provides direct integration with the existing IdP
- This step ensures that only authorized employees can access Amazon Bedrock

https://docs.aws.amazon.com/singlesignon/latest/userguide/idp-microsoft-entra.html




