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
## Annotation Notes

Most of the time, **VEP** throws connection errors with the database if we try to annotate online.  
Here, we are performing the annotation **offline**.  

- The reference FASTA file can be obtained from: [GENCODE Human](https://www.gencodegenes.org/human/)  
- The code below will result in **only one line per variant**:
```bash
vep \
	--input_file snps_ensembl.txt \
	--output_file annotated_variants_canonical.txt \
	--species homo_sapiens \
	--fasta /work/gencode47_GRCh38.p14_Human/GRCh38.primary_assembly.genome.fa \
	--cache \
	--everything \
	--canonical \
	--pick_allele \
	--fork 8 \
	--offline
```

