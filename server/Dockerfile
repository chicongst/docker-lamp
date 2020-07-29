FROM amazonlinux:1
MAINTAINER Chicongst <chicong01100001@gmail.com>

ARG PHP_VERSION=73
ARG NODE_VERSION=10
ARG REPO_NAME=nkvd

RUN yum clean all
RUN yum -y update

RUN yum install -y php${PHP_VERSION} php${PHP_VERSION}-common php${PHP_VERSION}-mysql  php${PHP_VERSION}-pdo_mysql php${PHP_VERSION}-xml php${PHP_VERSION}-xmlrpc php${PHP_VERSION}-curl php${PHP_VERSION}-gd php${PHP_VERSION}-imagick php${PHP_VERSION}-cli php${PHP_VERSION}-dev php${PHP_VERSION}-imap php${PHP_VERSION}-mbstring php${PHP_VERSION}-opcache php${PHP_VERSION}-soap php${PHP_VERSION}-zip php${PHP_VERSION}-intl -y

RUN yum install -y nano
RUN yum install -y vim

# Install Composer
RUN  curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer

# Install Node
RUN yum -y update
RUN yum install -y gcc gcc-c++ make openssl-devel

RUN curl --silent --location https://rpm.nodesource.com/setup_${NODE_VERSION}.x | bash -
RUN yum -y install nodejs


# Clear yum cache
RUN yum clean all

RUN mkdir -p /var/www/${REPO_NAME}
RUN chmod -R 755 /var/www/${REPO_NAME}

# config virtual host
ADD laravel.conf /etc/httpd/conf.d
# workspace
WORKDIR /var/www/${REPO_NAME}
# for web
EXPOSE 80
EXPOSE 443

CMD /usr/sbin/httpd -DFOREGROUND
