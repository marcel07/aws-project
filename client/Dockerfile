FROM node:alpine as builder
RUN mkdir -p /var/www/html

WORKDIR /var/www/html

EXPOSE 3000

COPY package.json .

RUN npm run build

COPY . .

CMD ["npm", "run", "start"]

#FROM nginx
#EXPOSE 3000
#COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
#COPY --from=builder ./public /usr/local/bin/nginx/html
