# Amazon Q Business

- Fully managed Gen-AI assistant for employees
- Based on your company's knowledge and data
- Built on Amazon Bedrock (the underlying FM cannot be changed)
- Admin Controls = Guardrails

---

## Data Source Connectors

- Managed integration points that provide secure connections to external content systems
- Uses built-in connectors to integrate content securely
- Uses IAM Identity Center for enterprise-grade authentication and RBAC
- Meets compliance requirements without custom development

**References:**
- https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/data-sources.html
- https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/security-iam.html

---

## Automatic Content Synchronization

- Updates knowledge bases from source systems in real time
- Security group mapping provides automatic access control based on existing enterprise roles
- Uses built-in capabilities to maintain current content and enforce proper access controls
- Does not require additional services or custom code
