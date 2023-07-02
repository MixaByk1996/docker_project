FROM nginx:1.23

ADD www.conf /etc/nginx/conf.d/www.conf

USER root

RUN apt-get update

WORKDIR /www/