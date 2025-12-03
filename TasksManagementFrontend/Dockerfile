# Stage 1: Build the React app
FROM node:16 AS build

WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy all source files
COPY . .

ENV REACT_APP_BACKEND_URL=http://localhost:8080

# Build the app for production
RUN npm run build

# Stage 2: Serve the built static files
FROM node:16-alpine

# Install serve to host static files
RUN npm install -g serve

WORKDIR /app

# Copy build output from previous stage
COPY --from=build /app/build ./build

# Expose port 5000
EXPOSE 5000

# Serve the static files
CMD ["serve", "-s", "-l", "5000", "build"]

