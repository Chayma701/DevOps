# Use the official Node.js base image
FROM node:20.10.0-alpine

# Set the working directory to /app
WORKDIR /app

# Copy package.json and package-lock.json to leverage Docker cache
COPY package*.json ./

# Install Angular CLI globally
RUN npm install -g @angular/cli

# Install app dependencies
RUN npm install

# Copy the entire Angular project to the Docker image
COPY . .

# Expose the default Angular port
EXPOSE 4200

# Run ng serve in development mode
CMD ["ng", "serve", "--host", "0.0.0.0"]
