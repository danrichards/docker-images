FROM ubuntu:20.04
# Install PHP tooling
RUN apt-get update \
    && apt-get install -y software-properties-common \
    && add-apt-repository -y ppa:ondrej/php \
    && apt-get update \
    && apt-get install -y \
		nano \
    	curl \
    	python3 \
    	python3-pip \
    	php8.1 \
    	php8.1-fpm \
    	php8.1-curl \
    	php8.1-mbstring \
    	php8.1-gd \
    	php8.1-imagick \
    	php8.1-xml \
    	php8.1-mysql \
    	php8.1-redis \
    	php8.1-memcached \
    	php8.1-mongodb \
		php8.1-zip
# Setup NodeJS
RUN apt-get update \
	&& apt-get install npm -y \
    && npm i -g n \
    && n 16
# Install supervisor
RUN pip3 install supervisor
# Install sudo
RUN apt-get install sudo
# Create new user `docker` and disable 
# password and gecos for later
# --gecos explained well here:
# https://askubuntu.com/a/1195288/635348
RUN adduser --disabled-password --gecos '' docker
#  Add new user docker to sudo group
RUN adduser docker sudo
# Ensure sudo group users are not 
# asked for a password when using 
# sudo command by ammending sudoers file
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers
# now we can set USER to the 
# user we just created
USER docker
# Run supervisor
CMD sudo supervisord && sudo tail -f /tmp/supervisord.log
