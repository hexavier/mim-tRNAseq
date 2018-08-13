# mim-tRNAseq
### Modification-induced misincorporation based sequencing of tRNAs using high-throughput RNA sequencing datasets.

This package is a semi-automated analysis pipeline for the quantification and analysis of tRNA expression. Given trimmed sequencing reads in fastq format, this pipeline will:
* Align the reads
* Calculate coverage information and plots (useful for QC)
* Quantify expression
* Calculate tRNA differential expression with [DESeq2](https://bioconductor.org/packages/release/bioc/html/DESeq2.html).

## Alignment strategy

The driving force behind this pipeline is the unique alignment strategy it uses to accurately place tRNA-seq reads during alignment. The method is based off the ability of a reverse transcriptase (RT), TGIRT, to misincorportate incorrect nucleotides at modified tRNA positions. 

Due to the abundance of modifications to tRNA residues as well as high sequence conservation between tRNA genes and families of isoacceptors, the generation and alignment of tRNA sequencing datasets is faced with two problems: 1) the modifications cause normal RTs to fail during the cDNA synthesis step of RNA-seq library preparation, and 2) even when long enough reads are sequenced, they cannot be uniquely placed during alignment because of the high degree of sequeunce similarity between tRNAs. This results in high rates of multi-mapping reads which are difficult to use for downstream analysis.

Using mim-tRNAseq and TGIRT overcomes these problems. Misincorporations at modified nucleotides by TGIRT allows read-through of modifications producing longer reads and libraries with more even gene coverage. Additionally, indexed modification data is used by mim-tRNAseq to account for misincorporations, and thereby guides more accurate read placement and lowers rates of multi-mapping reads. Collectively, mim-tRNAseq improves tRNA gene coverage from sequencing data and thereby reduces bias, enables more data from libraries to be used by reducing multi-mapping, and overall improves estimation of tRNA expression.

## Install

mim-tRNAseq can be installed using ```pip``` as follows:
```
pip install mim-tRNAseq
```

## Dependencies

Unix command line dependencies:

Tool | Version >=
-----|--------
Subread package | 1.6.2
GMAP-GSNAP | 2018-05-30
samtools | 1.6
usearch | 10.0.240
bedtools | 2.26.0
R | 3.3.1

Required R packages:

Package | Version >=
--------|------------
ggplot2 | 2.2.1
DESeq2 | 1.14.1
RColorBrewer | 1.1.2  
pheatmap | 1.0.10
calibrate | 1.7.2

When mim-tRNAseq is installed using ```pip``` as described above, all Python package dependencies will be installed automatically. These include:

Package | Version >=
--------|---------
biopython | 1.70
pyfiglet | 0.7.5
pybedtools | 0.7.10
pandas | 0.22.0
numpy | 1.14.0
 
## Usage

## Input formatting

## Outputs

## Contact

## Cite

## 