# Use official Node.js 18 image as the base
FROM node:18

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json (or npm-shrinkwrap.json) to the working directory
COPY package*.json ./

# Install all dependencies (both production and development)
RUN npm install

# Copy the rest of the application files
COPY . .

# Build the application for production
RUN npm run build

# Expose the port your application will run on
EXPOSE 5302

# Set the necessary environment variables
ENV PORT=5302
ENV NODE_ENV=production
# Command to run your app in production
CMD ["node", ".output/server/index.mjs"]
