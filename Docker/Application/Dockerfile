FROM centos:7
MAINTAINER ravikishore <ravikishorefst@gmail.com>
WORKDIR /root
ENV WIKI_VERSION=1.35.0
ENV WIKI_EXACT_VERSION=1.35
RUN yum -y install http://rpms.remirepo.net/enterprise/remi-release-7.rpm &&\
    yum -y install epel-release && \
    yum-config-manager --disable remi-php54 && \
    yum-config-manager --enable remi-php73 && \
    yum -y install httpd && \
    yum -y install php php-mysql php-pdo php-gd php-mbstring php-xml php-intl texlive && \
    yum -y install wget

RUN wget https://releases.wikimedia.org/mediawiki/$WIKI_EXACT_VERSION/mediawiki-$WIKI_VERSION.tar.gz && \
    tar -xf mediawiki-$WIKI_VERSION.tar.gz && \
    mv mediawiki-$WIKI_VERSION/* /var/www/html/ && \
    rm mediawiki-$WIKI_VERSION.tar.gz

CMD /usr/sbin/apachectl -DFOREGROUND
EXPOSE 80
