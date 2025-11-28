# backend/Dockerfile
FROM node:18-alpine

# Set working directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the source code
COPY . .

# Set environment variable for production
ENV NODE_ENV=production

# Expose the backend port
EXPOSE 8080

# Start the server
CMD ["node", "server.js"]
