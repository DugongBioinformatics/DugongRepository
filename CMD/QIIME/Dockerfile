FROM dugong/dugong:cmd
MAINTAINER Fabiano Menegidio <fabiano.menegidio@biology.bio.br>

USER root

RUN apt-get update && apt-get -y install \
      ant gfortran ghc libatlas-base-dev libatlas-dev libbz2-dev libc6-i386 libfreetype6-dev libgsl0-dev libhdf5-serial-dev \
      liblapack-dev libmysqlclient20 libmysqlclient-dev libncurses5-dev libpng12-dev libreadline-dev libsqlite3-dev \
      libssl-dev libxml2 libxslt1.1 libxslt1-dev libzmq-dev mpich pkg-config sqlite3 subversion swig tcl-dev tk-dev \
      zlib1g-dev apt-transport-https \
    && apt-get autoremove -y && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*


USER dugong

RUN /headless/.conda2/bin/conda install qiime qiime-default-reference r-qiimer qiimetomaaslin pandaseq vsearch matplotlib mock nose h5py \
    bioconductor-metagenomeseq bioconductor-deseq2
      
      
USER root

# Use qiime-deploy to install all other dependencies
RUN cd $HOME && mkdir tmp && cd tmp && git clone https://github.com/fabianomenegidio/qiime_deps \
    && cd qiime_deps &&  cat qiime_deps.tar.gz.part-* > qiime_deps.tar \
    && tar xvf qiime_deps.tar && mv qiime_deps /opt && rm -rf $HOME/tmp && chown -R dugong:dugong /opt/qiime_deps \
    && mkdir /opt/qiime_db && wget cd /opt/qiime_db /
    && wget https://unite.ut.ee/sh_files/sh_qiime_release_28.06.2017.zip \
    && wget ftp://greengenes.microbio.me/greengenes_release/gg_13_5/gg_13_8_otus.tar.gz \
    && unzip sh_qiime_release_28.06.2017.zip && tar zxvf gg_13_8_otus.tar.gz && chown -R dugong:dugong /opt/qiime_db \
    && rm sh_qiime_release_28.06.2017.zip gg_13_8_otus.tar.gz
    
ENV qiime_db /opt/qiime_db
ENV qiime_deps /opt/qiime_deps
      
USER dugong      
      
ENV PYTHONPATH /opt/qiime_deps/qiime-galaxy-0.0.1-repository-de3646d3/lib/:/opt/qiime_deps/tax2tree-1.0-release/lib/python2.7/site-packages:/opt/qiime_deps/pprospector-1.0.1-release/lib/python2.7/site-packages:$PYTHONPATH
ENV BLASTMAT /opt/qiime_deps/blast-2.2.22-release/data
ENV QIIME_CONFIG_FP /opt/qiime_deps/qiime_config
ENV PYRO_LOOKUP_FILE /opt/qiime_deps/ampliconnoise-1.27-release/Data/LookUp_E123.dat
ENV RDP_JAR_PATH /opt/qiime_deps/rdpclassifier-2.2-release/rdp_classifier-2.2.jar
ENV SEQ_LOOKUP_FILE /opt/qiime_deps/ampliconnoise-1.27-release/Data/Tran.dat
ENV PATH $CONDA2_DIR/bin:/opt/qiime_deps/infernal-1.0.2-release/bin:/opt/qiime_deps/vienna-1.8.4-release/:/opt/qiime_deps/ea-utils-1.1.2-537-release/:/opt/qiime_deps/cytoscape-2.7.0-release/:/opt/qiime_deps/cdhit-3.1-release/:/opt/qiime_deps/bwa-0.6.2-release/:/opt/qiime_deps/rdpclassifier-2.2-release/:/opt/qiime_deps/muscle-3.8.31-release/:/opt/qiime_deps/SeqPrep-v1.1-release/:/opt/qiime_deps/blast-2.2.22-release/bin:/opt/qiime_deps/ampliconnoise-1.27-release/Scripts:/opt/qiime_deps/ampliconnoise-1.27-release/bin:/opt/qiime_deps/qiime-galaxy-0.0.1-repository-de3646d3/scripts:/opt/qiime_deps/mothur-1.25.0-release/:/opt/qiime_deps/raxml-7.3.0-release/:/opt/qiime_deps/chimeraslayer-4.29.2010-release/ChimeraSlayer:/opt/qiime_deps/chimeraslayer-4.29.2010-release/NAST-iEr:/opt/qiime_deps/tax2tree-1.0-release/bin:/opt/qiime_deps/drisee-1.2-release/:/opt/qiime_deps/clearcut-1.0.9-release/:/opt/qiime_deps/cdbtools-10.11.2010-release/:/opt/qiime_deps/rtax-0.984-release/:/opt/qiime_deps/sourcetracker-1.0.0-release/:/opt/qiime_deps/pprospector-1.0.1-release/bin:/opt/qiime_deps/blat-34-release/:$PATH
ENV SOURCETRACKER_PATH /opt/qiime_deps/sourcetracker-1.0.0-release/
