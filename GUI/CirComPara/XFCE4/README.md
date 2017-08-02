# DugongGUI - CirComPara

CirComPara is a computational pipeline to detect, quantify, and correlate expression of linear and circular RNAs from RNA-seq data.

## Quick install Dugong:

To start a container, the user must have Docker installed on his operating system, according to the tutorials available in the project documentation. The Dugong image is available in the Docker Hub and its use is the recommended method of installation.

Two steps are required to start a container containing Dugong. In the first step, the Dugong image is downloaded from the Docker Hub servers to the host, and in the second, a container is created on the host machine with the default Dugong installation. If the host machine is a Linux, the following commands must be performed in the terminal:


$ docker pull dugong/dugong-circompara
$ docker run -d -p 5901:5901 -p 6901:6901 -v $HOME/dugong/:/data/ \
    --name Dugong-CirComPara -h Dugong-CirComPara --privileged dugong/dugong-circompara
At the end of the commands a Dugong instance will be available in the container named Dugong. Details about the container can be obtained through the command below:

$ docker ps

## Video installation:

Click to watch the installation of DugongGUI on Linux Ubuntu Server in video:

Click to watch the installation of DugongCMD on Linux Ubuntu Server in video:

## Test your installation

Type in the terminal:

cd test_circompara
cd analysis
../../circompara

If you plan to use single-end reads, test with meta_se.csv file instead of meta.csv.

## CirCompara working in Dugong

CircRNA analysis using a CirComPara tool on an Ubuntu Server with a DugongGUI container installed:
Watch the video

## How to use

Set your analysis project

This section shows how to set your project directory and run the analysis. To run an analysis usually you want to specify your data (the sequenced reads in FASTQ format) and a reference genome in FASTA format.

## Compose META file

You have to specify read files, sample names and sample experimental condition in a metadata table file. The file format is a comma separated text file with the following header:

file,sample,condition
Then, each row corresponds to a read file. If you have paired-end sequenced samples write one line per file with the same sample name and condition.

An example of the metadata table:

file	sample	condition
/home/user/reads_S1_1.fq	S1	WT
/home/user/reads_S1_2.fq	S1	WT
/home/user/reads_S2_1.fq	S2	MU
/home/user/reads_S2_1.fq	S2	MU
and metadata file content:

file,sample,condition
/home/user/reads_S1_1.fq,S1,WT
/home/user/reads_S1_2.fq,S1,WT
/home/user/reads_S2_1.fq,S2,MU
/home/user/reads_S2_1.fq,S2,MU
In the meta file you can also specify the adapter sequences to preprocess the reads, just add an adapter column with the adpter file.

file	sample	condition	adapter
/home/user/reads_S1_1.fq	S1	WT	/home/user/circompara/adapter.fa
/home/user/reads_S1_2.fq	S1	WT	/home/user/circompara/adapter.fa
Specify the reference genome file

A required parameter is the reference genome. You can either pass the reference genome from the command line

./circompara "GENOME_FASTA='/home/user/genomes/Homo_sapiens.GRCh38.dna.primary_assembly.fa'"
or by setting the GENOME_FASTA parameter in the vars.py file; e.g.:

GENOME_FASTA = '/home/user/genomes/Homo_sapiens.GRCh38.dna.primary_assembly.fa'
Specify options in vars.py

Although parameters can be set from command line (sorrounded by quotes), you can set them in a local vars.py file, which must be placed in the analysis directory. Parameters not specified by the user will take defaulkt values.
Below there is the full list of the parameters:

META: (required) The metadata table file where you specify the project samples, etc.
    default: meta.csv

GENOME_FASTA: (required) The FASTA file with the reference genome
    default: 

ANNOTATION: Gene annotation (Ensembl GFF)
    default: 

CIRCRNA_METHODS: Comma separated list of circRNA detection methods to use. Use all methods available (default)
    default: 

CPUS: Set number of CPUs to be used by each method
    default: 4

TOGGLE_TRANSCRIPTOME_RECONSTRUCTION: Set 'True' to enable transcriptome reconstruction. 'False' only quantifies genes and transcripts from the given annotation GTF file
    default: False
    
PREPROCESSOR: The preprocessing method. Set "" for no preprocessing
    default: trimmomatic

PREPROCESSOR_PARAMS: Read preprocessor extra parameters. F.i. if Trimmomatic, an empty string defaults to MAXINFO:40:0.5 LEADING:20 TRAILING:20 SLIDINGWINDOW:4:30 MINLEN:50 AVGQUAL:30 
    default: 
    
CIRI: The full path to the CIRI_vx.x.pl perl script
    default: 

CIRI_EXTRA_PARAMS: CIRI additional parameters
    default: 

BWA_PARAMS: Extra parameters for BWA
    default: 

GENOME_INDEX: The index of the reference genome for HISAT2
    default: 

SEGEMEHL_INDEX: The .idx index for segemehl
    default: 

BWA_INDEX: The index of the reference genome for BWA
    default: 

BOWTIE2_INDEX: The index of the reference genome for BOWTIE2
    default: 

STAR_INDEX: The directory path where to find Star genome index
    default: 

GENEPRED: The genome annotation in GenePred format
    default: 

HISAT2_EXTRA_PARAMS: Extra parameters to add to the HISAT2 aligner fixed parameters '--dta --dta-cufflinks --rg-id <SAMPLE> --no-discordant --no-mixed --no-overlap'. For instance, '--rna-strandness FR' if stranded reads are used.
    default: 

CUFFLINKS_PARAMS: Cufflinks extra parameters. F.i. '--library-type fr-firststrand' if dUTPs stranded library were used for the sequencing
    default: 

CUFFQUANT_EXTRA_PARAMS: Cuffquant parameter options to specify. E.g. --frag-bias-correct $GENOME_FASTA  --multi-read-correct --max-bundle-frags 9999999
    default: 

CUFFNORM_EXTRA_PARAMS: Extra parameters to use if using Cuffnorm
    default: --output-format cuffdiff
    
READSTAT_METHODS: Comma separated list of methods to use for read statistics. Currently supported: fastqc,fastx
    default: fastqc
    
CUFFDIFF_EXTRA_PARAMS: Cuffdiff parameter options to specify. E.g. --frag-bias-correct $GENOME_FASTA  --multi-read-correct
    default: 

DIFF_EXP: Set True to enable differential expression computation. Only available if more than one sample and more than one condition are given
    default: False

DESEQ: Set True to enable differential expression computation also with DESeq2. Only available if more than one sample and more than one condition are given
    default: False

QRE_FIND: Set True to toggle analysis of QKI response elements sequences
    default: False
    
Run the analysis

To trigger the analyses you simply have to call the ./circompara script in the analysis directory. Remember that if you use the vars.py option file, this has to be in the analysis directory.

cd /home/user/circrna_analysis
/home/user/circompara/circompara

Additional options from the Scons engine:

Dryrun: to see which commands will be executed without actually execute them, use the -n option. NB: many commands will be listed, so you should redirect to a file or pipe to a reader like less

  /path/to/circompara/dir/circompara -n | less -SR
Basic execution:

  /path/to/circompara/dir/circompara
Multitasks: the -j option specifies how many tasks can be run in parallel. Caveat: the '-j * CPUS' value should not be greater than the number of CPU cores available.

  /path/to/circompara/dir/circompara_CirComPara -j4
Ignore errors: keep executing the tasks even when some of them fails. Caveat: this can break downstream analyses

  /path/to/circompara/dir/circompara -i
Combine options: to set multiple options you must sorround them with quotes

  /path/to/circompara/dir/circompara_CirComPara "-j4 -i"

#Output files

Results regarding circRNAs are reported in circrna_analyze directory with a summary reported in circrna_analyze/circRNAs_analysis.html file. Gene expression tables are saved in cuffdiff directory.

Advanced features

Stranded libraries

Some tools in CirComPara require special parameters to handle properly stranded reads. CirComPara allows to specify such parameters

Example: include the following parameters if you used the Illumina TruSeq Stranded Total RNA Library Prep Kit with Ribo-Zero Human/Mouse/Rat

HISAT2_EXTRA_PARAMS = "--rna-strandness FR "
CUFFLINKS_PARAMS = "--library-type fr-firststrand "
How to cite CirComPara

If you used CirComPara for your analysis, please add the following citation to your references:

Gaffo, E., Bonizzato, A., Kronnie, G. te & Bortoluzzi, S. CirComPara: A Multi‐Method Comparative Bioinformatics Pipeline to Detect and Study circRNAs from RNA‐seq Data. Non-Coding RNA 3, 8 (2017). [http://www.mdpi.com/2311-553X/3/1/8][circompara_article]
