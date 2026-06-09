FROM node:26-alpine AS builder

# to fix the OpenSSL unsupported error
ENV NODE_OPTIONS=--openssl-legacy-provider

WORKDIR /app

COPY package*.json ./

RUN npm install


COPY . .

RUN npm run build


FROM nginx:alpine

COPY --from=builder /app/build /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

