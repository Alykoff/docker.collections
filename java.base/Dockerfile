# Use phusion/baseimage as base image. To make your builds
# reproducible, make sure you lock down to a specific version, not
# to `latest`! See
# https://github.com/phusion/baseimage-docker/blob/master/Changelog.md
# for a list of version numbers.

# We use https://github.com/jwerle/mush/blob/master/mush.sh for config files templating
FROM phusion/baseimage:latest
MAINTAINER Gali Alykov <galll-al@yandex.kz>

# Use baseimage-docker's init system.
CMD ["/sbin/my_init"]

RUN echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \ 
    add-apt-repository -y ppa:webupd8team/java && \
    apt-get update && \
    apt-get install -y oracle-java8-installer && \
    apt-get clean && \
    rm -rf /var/lib/{apt,dpkg,cache,log}/* /tmp/* /var/tmp/* && \
    rm -rf /var/cache/oracle-jdk8-installer

ENV JAVA_HOME /usr/lib/jvm/java-8-oracle
