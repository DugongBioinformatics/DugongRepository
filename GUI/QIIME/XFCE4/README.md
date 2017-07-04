# DugongCMD - Qiime

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

## Quick install Dugong:

To start a container, the user must have Docker installed on his operating system, according to the tutorials available in the project documentation. The Dugong image is available in the Docker Hub and its use is the recommended method of installation.

Two steps are required to start a container containing Dugong. In the first step, the Dugong image is downloaded from the Docker Hub servers to the host, and in the second, a container is created on the host machine with the default Dugong installation. If the host machine is a Linux, the following commands must be performed in the terminal:

    $ docker pull dugong/dugongcmd-qiime
    $ docker run -d -p 3000:3000 -p 2222:22 -v $HOME/dugong/:/data/ \
        --name DugongCMD -h DugongCMD --privileged dugong/dugongcmd-qiime

At the end of the commands a Dugong instance will be available in the container named Dugong. Details about the container can be obtained through the command below:

    $ docker ps
