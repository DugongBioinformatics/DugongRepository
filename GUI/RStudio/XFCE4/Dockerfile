FROM dugong/dugong
MAINTAINER Fabiano Menegidio

USER root

RUN wget https://download1.rstudio.org/rstudio-1.0.143-amd64.deb \
    && gdebi -n rstudio-1.0.143-amd64.deb \
    && rm rstudio-1.0.143-amd64.deb

USER dugong

RUN /headless/.conda2/bin/conda install -c r r-essentials \
    && /headless/.conda2/bin/conda clean -tipsy
