# Use an official Node image
FROM node:14-alpine

WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the source code
COPY . .

# Expose the backend port (e.g., 5000)
EXPOSE 5000

# Start the backend (adjust the command if necessary)
CMD ["npm", "run", "dev"]
