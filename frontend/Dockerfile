# Step 1: Build the app using Node.js
FROM node:22 AS build

# Set the working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package*.json ./


# Copy the rest of your front-end files
COPY . .

# Build the React app
RUN npm i && npm run build

# Serve the static files using Nginx
FROM nginx:alpine

# Set the working directory
WORKDIR /usr/share/nginx/html

# Remove the default Nginx configuration
RUN rm -rf ./*

# Copy build folder to Nginx's public directory
COPY --from=build /app/build .


# Run Nginx
ENTRYPOINT  ["nginx", "-g", "daemon off;"]

