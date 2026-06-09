FROM node:24-alpine AS builder

ENV NODE_ENV=production

WORKDIR /app

COPY package*.json ./

RUN npm ci --only=production

COPY . . 

EXPOSE 3500

cmd ["node","index.js"]
