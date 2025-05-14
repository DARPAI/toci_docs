# Deployment Process

To deploy your project you need to:

* create a github repo (or any other publically available git) with code of your MCP server
* create Dockefile that runs your MCP server
* fill in this form

After that the deployment will be added to the queue and started typically within a couple of minutes.

## Requirements

**Name:** only english letters, digits or underscores. It must not start with digits.

**Description:** Any string. Supports Markdown.

**Logo:** Upload an image.

**Repository URL:** Valid https git repository URL. Repository must satisfy the following requirements:
- Have a Dockerfile in root folder
- Use SSE transport
- Listen on port 80 on `/sse`

_**Note:** We recommend to use `CMD` instead of `ENTRY` to define main command of your MCP server, this way you can override it without modifying the sources_

**Command:** Optional. Command to overrids CMD of Dockerfile. This is always executed using shell.

_Example: `node dist/index.js`_

_**Note:** If you use `stdio` transport and your docker container has NodeJS you can convert it to SSE using the following command:
`npx -y supergateway --stdio '"YOUR CMD"' --port 80 --baseUrl http://localhost:80 --ssePath /sse`_
