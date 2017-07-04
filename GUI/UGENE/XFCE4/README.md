***UGENE*** is free open-source cross-platform bioinformatics software.

## Features of UGENE

UGENE 3D Protein Structure Viewer:

![UGENE](http://ugene.net/wp-content/themes/Ugene/gallery/images/3dstruct.png)

A nucleotide sequence is opened. The BLAST NCBI and Short Tandem Repeats Finder tasks are launched in the background:

![UGENE](http://ugene.net/wp-content/themes/Ugene/gallery/images/project_and_sequence_view.png)

A sample workflow schema of the Workflow Designer. The schema filters each input gene sequence by its length:

![UGENE](http://ugene.net/wp-content/themes/Ugene/gallery/images/wd_filter_by_length.png)

A BAM file is opened in the Assembly Browser:

![UGENE](http://ugene.net/wp-content/themes/Ugene/gallery/images/wd_filter_by_length.png)

A BAM file is opened in the Assembly Browser:

![UGENE](http://ugene.net/wp-content/themes/Ugene/gallery/images/ass_br_diff_mode.png)


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

## Site UGENE

http://ugene.net/

## Cite UGENE

Okonechnikov K, Golosova O, Fursov M, the UGENE team. Unipro UGENE: a unified bioinformatics toolkit. Bioinformatics 2012 28: 1166-1167. doi:10.1093/bioinformatics/bts091

Golosova O, Henderson R, Vaskin Y, Gabrielian A, Grekhov G, Nagarajan V, Oler AJ, Quiñones M, Hurt D, Fursov M, Huyen Y. Unipro UGENE NGS pipelines and components for variant calling, RNA-seq and ChIP-seq data analyses. PeerJ 2014 2:e644. doi:10.7717/peerj.644
