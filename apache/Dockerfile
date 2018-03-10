FROM centos:7

MAINTAINER Eswarmoorthi Duraisamy <eswar2k11@gmail.com>

#
# Import the Centos-6 RPM GPG key to prevent warnings and Add EPEL Repository
#
#
RUN rpm --import http://mirror.centos.org/centos/RPM-GPG-KEY-CentOS-7 \
    && rpm --import http://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-7 \
    && yum -y install epel-release.noarch


RUN yum -y install \
    httpd \
    mysql-devel \
    mysql-libs \
    mod_ssl \
    php \
    php-cli \
    php-imap \
    php-ldap \
    php-mbstring \
    php-mcrypt \
    php-mysql \
    php-pear-MDB2-Driver-mysqli \
    php-pecl-memcached \
    php-tidy \
    php-xml \
    php-gd \
    msmtp \
    && yum -y update bash \
    && rm -rf /var/cache/yum/* \
    && yum clean all

RUN echo '<?php phpinfo(); ?>' > /var/www/html/index.php

EXPOSE 80 443

ENTRYPOINT /usr/sbin/httpd -c "ErrorLog /dev/stdout" -DFOREGROUND
