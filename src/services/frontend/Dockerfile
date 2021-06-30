# Multi-stage
# Stage 1: based on Node.js, to build and compile the frontend
FROM node:16.3.0-alpine3.11 as build-stage
WORKDIR /app
COPY package*.json /app/
RUN npm install
COPY ./ /app/
RUN npm run build

# Stage 2: based on Nginx, to have only the compiled app, ready for production with Nginx
FROM nginx:alpine
WORKDIR /usr/share/nginx/html
RUN rm -rf ./*
COPY --from=build-stage /app/build .

ENTRYPOINT ["nginx", "-g", "daemon off;"]

