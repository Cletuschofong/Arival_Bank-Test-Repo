# Arival_Bank-Test-Repo
Dockerfile for a Node.js application
This Dockerfile creates a two-stage build for a Node.js application.

Stage 1: Build the application
In this stage, the Dockerfile starts with an node:14-alpine image, sets the working directory to /usr/src/app, and copies the package.json and package-lock.json files to the working directory. It then runs npm install to install production dependencies. Finally, it copies the application code to the working directory and runs npm run build to create a production build.

Stage 2: Create the final image
In this stage, the Dockerfile starts with another node:14-alpine image, sets the working directory to /usr/src/app, and copies the package.json and package-lock.json files to the working directory. It then runs npm install to install production dependencies. Finally, it copies the build output from the previous stage (/usr/src/app/build) to the working directory.

The EXPOSE command exposes port 5000, which is the port that the application listens on.

The CMD command runs npm start, which starts the application.

Building the image
 #Run the following command, to build the Docker image:
docker build -t <image-name> .
