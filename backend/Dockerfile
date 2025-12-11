# ============================
# Stage 1: Build & Test
# ============================
FROM node:21 AS backend-builder

# Set working directory
WORKDIR /app

# Copy everything
COPY . .

# Install dependencies
RUN npm install



# ============================
# Stage 2: Production Image
# ============================
FROM node:21-slim

# Set working directory
WORKDIR /app

# Copy only the built app from Stage 1
COPY --from=backend-builder /app .

# Copy environment file
COPY .env.docker .env

# Expose backend port
EXPOSE 5000

# Start the server
CMD ["npm", "start"]
