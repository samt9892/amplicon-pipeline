# amplicon-pipeline

![image](https://user-images.githubusercontent.com/69192049/170900440-2450f153-b4f8-41ec-acb8-57c4236aacd6.png) 

![image](https://user-images.githubusercontent.com/69192049/170900515-15534e55-0ca7-4b4d-aa84-35b0beb43fec.png)



# Overview 

This repository contains a simple  [Usearch](https://drive5.com/usearch/new5.html) amplicon pipeline and allows use of a user-curated reference database and/or a `blastn` query for taxonomic identification. 

This pipeline generates both 97% OTUs and ZOTUs.

The scripts contained herein are:

``` 
run.sh                            - sets up folder structure and runs the below scripts in order:

merge.sh                          - merges paired-end amplicon reads
strip.sh                          - removes primer binding regions from merged reads
filter.sh                         - quality filtering of stripped reads 
uniques.sh                        - generate unique reads and occurance numbers
otus.sh                           - filters chimeras, clusters OTUs (cluster_otus) and generates ZOTUs (unoise3)
otutable.sh                       - generates 97% OTU table and 99% ZOTU table\
taxonomy.sh                       - taxonomy assignment of OTUs/ZOTUs via user-inputted reference database
otu_blast.sh                      - taxonomy assignment of OTUs using blastn nt database
zotu_blast.sh                     - taxonomy assignment of ZOTUs using blastn nt database
export.sh							            - converting files for export into R

```

## Dependencies 

install usearch, 32-bit binary download available [here]https://drive5.com/usearch/download.html

Install blastn via instructions [here]https://iamphioxus.org/2018/01/08/local-installation-of-ncbi-blast-together-with-the-nr-and-taxonomy-database/
 - Reccomended: install the `nt` database locally if storage available
 - Get the latest version if accessing the `nt` database remotely via the `-remote` command.



                                   
