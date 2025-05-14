# Input requirements
**Name:** Name must have only english letters, digits or underscores. It must not start with digits.

**Description:** Any string. Supports Markdown.

**Logo:** Upload an image.

**Command:** Optional start command of your application. This field can be left out if your Dockerfile has the necessary command inside of it.
_Example: `node dist/index.js`_
_**Note:** In case you use `stdio` transport and your docker container has NodeJS you can use the following command:
`npx -y supergateway --stdio '"YOUR START COMMAND"' --port 80 --baseUrl http://localhost:80 --ssePath /sse`_

**Repository URL:** Valid https git repository URL. Repository must satisfy the following requirements:
- Have a Dockerfile in root folder
- Use SSE transport
- Listen on port 80 on `/sse`
