# --- Builder/test stage ---
FROM node:20 AS builder
WORKDIR /app

# installera beroenden
COPY package*.json ./
RUN npm ci

# kopiera in resten av koden
COPY . .

# kör tester under build
RUN npm test

# --- Runtime stage ---
FROM node:20-slim AS runtime
WORKDIR /app

# kopiera bara det vi behöver från builder
COPY --from=builder /app ./

# startkommandot
CMD ["npm", "start"]
