# Containerized Node.js Application with Docker
This repository contains a sample Node.js application that has been containerized using Docker, following the best practices for containerization.

## Best Practices for Containerization
The following best practices have been implemented in this project:

- Use a minimal base image
- Use a multi stage dockerfile
- Use a .dockerignore file
- Set the NODE_ENV environment variable
- Use a non-root user
- Use a health check

## Project Structure
```
app/
  ├── package.json
  ├── index.js
  ├── docker-compose.yml
  ├── Dockerfile
  └── .dockerignore
```

The `index.js` file contains "Hello World" code in Node.js, including healthcheck.

The `Dockerfile` contains the instructions for building the Docker image for the application, following the best practices outlined above.

The `docker-compose.yml` file defines a single service for the application, with the necessary environment variables and port mappings.

## Usage
To build and run the containerized application, follow these steps:

1. Clone the repository to your local machine.
2. Navigate to the project directory.
3. Run `docker-compose up --build` to build the Docker image and start the container.
4. Access the application at `http://localhost:3000/`.

## Conclusion
By following the best practices for containerization and using Docker, we can create a portable, secure, and efficient container for our Node.js application.
