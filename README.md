# Amplicon-pipeline

![image](https://user-images.githubusercontent.com/69192049/170900440-2450f153-b4f8-41ec-acb8-57c4236aacd6.png) 

![image](https://user-images.githubusercontent.com/69192049/170900515-15534e55-0ca7-4b4d-aa84-35b0beb43fec.png)



# Overview 

This repository contains a simple  [Usearch](https://drive5.com/usearch/new5.html) amplicon pipeline and allows use of a user-curated reference database and/or a `blastn` query for taxonomic identification. 

This pipeline generates both 97% OTUs and ZOTUs.

The scripts contained herein are:

``` 
00-run.sh                            - runs the below scripts:

01-setup                             - builds folder structure, removing previous output data
02-fastqc.sh                         - QC check on reads
03-merge.sh                          - merges paired-end amplicon reads
04-strip_primers.sh                  - remove primer binding regions from merged reads
05-filter.sh                         - quality filtering of stripped reads 
06-uniques.sh                        - generate unique reads and occurance numbers
07-otus.sh                           - filters chimeras, clusters OTUs (cluster_otus) and generates ZOTUs (unoise3)
08-otutable.sh                       - generates 97% OTU and 99% ZOTU tables
09-taxonomy.sh                       - taxonomy assignment of OTUs/ZOTUs via user-inputted reference database
10-blast.sh                          - taxonomy assignment of OTUs/ZOTUs using blastn nt database
11-export.sh	                     - convert files for export into R

```
3 files produced for  each clustering type (*OTU/ZOTU*):

```
**_table.txt                      - taxonomic unit table
**_sintax.txt                     - assigned sintax using reference database
**_blast.txt                      - top 10 hits using blast nt database
```

## Dependencies 

Install Usearch, 32-bit binary download available [here](https://drive5.com/usearch/download.html)

Install BLAST+ as per instructions [here](https://iamphioxus.org/2018/01/08/local-installation-of-ncbi-blast-together-with-the-nr-and-taxonomy-database/)
 - Reccomended: install the `nt` database locally if storage available
 - install the latest BLAST+ version if accessing `nt` database remotely via the `-remote` command.

## How To

### Bash Scripts

#### Set up analysis environment

Firstly, confirm both Usearch and BLASTn are installed correctly:
```
bash usearch
bash blastn
```

Then download this GitHub repository to your local file system and `cd` into the repository's folder:

```
bash git clone https://github.com/samt9892/amplicon-pipeline.git
```

The folder structure should be as follows:
```
.
├── export
├── fastqc
├── fq
├── out
├── reference
└── scripts
```

The pipeline expects fastq of your amplicon sequencing data in the fq/ folder. The files should be named `*sample_name*_R1.fastq` and `*sample_name*_R2.fastq`

An example reference database `ref.fa` is included in the reference/ folder. The naming structure therein should be followed when adding reference sequences.

Run the pipeline using the command:
```
bash scripts/./00-run
```

## Authors and contributors
Samuel Thompson

                                   
