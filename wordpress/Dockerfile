FROM centos:centos7

LABEL maintainer="LI JHIH-SIOU"

ENV TZ=UTC

# Upgrade the system
RUN yum -y update && yum -y upgrade

# Install httpd web server & PHP dependencies & other utilities
RUN yum -y install                                                              \
        httpd                                                                   \
        php php-fpm php-mysql php-gd php-xml php-curl php-opcache php-mbstring  \
        wget

# # Copy the predownloaded Wordpress 6.2.3 to /var/www/html
# COPY . /var/www/html/

# Expose port
EXPOSE 80

# Entrypoint
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
