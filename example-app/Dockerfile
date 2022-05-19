# STAGE 1: build
FROM node:18-alpine3.14 AS builder

WORKDIR /app

COPY . .

RUN npm install && npm run build

# STAGE 2: deploy
FROM nginx:1.21.6

COPY --from=builder /app/build/ /usr/share/nginx/html
COPY ./nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

ENTRYPOINT ["nginx", "-g", "daemon off;"]