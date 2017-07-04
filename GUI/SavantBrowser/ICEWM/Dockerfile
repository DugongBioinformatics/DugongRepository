FROM dugong/dugong:icewm
MAINTAINER Fabiano Menegidio

USER root

RUN wget http://www.genomesavant.com/p/savant/dist/v2_0_5/savant-deb-2.0.5.deb \
    && gdebi -n savant-deb-2.0.5.deb \
    && rm savant-deb-2.0.5.deb

USER dugong
