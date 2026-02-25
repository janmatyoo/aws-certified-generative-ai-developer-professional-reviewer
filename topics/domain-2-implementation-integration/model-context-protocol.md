# Model Context Protocol (MCP)

- Designed to provide a consistent interface for AI models and agents to interact with external tools and APIs
- The MCP server provides function schemas that define a standardized way to interact with a CMS
- Handles API inconsistencies internally
- Abstracts the complexities of the underlying CMS API from the agents
- Provides a clean, consistent interface that is reusable across different agent workflows
- All workflows interact with the CMS through the same MCP functions
- Reduces integration complexity and operational overhead
- API changes or new edge cases can be updated in one central location rather than in each individual agent

**References:**
- https://aws.amazon.com/blogs/devops/extend-the-amazon-q-developer-cli-with-mcp/
- https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/qdev-mcp-overview.html
