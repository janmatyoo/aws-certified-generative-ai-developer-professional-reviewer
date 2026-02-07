AWS AppConfig
- externalize model selection parameters, allowing runtime configuration changes without code deployments or service interruptions
- enable gradual rollout of new models, A/B testing between models, and quick rollbacks if performance issues arise



SCPs and cross account access
- provide organization-wide preventive controls
- can effectively deny access to marketplace models across all accounts
- can scope bedrock:InvokeModel* actions to only approved AWS and Anthropic model IDs
- can deny all other marketplace models


Cross-region

Identity Center + SAML for 3rd party access
Identity Center + OIDC for temporary access
Multi-KB for separation of domains
Multi inference profiles for multi-tenant inference and cost management


