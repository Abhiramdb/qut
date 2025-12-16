### Preparing SNP list for UCSC LiftOver (GRCh38 → GRCh37)

Input format (example):
```
CHR SNP A1 A2 MAF
1 chr1:10000:T:C T C 0.3
```
Required LiftOver format:
```
chr1 10000 10000
```
We can use `awk` to reformat the SNP list:

```bash
awk 'NR>1 {
    split($2, a, ":");
    print a[1], a[2], a[2], $2
}' OFS="\t" merged_sorted_eur_frq.snplist > formatted_fr_liftover_eur.snplist
```
This will create the file formatted_fr_liftover_eur.snplist in the correct 4-column BED-like format for UCSC LiftOver.

Next step: upload formatted_fr_liftover_eur.snplist to the UCSC LiftOver tool

## Command line UCSC
Download the software from the UCSC

```bash
chmod +x liftOver
```
Run liftOver:
```bash
./liftOver
```
Download the chain file:
```bash
wget https://hgdownload.soe.ucsc.edu/goldenPath/hg38/liftOver/hg38ToHg19.over.chain.gz
```
Perform the conversion:
```bash
./liftOver formatted_fr_liftover_eur.snplist hg19ToHg38.over.chain.gz conversions.bed unMapped
```
