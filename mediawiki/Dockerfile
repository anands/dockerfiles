FROM ubuntu:16.04
ENV DEBIAN_FRONTEND noninteractive
RUN \
	apt-get update && \
	apt-get -y install wget curl vim net-tools supervisor apache2 php7.0 libapache2-mod-php7.0 php7.0-mbstring php7.0-xml php7.0-mysql mysql-server-5.7 && \
	service mysql start && \
	mysqladmin -u root password mediawiki && \
	cd /var/www/html && \
	rm index.html && \
	wget https://releases.wikimedia.org/mediawiki/1.28/mediawiki-1.28.0.tar.gz && \
	tar -zxf mediawiki-1.28.0.tar.gz -C . --strip-components=1 && \
	rm mediawiki-1.28.0.tar.gz

ADD start-apache2.sh /start-apache2.sh
ADD start-mysqld.sh /start-mysqld.sh
ADD run.sh /run.sh
RUN chmod 755 /*.sh

ADD supervisord-apache2.conf /etc/supervisor/conf.d/supervisord-apache2.conf
ADD supervisord-mysqld.conf /etc/supervisor/conf.d/supervisord-mysqld.conf

EXPOSE 80

CMD ["/run.sh"]