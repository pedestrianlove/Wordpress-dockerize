FROM --platform=linux/amd64 centos:centos7

LABEL maintainer="LI JHIH-SIOU"

ENV TZ=UTC+8

# Upgrade the system
RUN yum -y update                                                                                       \
        && yum -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm        \
        && yum -y install http://rpms.remirepo.net/enterprise/remi-release-7.rpm                        \
        && yum -y install yum-utils && yum-config-manager --enable remi-php74                           

# Install httpd web server & PHP dependencies & other utilities
RUN yum -y install                                                                                      \
        httpd                                                                                           \
        php php-cli php-mysql php-gd php-xml php-curl php-zip php-mbstring php-magick php-xml           \
        wget

# # Copy the predownloaded Wordpress 6.2.3 to /var/www/html
# COPY . /var/www/html/

# Expose port
EXPOSE 80

# Entrypoint
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
