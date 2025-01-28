# Use Node.js as the base image
FROM node:alpine

# Set the working directory
WORKDIR /usr/server

# Copy package.json and install dependencies
COPY ./ ./

RUN npm install

# Expose the backend port
EXPOSE 5000

# Start the server
CMD ["npm", "start"]
