FROM node:16
WORKDIR /var/www/frontend

COPY ./package.json /var/www/frontend/.
COPY ./package-lock.json /var/www/frontend/.

RUN npm install

EXPOSE 5173
