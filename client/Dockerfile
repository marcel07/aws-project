FROM node:alpine as builder
RUN mkdir -p /var/www/html
RUN mkdir -p /dist

WORKDIR /var/www/html

EXPOSE 3000

COPY client/package.json /var/www/html/

RUN ls .


RUN npm install

COPY client /var/www/html/

RUN npm run build

FROM nginx
EXPOSE 3000
COPY client/nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder ./public /etc/nginx/html
