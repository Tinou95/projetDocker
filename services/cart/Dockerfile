# Service Cart Dockerfile (services/cart/Dockerfile)
FROM node:18-slim AS development
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3003
USER node
CMD ["npm", "run", "dev"]

FROM node:18-slim AS production
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
EXPOSE 3003
USER node
CMD ["npm", "start"]