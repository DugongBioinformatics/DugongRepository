# CirComPara Pipeline

To demonstrate Dugong ́s effectiveness to distribute and run bioinformatics tools in alternative computational environments, the [CirComPara](http://www.mdpi.com/2311-553X/3/1/8) pipeline was implemented in a Dugong container and tested in different OS with the aid of virtual machines (VM) or cloud computing servers.

***CirComPara*** is a computational pipeline to detect, quantify, and correlate expression of linear and circular RNAs from RNA-seq data. Is a highly complex pipeline, which employs a series of bioinformatics software and was originally designed to run in an Ubuntu Server 16.04 LTS (x64).

Although authors provide details regarding the expected versions of each software and their dependency requirements, several problems can still be encountered during CirComPara implementation by inexperienced users (see [documentation](https://goo.gl/Eg6cKG) for CirComPara installation details).

## Simulate the reproducibility and replicability

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

## Results of the simulations

In the table below, we provide the results obtained in the simulations performed using the different operating systems mentioned above as hosting for Dugong-CirComPara. The table deals with the detection of CircRNAs using the different predictive methods available in CirComPara:

![Comparative](https://raw.githubusercontent.com/DugongBioinformatics/dugongbioinformatics.github.io/master/.misc/CirComPara.png)

All results obtained in our tests in different computational environments demonstrated 100% reproducibility based on the data expected by the test samples made available by the authors of CirComPara.

We also provide the HTML results created in CirComPara for operating systems: Windows, CentOS, [Ubuntu](http://htmlpreview.github.io/?https://github.com/DugongBioinformatics/dugongbioinformatics.github.io/blob/master/.results/ubuntu/circRNAs_analysis.html) and Arch Linux.

