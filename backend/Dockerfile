# Build stage
FROM node:20-alpine AS builder

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build


# Production
FROM node:20-alpine

WORKDIR /app
COPY --from=builder --chown=node:node /app /app
USER node

EXPOSE 5000
CMD ["npm", "start"]
