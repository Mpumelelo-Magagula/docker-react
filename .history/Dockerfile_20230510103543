#Install all the dependencies 
FROM node:alpine as builder 
WORKDIR '/app'
COPY package.json .
RUN npm install
COPY . .
RUN npm run build 

#Configuration for the run phase to start up the NGINX
FROM nginx 
#
COPY --from=builder /app/build /sur/share/nginx/html


