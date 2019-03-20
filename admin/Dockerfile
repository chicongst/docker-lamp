FROM amazonlinux:1
MAINTAINER Chicongst <chicongst9x@gmail.com>

RUN yum clean all
RUN yum -y update

RUN yum install -y php71 php71-cli php71-common php71-json php71-mbstring php71-mysqlnd php71-pdo php71-process php71-xml httpd24 httpd24-tools openssl zip unzip php71-zip git

RUN yum install -y nano
RUN yum install -y vim

# Install Composer
RUN  curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer

# Install nodejs
RUN yum -y update
RUN yum install -y gcc gcc-c++ make openssl-devel

RUN curl --silent --location https://rpm.nodesource.com/setup_8.x | bash -
RUN yum -y install nodejs


# Clear yum cache
RUN yum clean all

RUN mkdir -p /var/www/html/cc_admin
RUN chmod -R 755 /var/www/html/cc_admin

# config virtual host
ADD cc-test.conf /etc/httpd/conf.d
# workspace
WORKDIR /var/www/html/cc_admin/
# for web
EXPOSE 80
EXPOSE 443

CMD /usr/sbin/httpd -DFOREGROUND
