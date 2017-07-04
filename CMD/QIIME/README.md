# Dugong - Qiime

***QIIME*** is an open-source bioinformatics pipeline for performing microbiome analysis from raw DNA sequencing data. QIIME is designed to take users from raw sequencing data generated on the Illumina or other platforms through publication quality graphics and statistics. This includes demultiplexing and quality filtering, OTU picking, taxonomic assignment, and phylogenetic reconstruction, and diversity analyses and visualizations.

***Additional software:*** PANDASeq

## Install Docker

### Ubuntu:

1. Set up the repository

Set up the Docker CE repository on Ubuntu. The lsb_release -cs sub-command prints the name of your Ubuntu version, like xenial or trusty.

    $ sudo apt-get -y install \
        apt-transport-https \
        ca-certificates \
        curl

    $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

    $ sudo add-apt-repository \
        "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
        $(lsb_release -cs) \
        stable"

    $ sudo apt-get update

2. Get Docker CE

Install the latest version of Docker CE on Ubuntu:

    $ sudo apt-get -y install docker-ce

3. Test your Docker CE installation

Test your installation:

    $ sudo docker run hello-world


### Fedora

1. Set up the repository

Set up the Docker CE repository on Fedora:

    $ sudo dnf -y install dnf-plugins-core

    $ sudo dnf config-manager \
        --add-repo \
        https://download.docker.com/linux/fedora/docker-ce.repo

    $ sudo dnf makecache fast
    
2. Get Docker CE

Install the latest version of Docker CE on Fedora:

    $ sudo dnf -y install docker-ce

Start Docker:

    $ sudo systemctl start docker

or

    $ sudo service docker start

3. Test your Docker CE installation

Test your installation:

    $ sudo docker run hello-world

### Windows:

Access: https://store.docker.com/editions/community/docker-ce-desktop-windows

### MacOS:

Access: https://store.docker.com/editions/community/docker-ce-desktop-mac
