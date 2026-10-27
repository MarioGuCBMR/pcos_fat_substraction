# pcos_fat_substraction
Repository to compute GWAS by substraction between PCOS and adiposity traits

## Download data

This project utilizes GSEM's approach of GWAS by substraction to identify the shared and independent biology for PCOS and adiposity and fat distribution traits.

## Packages and environment.

All code produced for this project is run on an HPC server with slurm queueing system and a module system for tools.
Unless stated otherwise, all analyses are run with the following softwares:

```
gcc/11.2.0
R/4.3.1
anaconda3/5.3.1 #depending on the way your modules are assigned, anaconda3 might have its own gcc assigned. Unload gcc/11.2.0 for those analyses to make thing work!
```
Regarding R modules, please install before starting reproducing the analyses:

```
install.packages("tidyverse")
install.packages("data.table")
install.packages("ieugwasr")
install.packages('gwasvcf', repos = c('https://mrcieu.r-universe.dev', 'https://cloud.r-project.org'))
install.packages(GenomicRanges)
install.packages(rtracklayer)
install.packages("bigsnpr")
install.packages("GenomicSEM")

if (!require("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

BiocManager::install("VariantAnnotation")
BiocManager::install("SNPlocs.Hsapiens.dbSNP155.GRCh37")

```
Additionally, in raw_data/software_and_utils please follow this code to download additional code and packages:

```
mkdir $WD/raw_data/utils
cd $WD/raw_data/utils

#Liftover chains:

wget https://hgdownload.soe.ucsc.edu/gbdb/hg19/liftOver/hg19ToHg38.over.chain.gz
wget https://hgdownload.soe.ucsc.edu/gbdb/hg38/liftOver/hg38ToHg19.over.chain.gz

gzip -d $WD/raw_data/utils/hg19ToHg38.over.chain.gz
gzip -d $WD/raw_data/utils/hg38ToHg19.over.chain.gz
```

#Download reference panels and data to run LDSC, that base for G-SEM

```


```
