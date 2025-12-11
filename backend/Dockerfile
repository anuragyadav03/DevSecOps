# ============================
# Stage 1: Builder
# ============================
FROM node:21 AS backend-builder

WORKDIR /app

# Copy backend code
COPY . .

# Install dependencies
RUN npm install

# ============================
# Stage 2: Production Image
# ============================
FROM node:21-slim

WORKDIR /app

# Copy built app from previous stage
COPY --from=backend-builder /app .

# Expose backend port
EXPOSE 5000

# Start application
CMD ["npm", "start"]
