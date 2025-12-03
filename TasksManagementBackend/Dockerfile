FROM node:16

WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy all source files
COPY . .

# Expose port 8080
EXPOSE 8080

# Command to run the backend server
CMD ["npm", "start"]

