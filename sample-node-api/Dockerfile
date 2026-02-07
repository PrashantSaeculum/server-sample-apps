# Use an official Node.js runtime as a parent image
FROM node:22-alpine

# Set the working directory in the container
WORKDIR /

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Express server port
ENV PORT=3000

# DB connection url
ENV PRIMARY_DB_URL='mongodb://root:CIqrnarFGsRbIZ5k@143.198.130.213:27017/?directConnection=true&serverSelectionTimeoutMS=2000&authSource=admin&appName=mongosh+2.6.0'

# Caching redis
ENV REDIS_HOST='143.198.130.213'
ENV REDIS_PORT='6379'
ENV REDIS_USERNAME='default'
ENV REDIS_PASSWORD='pj7ZdweGZFGuhRZR'

# Third-party
ENV MSMQ_ENABLE=true
ENV MSMQ_PROTOCOL='amqp'
ENV MSMQ_HOST='143.198.130.213'
ENV MSMQ_PORT=5672
ENV MSMQ_USERNAME='admin'
ENV MSMQ_PASSWORD='1kRB8Dnrs4Cj8JN9'
ENV MSMQ_QUEUE=task_queue

# Copy the rest of the application code to the working directory
COPY . .

# Expose the application port
EXPOSE 3000

# Define the command to run the application
CMD ["npm", "start"]
