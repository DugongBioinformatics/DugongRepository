FROM dugong/dugong
MAINTAINER Fabiano Menegidio

USER root
RUN apt-get update \
    && apt-get install -y fastqc \
    && apt-get autoremove -y && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

USER dugong
