# Stage 1: Build the application with Node.js
FROM node:14.15.0-alpine as builder 
WORKDIR /app 
COPY . .  
RUN npm install  
RUN npm run build  

# Stage 2: Create the final image with Nginx
FROM nginx:alpine 
COPY --from=builder /app/dist/smart-home /usr/share/nginx/html