FROM node:alpine as builder
RUN mkdir -p /var/www/html

WORKDIR /var/www/html

COPY client/package.json /var/www/html/

RUN npm install

COPY client /var/www/html/

RUN ls /var/www/html/
RUN ls /var/www/html/client
RUN ls /var/www/html/client/public


RUN npm run build

FROM nginx
EXPOSE 3000
COPY client/nginx/default.conf /etc/nginx/conf.d/default.conf

COPY --from=builder /var/www/html /etc/nginx/html
