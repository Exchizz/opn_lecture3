FROM ubuntu
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install apache2 libapache2-mod-php7.2 php-mysql -y


COPY www/* /var/www/html/
EXPOSE 80
CMD /usr/sbin/apache2ctl -D FOREGROUND
