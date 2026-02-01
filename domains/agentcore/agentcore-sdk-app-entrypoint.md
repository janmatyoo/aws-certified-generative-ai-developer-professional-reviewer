AgentCore SDK with the @app.entrypoint decorator
- provides minimal operational overhead
- automatically creates an HTTP server on port 8080 and implements the required /invocations and /ping endpoints
- handles proper content types and response formats
- supports both JSON responses for quick lookups and streaming responses for long-running report generation
- does not require manual server configuration or endpoint management.

