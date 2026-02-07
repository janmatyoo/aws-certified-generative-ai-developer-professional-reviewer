Model Context Protocol (MCP) 
- designed to provide a consistent interface for AI models and agents to interact with external tools and APIs
- The MCP server provides function schemas that define a standardized way to interact with the CMS
- The implementation of the functions handles the API **inconsistencies** internally.
- This solution abstracts the complexities of the underlying CMS API from the agents
- This solution provides a clean, consistent interface
- This solution is reusable across different agent workflows
- The workflows can all interact with the CMS through the same MCP functions
- This solution reduces integration complexity and operational overhead
- You can update API changes or new edge cases in one central location rather than in each individual agent


https://aws.amazon.com/blogs/devops/extend-the-amazon-q-developer-cli-with-mcp/
https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/qdev-mcp-overview.html
