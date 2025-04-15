# Use Node.js LTS as the base image
FROM node:20-slim

# Set working directory
WORKDIR /app

# Clone the repository
RUN apt-get update && apt-get install -y git && \
    git clone https://github.com/spences10/mcp-svelte-docs.git . && \
    apt-get purge -y git && apt-get autoremove -y && rm -rf /var/lib/apt/lists/*

# Install dependencies
RUN npm ci

# Build the project
RUN npm run build

# Expose the default MCP server port
EXPOSE 3010

# Set environment variables (these can be overridden at runtime)
ENV DEBUG=false

# Run the MCP server
CMD ["node", "dist/index.js"]
