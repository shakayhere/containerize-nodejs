# First stage: Build the Node.js application
FROM node:14-alpine AS build

# Set the working directory to /app
WORKDIR /app

# Copy package.json and package-lock.json to the container
COPY package*.json ./

# Install Node.js dependencies
RUN npm install --production

# Second stage: Run the Node.js application
FROM node:14-alpine

# Set the working directory to /app
WORKDIR /app

# Copy only the necessary files from the build stage
COPY --from=build /app/node_modules ./node_modules
COPY --from=build /app/package*.json ./

# Copy the rest of the application code to the container
COPY . .

# Use a non-root user to run the Node.js application
USER node

# Set the NODE_ENV environment variable to production
ENV NODE_ENV=production

# Expose port 3000 for the Node.js application
EXPOSE 3000

# Define a health check for the container
HEALTHCHECK --interval=30s --timeout=10s --start-period=5s --retries=3 \
  CMD curl -f http://localhost:3000/ || exit 1

# Start the Node.js application
CMD [ "npm", "start" ]
