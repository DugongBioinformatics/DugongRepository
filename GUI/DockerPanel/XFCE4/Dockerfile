FROM dugong/dugong
MAINTAINER Fabiano Menegidio

RUN ~/.conda2/bin/conda config --system --prepend channels conda-forge \
    && ~/.conda2/bin/conda config --system --set auto_update_conda false \
    && ~/.conda2/bin/conda config --system --set show_channel_urls true \
    && ~/.conda2/bin/conda update --all \
    && ~/.conda2/bin/conda install --quiet --yes \
    'anaconda-navigator' \
    && ~/.conda2/bin/conda clean -tipsy
