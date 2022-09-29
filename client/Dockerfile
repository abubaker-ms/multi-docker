#This docker file creates prodution server
FROM node:16-alpine as builder

WORKDIR '/app'
COPY package.json .
RUN npm install 
COPY . . 
RUN npm run build
#nginx behaves as production server
FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build/ /usr/share/nginx/html