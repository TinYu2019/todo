# ==== CONFIGURE =====
# Use a Node 18 base image
FROM node:18-slim

# Set the working directory to /app inside the container
WORKDIR /app

# Copy frontend app files
COPY . .

# ==== BUILD =====
# Install dependencies (npm ci makes sure the exact versions in the lockfile gets installed)
RUN npm ci 

# Build the app
RUN npm run build

# ==== RUN =======
# Set the env to "development"
ENV NODE_ENV development

# Expose the port on which the app will be running (3000 is the default that `server` uses)
EXPOSE 3000

# Start the app
CMD [ "npx", "serve", "build" ]