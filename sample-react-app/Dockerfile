# Build stage
FROM node:latest AS build

WORKDIR /app

# Copy package files and npmrc
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy source code
COPY . .

# Set environment variables
ENV VITE_API_URL=http://143.198.130.213:3000

RUN npm install -g serve

# Build the application
RUN npm run build

# Expose port 80
EXPOSE 5173

# Start Nginx
CMD ["serve", "-s", "build", "-l", "5173"]