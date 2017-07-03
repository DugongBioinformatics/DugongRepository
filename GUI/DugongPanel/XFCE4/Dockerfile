FROM dugong/dugong
MAINTAINER Fabiano Menegidio

USER root
ENV USER dugong
USER dugong

ADD .config/GUI/xfce/ $HOME/

RUN /headless/.conda2/bin/conda create -n panel anaconda-navigator=1.5
