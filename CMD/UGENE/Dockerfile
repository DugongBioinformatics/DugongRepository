FROM dugong/dugong:cmd
MAINTAINER Fabiano Menegidio

################### Add repository UGENE
USER root

RUN echo "deb http://ppa.launchpad.net/iefremov/ppa/ubuntu natty main" >> /etc/apt/sources.list.d/ugene.list \
    && echo "deb-src http://ppa.launchpad.net/iefremov/ppa/ubuntu natty main" >> /etc/apt/sources.list.d/ugene.list \
    && apt-get update \
    && apt-get install -y libc6 libgcc1 libgl1-mesa-glx libqt4-network \
    libqt4-opengl libqt4-script libqt4-svg libqt4-xml libqtcore4 \
    libqtgui4 libqtwebkit4 libsqlite3-0 libstdc++6 libx11-6 zlib1g ugene \
    && apt-get autoremove -y && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

USER dugong
