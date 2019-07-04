FROM amazonlinux:2018.03.0.20190212
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

# PHP56
RUN yum -y install \
    php56 \
    php56-devel \
    php56-mysqlnd \
    php56-mbstring \
    php56-gd

# phpのタイムゾーン設定
#RUN "date.timezone=Asia/Tokyo" > /etc/php.ini

# mysql56
RUN yum -y install mysql56 mysql56-server

# mysqlの設定を追加
RUN echo "\n[mysqld]\ncharacter_set_server=utf8\ndefault-storage-engine=InnoDB\ninnodb_file_per_table\n\n[mysql]\ndefault-character-set=utf8\n\n[mysqldump]\ndefault-character-set=utf8" >> /etc/my.cnf
