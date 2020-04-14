FROM jenkins/jenkins:lts

USER root

RUN install-plugins.sh antisamy-markup-formatter matrix-auth pipeline-model-definition blueocean

RUN echo "deb http://repos.zend.com/zend-server/2019.0/deb_debian9 server non-free" > /etc/apt/sources.list.d/zend.list && \
	wget http://repos.zend.com/zend.key -O- |apt-key add - && \
	apt-get update && \
    apt-get install -y zend-server-apache-fpm && \
    update-alternatives --install /usr/bin/php php /usr/local/zend/bin/php 1
    
USER jenkins