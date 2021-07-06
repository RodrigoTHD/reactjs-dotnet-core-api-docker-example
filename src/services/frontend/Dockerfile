# Multi-stage
# Stage 1: based on Node.js, to build and compile the frontend.
FROM node:16.3.0-alpine3.11 as build
ARG GENERATE_SOURCEMAP
WORKDIR /app
COPY . .
RUN yarn
RUN yarn build

# Stage 2: based on Nginx, to have only the compiled app, ready for production with Nginx.
FROM nginx:stable-alpine
WORKDIR /usr/share/nginx/html
RUN rm -rf ./*
COPY --from=build /app/build .
COPY --from=build /app/nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]