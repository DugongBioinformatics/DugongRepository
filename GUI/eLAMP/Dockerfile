FROM dugong/dugong
MAINTAINER Fabiano Menegidio

USER root
RUN apt-get update \
    && apt-get install -y tre-agrep libtre5 libtre-dev  perl-tk \
    && apt-get autoremove -y && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

USER dugong
WORKDIR $HOME

RUN wget https://www.nybg.org/files/scientists/dlittle/eLAMP.tar.gz \
    && tar -zxvf eLAMP.tar.gz
