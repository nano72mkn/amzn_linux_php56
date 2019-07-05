ARG AMZN_LINUX_VER

FROM amazonlinux:${AMZN_LINUX_VER}

# 時計の調整
# RUN cp -p /usr/share/zoneinfo/Japan /etc/localtime
# RUN ntpdate ntp.nict.jp
# RUN chkconfig ntpd on

USER root

# yum update
RUN yum -y update
RUN yum clean all

# Development Tools install
RUN yum -y groupinstall "Development Tools"

# phpのタイムゾーン設定
#RUN "date.timezone=Asia/Tokyo" > /etc/php.ini

WORKDIR /var/www
