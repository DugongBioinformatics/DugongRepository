# CirComPara Pipeline

To demonstrate Dugong ́s effectiveness to distribute and run bioinformatics tools in alternative computational environments, the [CirComPara](http://www.mdpi.com/2311-553X/3/1/8) pipeline was implemented in a Dugong container and tested in different OS with the aid of virtual machines (VM) or cloud computing servers.

***CirComPara*** is a computational pipeline to detect, quantify, and correlate expression of linear and circular RNAs from RNA-seq data. Is a highly complex pipeline, which employs a series of bioinformatics software and was originally designed to run in an Ubuntu Server 16.04 LTS (x64).

Although authors provide details regarding the expected versions of each software and their dependency requirements, several problems can still be encountered during CirComPara implementation by inexperienced users (see [documentation](https://goo.gl/Eg6cKG) for CirComPara installation details).

## Simulating reproducibility and replicability in alternative OS

To simulate the reproducibility and replicability of the CirComPara pipeline after its implementation in Dugong, we have created different virtual machines in [VirtualBox](https://www.virtualbox.org/) and [CloudatCost Hosting](http://cloudatcost.com/).

For the simulations the following operating systems were used for the virtual machines:

- Ubuntu Server (CloudatCost)
- CentOS (CloudatCost)
- Ubuntu (VirtualBox)
- Fedora (VirtualBox)
- Arch Linux (VirtualBox)
- Windows (VirtualBox)

We make available in a virtual drive the OVA images created by VirtualBox, except for Windows due to Microsoft license issues. These images can be found [here](https://mega.nz/#F!cPhDUTTT!pXZy-CtLEvR4wx0uqpeqWQ).

Note: The images are large in size because they have all the standard Docker installation and containers for the DugongGUI, DugongCMD and Dugong-CirComPara pre-installed.

Below we provide a video from a CircRNA analysis using the CirComPara tool on an Ubuntu Server of CloudatCost with a DugongGUI container installed. The video presents a complete implementation of CirComPara with the test data provided by the authors and their expected results:

[![Watch the video](https://raw.githubusercontent.com/DugongBioinformatics/dugongbioinformatics.github.io/master/.misc/Screenshot%20from%202017-08-01%2004-41-23.png)](https://www.youtube.com/watch?v=8FlvmERIKJI)

### Simulating reproducibility and replicability using a pipeline in Jupyter Notebook

To demonstrate the ease of execution of CirComPara using Jupyter Notebook, available in all versions of Dugong, we have developed a simple CircRNA analysis pipeline.

This pipeline can be found in our [repository](https://github.com/DugongBioinformatics/DugongRepository/blob/master/Notebooks/CirComPara/CirComPara%20Pipeline.ipynb) along with the [results](https://github.com/DugongBioinformatics/DugongRepository/blob/master/Notebooks/CirComPara/Example_Results/CirComPara%20Pipeline%20(Results).ipynb) obtained during its execution.

Output files are not available in the repository, but can be [downloaded here](https://github.com/DugongBioinformatics/DugongRepository/blob/master/Notebooks/CirComPara/Example_Results/circrna_analyze.zip).

Below we present a video demonstrating the implementation of the pipeline, after the download in our repository, and its execution:

[![Watch the video](https://raw.githubusercontent.com/DugongBioinformatics/dugongbioinformatics.github.io/master/.misc/Screenshot%20from%202017-08-07%2001-18-21.png)](https://www.youtube.com/watch?v=lk92Jj7JDiI)

## Results of simulations

In the table below, we provide the results obtained in the simulations performed using the different operating systems mentioned above as hosts for Dugong-CirComPara. The table deals with the detection of CircRNAs using the different predictive methods available in CirComPara:

![Comparative](https://raw.githubusercontent.com/DugongBioinformatics/dugongbioinformatics.github.io/master/.misc/CirComPara.png)

All results obtained in our tests in different computational environments demonstrated 100% reproducibility based on the data expected by the test samples made available by the authors of CirComPara.

We also provide the HTML results created in CirComPara for operating systems: [Windows](http://htmlpreview.github.io/?https://github.com/DugongBioinformatics/dugongbioinformatics.github.io/blob/master/.results/windows/circRNAs_analysis.html), [CentOS](http://htmlpreview.github.io/?https://github.com/DugongBioinformatics/dugongbioinformatics.github.io/blob/master/.results/centos/circRNAs_analysis.html), [Fedora](http://htmlpreview.github.io/?https://github.com/DugongBioinformatics/dugongbioinformatics.github.io/blob/master/.results/fedora/circRNAs_analysis.html), [Ubuntu](http://htmlpreview.github.io/?https://github.com/DugongBioinformatics/dugongbioinformatics.github.io/blob/master/.results/ubuntu/circRNAs_analysis.html) and [Arch Linux](http://htmlpreview.github.io/?https://github.com/DugongBioinformatics/dugongbioinformatics.github.io/blob/master/.results/arch/circRNAs_analysis.html).

## Quick installation of Dugong CirComPara

To start a container, the user must have Docker installed on his/her operating system, according to the tutorials available in the Docker project documentation. The Dugong image is available in the Docker Hub and its use is the recommended method of installation.

Two steps are required to start a container containing Dugong. In the first step, the Dugong image is downloaded from the Docker Hub servers to the host, and in the second, a container is created on the host machine with the default Dugong installation. If the host machine is a Linux, the following commands must be performed in the terminal:

```
docker pull dugong/dugong-circompara
docker run -d -p 5901:5901 -p 6901:6901 -v $HOME/dugong/:$HOME/data/ \
    --name Dugong-CirComPara -h Dugong-CirComPara --privileged dugong/dugong-circompara
```


At the end of the commands a Dugong instance will be available in the container named Dugong. Details about the container can be obtained through the command below:

```
docker ps
```

## Test your installation

Type in the terminal:

```
cd test_circompara
cd analysis
../../circompara
```

If you plan to use single-end reads, test with meta_se.csv file instead of meta.csv.
