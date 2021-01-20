FROM centos:7
MAINTAINER ravikishore<ravikishorefst@gmail.com>
WORKDIR /root

RUN yum -y install mariadb-server mariadb &&\
    mysql_install_db --user=mysql --ldata=/var/lib/mysql

CMD /usr/bin/mysqld_safe --datadir='/var/lib/mysql'

EXPOSE 3306
