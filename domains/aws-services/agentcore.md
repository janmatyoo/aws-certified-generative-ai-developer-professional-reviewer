AgentCore Runtime with Strands Agent
- can be use to build AI agents with built-in MCP support
- a prebuilt MCP server can directly expose Aurora inventory and store data as MCP tools
    - this solution eliminates the need for custom containers or API management
    - this solution provides natural language access to data
    - this solution automates supply chain actions with the least operational overhead because Amazon Bedrock handles orchestration and hosting

https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/agents-tools-runtime.html

---

AgentCore Identity
- supports Microsoft Entra ID as an inbound IdP for OIDC authentication.
- for setup, you must configure the discovery URL to the Microsoft v2.0 OIDC metadata endpoint
- you set the allowed audiences to match the application ID from the Microsoft Entra ID application registration
- this built-in integration eliminates the need for additional infrastructure components or custom code
- this solution provides direct OIDC authentication with the least operational overhead

---

AgentCore starter toolkit
- provides automated packaging, containerization, and deployment workflows
- minimal operational overhead
- automatically generates container images based on provided Dockerfiles
- automatically handles ARM64 container builds and manages ECR repository creation and image pushing
- automatically deploys agents by using the CreateAgentRuntime operation
- designed for users that want to focus on agent logic rather than infrastructure management

---

AgentCore SDK with the @app.entrypoint decorator
- provides minimal operational overhead
- automatically creates an HTTP server on port 8080 and implements the required /invocations and /ping endpoints
- handles proper content types and response formats
- supports both JSON responses for quick lookups and streaming responses for long-running report generation
- does not require manual server configuration or endpoint management.


