FROM node:18-alpine

WORKDIR /app

# Copy package files first for better caching
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application
COPY . .

# Build the Svelte documentation site - this is a Node.js MCP server for Svelte docs
RUN npm run build

# Expose the port for the MCP server
EXPOSE 3000

# Start the MCP server
CMD ["npm", "start"]
