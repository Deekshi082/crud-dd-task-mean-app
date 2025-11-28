# Stage 1: Build Angular
FROM node:18 AS build
WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy all source files
COPY . .

# Build Angular project using local Angular CLI
RUN npx ng build --configuration production

# Stage 2: Serve with Nginx
FROM nginx:alpine

# Copy built Angular app from Stage 1
COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html

# Copy custom Nginx config
COPY default.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
