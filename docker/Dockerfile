FROM centos:centos7

LABEL maintainer="LI JHIH-SIOU"

ENV TZ=UTC

# Upgrade the system
RUN yum -y update && yum upgrade

# Install httpd web server & PHP dependencies & other utilities
RUN yum -y install                                                              \
        httpd                                                                   \
        php php-fpm php-mysql php-gd php-xml php-curl php-opcache php-mbstring  \
        wget

# Download and extract wordpress to the designated directory
RUN wget "https://wordpress.org/wordpress-6.2.3.tar.gz" -O /tmp/latest.tar.gz        
RUN tar -zxvf /tmp/latest.tar.gz                                             

RUN cp -R /tmp/wordpress/* /var/www/html/

# Expose port
EXPOSE 80

# Entrypoint
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
