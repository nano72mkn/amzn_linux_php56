ARG AMZN_LINUX_VER

FROM amazonlinux:${AMZN_LINUX_VER}
WORKDIR /projects

# 時計の調整
# RUN cp -p /usr/share/zoneinfo/Japan /etc/localtime
# RUN ntpdate ntp.nict.jp
# RUN chkconfig ntpd on

# yum update
RUN yum -y update
RUN yum clean all

# Development Tools install
RUN yum -y groupinstall "Development Tools"

# epel追加
# RUN amazon-linux-extras install -y epel

# PHP
ARG PHP_VER
RUN yum -y install \
    php${PHP_VER} \
    php${PHP_VER}-devel \
    php${PHP_VER}-mysqlnd \
    php${PHP_VER}-mbstring \
    php${PHP_VER}-gd

# phpのタイムゾーン設定
#RUN "date.timezone=Asia/Tokyo" > /etc/php.ini

# mysql
ARG MYSQL_VER
RUN yum -y install mysql${MYSQL_VER} mysql${MYSQL_VER}-server

# mysqlの設定を追加
RUN echo "\n[mysqld]\ncharacter_set_server=utf8\ndefault-storage-engine=InnoDB\ninnodb_file_per_table\n\n[mysql]\ndefault-character-set=utf8\n\n[mysqldump]\ndefault-character-set=utf8" >> /etc/my.cnf
