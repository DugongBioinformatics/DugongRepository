FROM dugong/dugong:icewm
MAINTAINER Fabiano Menegidio

USER root
ENV USER dugong
USER dugong

ADD .config/GUI/icewm/ $HOME/

RUN /headless/.conda2/bin/conda create -n panel anaconda-navigator=1.5
