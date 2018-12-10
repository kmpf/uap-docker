Welcome to the uap Test Container
=================================

This container is meant to be used as a hands-on experience of uap. You can find the uap code repository at https://github.com/yigbt/uap and the documentation at https://readthedocs.org/projects/uap/.

If you start the container via one of the `make docker-run-*` commands, the container will get removed as you leave it. This means downloaded or processed data will be lost after logging out of the container!

Installed Bioinformatic Tools
-----------------------------

The uap test container contains installations of the following tools:

Tool     | Version | Path to Executable
-------- | ------- | ------------------
bowtie2  | 2.2.9   | /home/uap_user/bioinformatic-tools/bowtie2/bowtie2-2.2.9/bowtie2
bwa      | 0.7.15  | /home/uap_user/bioinformatic-tools/bwa/bwa-0.7.15/bwa
samtools | 1.3.1   | /home/uap_user/bioinformatic-tools/samtools/samtools-1.3.1/samtools
segemehl | 0.2.0   | /home/uap_user/bioinformatic-tools/segemehl/segemehl_0_2_0/segemehl/segemehl.x

These tools are required to execute the available example workflows.

uap Folders
-----------

The uap installation is found at /home/uap_user/uap/.
The subfolders are explained in the table below:

Folder                  | Explanation
----------------------- | -----------
example-configurations/ | Configurations for example workflows
|_example-out           | Output of example workflows go here
cluster/                | Cluster configuration files
doc/                    | Documentation
include/steps           | Available processing steps
include/sources         | Available source steps
include/subcommands     | Subcommand scripts


uap Workflows
-------------

Depending on the container you started it either already contains the genomic
and the sequencing data or it only contains the uap installation.

uap:1.0.0
*********

The uap:1.0.0 container contains only an installation of uap and no external
data. Users can start workflows that download data such as:

* download_human_gencode_release_v19.yaml
  * Downloads the human Gencode annotation v19
  * Downloads the human Gencode long non-coding RNA gene annotation v19
  * the downloaded files are located in `genomes/animalia/chordata/mammalia/primates/homo_sapiens/gencode`

* index_homo_sapiens_hg19_chr21.yaml
  * Downloads the homo sapiens chromosome sizes from UCSC
  * Downloads the homo sapiens chromosome 21 FASTA sequence from UCSC
  * the downloaded files are located in `genomes/animalia/chordata/mammalia/primates/homo_sapiens/hg19`
  * Generates the index for bowtie2 for chromosome 21
  * Generates the index for bwa for chromosome 21
  * Generates the fasta index for chromosome 21

* index_mycoplasma_genitalium_ASM2732v1_genome.yaml
  * Downloads the mycoplasma genitalium genome from NCBIs Genbank, these files are located in `genomes/bacteria/Mycoplasma_genitalium/`
  * Generates the index for bowtie2 for that genome
  * Generates the index for bwa for that genome
  * Generates the index for segemehl for that genome
  * Generates the fasta index for that genome

* ChIPseq-data-download-short.yaml
  * Downloads the ChIPseq data of H3K4me1 and H3K4me3 published in
   "High-Resolution Profiling of Histone Methylations in the Human Genome"
   Barski et al., Cell, 2007

* ChIPseq-data-download-full.yaml
  * Downloads the complete ChIPseq data published in
   "High-Resolution Profiling of Histone Methylations in the Human Genome"
   Barski et al., Cell, 2007

* RNAseq-data-download.yaml
  * Downloads the RNAseq and supplementary data published in
   "Targeted sequencing for gene discovery and quantification using RNA CaptureSeq"
   Mercer et al., Nature protocols, 2014


User Information
----------------

You enter this container as this user:

User | Password
---- | --------
uap  | manager



uap directory: `/home/uap_user/uap`
tools directory: `/home/uap_user/bioinformatic-tools`


You will now be dropped out to: `/home/uap_user/`

Have fun!
