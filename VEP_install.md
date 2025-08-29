# VEP Annotation Environment Setup

This guide provides steps to set up an environment for using Ensembl VEP (Variant Effect Predictor).

## 1. Create a Conda Environment

```bash
conda create -n annotation_vep -c conda-forge -c bioconda ensembl-vep
```
## Download VEP Cache
```bash
curl -O https://ftp.ensembl.org/pub/release-114/variation/indexed_vep_cache/homo_sapiens_vep_114_GRCh38.tar.gz
tar xzf homo_sapiens_vep_114_GRCh38.tar.gz
```

## Move Cache to VEP Directory
```bash
mv homo_sapiens ~/.vep
```
## To use
```bash
conda activate annotation_vep
vep --help
```
