# CirComPara Pipeline

To demonstrate Dugong ́s effectiveness to distribute and run bioinformatics tools in alternative computational environments, the [CirComPara](http://www.mdpi.com/2311-553X/3/1/8) pipeline was implemented in a Dugong container and tested in different OS with the aid of virtual machines (VM) or cloud computing servers.

***CirComPara*** is a computational pipeline to detect, quantify, and correlate expression of linear and circular RNAs from RNA-seq data. Is a highly complex pipeline, which employs a series of bioinformatics software and was originally designed to run in an Ubuntu Server 16.04 LTS (x64).

Although authors provide details regarding the expected versions of each software and their dependency requirements, several problems can still be encountered during CirComPara implementation by inexperienced users (see [documentation](https://goo.gl/Eg6cKG) for CirComPara installation details).

## Simulate the reproducibility and replicability

To simulate the reproducibility and replicability of the CirComPara pipeline after its implementation in Dugong, we have created different virtual machines in [VirtualBox](https://www.virtualbox.org/) and [CloudatCost Hosting](http://cloudatcost.com/).



- Video from a CircRNA analysis using the CirComPara tool on an Ubuntu Server with a DugongGUI container installed. The video presents a complete implementation of CirComPara with the test data provided by the authors and their expected results:

[![Watch the video](https://raw.githubusercontent.com/DugongBioinformatics/dugongbioinformatics.github.io/master/.misc/Screenshot%20from%202017-08-01%2004-41-23.png)](https://www.youtube.com/watch?v=8FlvmERIKJI)
