FROM node:18-alpine

# Declare the required environment variable
ENV SUPABASE_ACCESS_TOKEN=""

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

EXPOSE 3000

# Add environment variable check
CMD if [ -z "$SUPABASE_ACCESS_TOKEN" ]; then \
    echo "Error: SUPABASE_ACCESS_TOKEN environment variable is required" && exit 1; \
    fi && npm start