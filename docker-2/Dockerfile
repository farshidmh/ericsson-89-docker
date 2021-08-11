FROM ubuntu

ENV TZ=Europe/London
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update -y
RUN apt-get install -y curl apache2 php libapache2-mod-php php-mysql
RUN rm -rf /var/www/html/*

COPY /src/ /var/www/html/

ENV APACHE_RUN_DIR /var/www/html
ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2

EXPOSE 80

CMD ["/usr/sbin/apache2","-D","FOREGROUND"]