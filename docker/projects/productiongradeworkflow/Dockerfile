# Build phase
FROM node:alpine as builder
WORKDIR '/app'
COPY package.json .
RUN npm install
COPY . . 
RUN npm run build

# Run phase
FROM nginx

# For Elasticbeanstalk: "-p 8080:80" alternative
EXPOSE 80 

COPY --from=builder /app/build /usr/share/nginx/html

# docker build .
# docker run -p 8080:80 <container_id>