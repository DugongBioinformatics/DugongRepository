
###########################################################################
# Dugong - Scientific Linux Containers for Bioinformatic
# ======================================================
#
# Current development is led by Fabiano Menegidio.
#
# Bioinformatician/Bioinformaticist at the Laboratory of Functional 
# and Structural Genomics of the Integrated Nucleus of Biotechnology 
# at the University of Mogi das Cruzes, Brazil.
# 
# Contact: fabiano.menegidio@biology.bio.br
# GitHub: https://github.com/fabianomenegidio
#
#
###########################################################################
FROM dugong/dugong:xfce
MAINTAINER Fabiano Menegidio

USER root

################### Install geWorkbench
ADD geWorkbench_2.6.0 /root/geWorkbench_2.6.0
ADD geWorkbench_2.6.0 /headless/geWorkbench_2.6.0 
RUN chown -R dugong:dugong /headless/geWorkbench_2.6.0

WORKDIR /headless/geWorkbench_2.6.0
USER dugong
