# Amplicon-pipeline

![image](https://user-images.githubusercontent.com/69192049/170900440-2450f153-b4f8-41ec-acb8-57c4236aacd6.png) 

![image](https://user-images.githubusercontent.com/69192049/170900515-15534e55-0ca7-4b4d-aa84-35b0beb43fec.png)



# Overview 

This repository contains a simple  [Usearch](https://drive5.com/usearch/new5.html) amplicon pipeline and allows use of a user-curated reference database and/or a `blastn` query for taxonomic identification. 

This pipeline generates both 97% OTUs and ZOTUs.

The scripts contained herein are:

``` 
00-run.sh                            - setup folder structure and runs the below scripts:

01-fastqc.sh                         - QC check on reads
02-merge.sh                          - merges paired-end amplicon reads
03-strip.sh                          - removes primer binding regions from merged reads
04-filter.sh                         - quality filtering of stripped reads 
05-uniques.sh                        - generate unique reads and occurance numbers
06-otus.sh                           - filters chimeras, clusters OTUs (cluster_otus) and generates ZOTUs (unoise3)
07-otutable.sh                       - generates 97% OTU and 99% ZOTU tables
08-taxonomy.sh                       - taxonomy assignment of OTUs/ZOTUs via user-inputted reference database
09-blast.sh                          - taxonomy assignment of OTUs/ZOTUs using blastn nt database
10-export.sh	                     - convert files for export into R

```
3 files produced for  each clustering type (*OTU/ZOTU*):

```
**_table.txt                      - taxonomic unit table
**_sintax.txt                     - assigned sintax using reference database
**_blast.txt                      - top 10 hits using blast nt database
```

## Dependencies 

Install Usearch, 32-bit binary download available [here](https://drive5.com/usearch/download.html)

Install blastn as per instructions [here](https://iamphioxus.org/2018/01/08/local-installation-of-ncbi-blast-together-with-the-nr-and-taxonomy-database/)
 - Reccomended: install the `nt` database locally if storage available
 - Get the latest version if accessing the `nt` database remotely via the `-remote` command.

## Contributors
Samuel Thompson

                                   
