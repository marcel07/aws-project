FROM node:alpine as builder
RUN mkdir -p /var/www/html
RUN mkdir -p /var/www/html/dist

WORKDIR /var/www/html

COPY client/package.json /var/www/html/

RUN npm install

COPY client /var/www/html/

RUN npm run build

RUN tree . -l 3

FROM nginx
EXPOSE 3000
COPY client/nginx/default.conf /etc/nginx/conf.d/default.conf

COPY --from=builder /var/www/html /etc/nginx/html

RUN tree . -l 3
