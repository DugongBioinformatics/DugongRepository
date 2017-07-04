FROM dugong/dugong:icewm
MAINTAINER Fabiano Menegidio

USER root
ENV USER dugong
USER dugong

ADD .config/GUI/icewm/ $HOME/

RUN /headless/.conda2/bin/conda install anaconda-navigator=1.5
