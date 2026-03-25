FROM node:18-bullseye-slim

WORKDIR /app

# Update system packages to fix vulnerabilities
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y --only-upgrade libdb5.3 zlib1g && \
    rm -rf /var/lib/apt/lists/*

COPY package*.json ./
RUN npm install

COPY . .
CMD ["npm", "start"]