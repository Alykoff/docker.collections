# Use phusion/baseimage as base image. To make your builds
# reproducible, make sure you lock down to a specific version, not
# to `latest`! See
# https://github.com/phusion/baseimage-docker/blob/master/Changelog.md
# for a list of version numbers.

# We use https://github.com/jwerle/mush/blob/master/mush.sh for config files templating
FROM phusion/baseimage:latest
MAINTAINER Gali Alykov <galll-al@yandex.kz>

ENV CONSUL_VERSION 0.5.2

# Use baseimage-docker's init system.
CMD ["/sbin/my_init"]

RUN mkdir -p /usr/local/bin && \
    wget https://dl.bintray.com/mitchellh/consul/${CONSUL_VERSION}_linux_amd64.zip -P /usr/local/bin && \
    apt-get install unzip && \
    unzip /usr/local/bin/*.zip && \
    rm *.zip && \
    adduser consul && \
    mkdir -p /etc/consul.d/{bootstrap,server,client}
    mkdir -p /var/consul && \
    chown consul:consul /var/consul && \
    apt-get clean && \
    rm -rf /var/lib/{apt,dpkg,cache,log}/* /tmp/* /var/tmp/*

