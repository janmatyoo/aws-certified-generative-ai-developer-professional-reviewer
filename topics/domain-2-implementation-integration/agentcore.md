# AgentCore

## AgentCore Runtime with Strands Agent

- Builds AI agents with built-in MCP support
- A prebuilt MCP server can directly expose Aurora inventory and store data as MCP tools
  - Eliminates the need for custom containers or API management
  - Provides natural language access to data
  - Automates supply chain actions with minimal operational overhead — Amazon Bedrock handles orchestration and hosting

**Reference:** https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/agents-tools-runtime.html

---

## AgentCore Identity

- Supports Microsoft Entra ID as an inbound IdP for OIDC authentication
- Configure the discovery URL to the Microsoft v2.0 OIDC metadata endpoint
- Set the allowed audiences to match the application ID from the Microsoft Entra ID application registration
- Built-in integration eliminates the need for additional infrastructure or custom code
- Provides direct OIDC authentication with minimal operational overhead

**Reference:** https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/inbound-jwt-authorizer.html

---

## AgentCore Starter Toolkit

- Provides automated packaging, containerization, and deployment workflows
- Automatically generates container images based on provided Dockerfiles
- Handles ARM64 container builds and manages ECR repository creation and image pushing
- Deploys agents using the `CreateAgentRuntime` operation
- Designed for users who want to focus on agent logic rather than infrastructure management

**Reference:** https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/runtime-get-started-toolkit.html

---

## AgentCore SDK — `@app.entrypoint` Decorator

- Automatically creates an HTTP server on port 8080
- Implements the required `/invocations` and `/ping` endpoints
- Handles proper content types and response formats
- Supports both JSON responses (quick lookups) and streaming responses (long-running report generation)
- Does not require manual server configuration or endpoint management

**Reference:** https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/runtime-how-it-works.html
