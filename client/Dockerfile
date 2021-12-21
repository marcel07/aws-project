FROM node:alpine as builder
RUN mkdir -p /var/www/html
RUN mkdir -p /dist

WORKDIR /var/www/html

EXPOSE 3000

COPY . /var/www/html/

RUN ls .


#RUN npm install

#COPY . .

#RUN npm run build


CMD ["npm", "run", "start"]

#FROM nginx
#EXPOSE 3000
#COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
#COPY --from=builder ./public /usr/local/bin/nginx/html
