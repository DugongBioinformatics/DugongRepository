FROM dugong/dugong:icewm
MAINTAINER Fabiano Menegidio

USER root
RUN apt-get update \
    && apt-get autoremove -y && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

USER dugong
