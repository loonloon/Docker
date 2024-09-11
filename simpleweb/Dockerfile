# Use an official Node.js runtime as a base image, with Alpine Linux for a minimal footprint
FROM node:14-alpine

# Set the working directory inside the container
WORKDIR /usr/app

# Copy only the package.json file to the working directory
# This allows Docker to cache the npm install step if dependencies haven't changed
COPY ./package.json ./

# Install project dependencies from package.json
RUN npm install

# Copy the rest of the application files to the working directory
# This step occurs after npm install to leverage Docker's layer caching
COPY ./ ./

# Specify the default command to run the application
CMD ["npm", "start"]
