FROM mysql:5.7.21
LABEL maintainer "OpenStandia"

# timezone
RUN cp -p /usr/share/zoneinfo/Japan /etc/localtime
# MySQL設定
COPY my-custom.cnf /etc/mysql/conf.d/


