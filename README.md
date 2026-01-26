

<p align="left">
  <img src="logo.jpg" alt="syntheticMosaic Logo" width="300">
</p>

We created a synthetic mosaic human DNA sample by spiking twenty 500bp oligos with known pathogenic variants into a WT human DNA background. The oligos are spiked in at low concentrations relative to WT DNA to emulate low grade mosaicism:
- Different oligos are spiked in at different concentrations so that the variant allele frequencies (VAF) vary between 0.5 and 6 percent.
- We chose this VAF range because it reflects the range of VAFs typically found in pathogenic mutations in the PIK-AKT-MTOR and MAPK pathways ([Fujita et al. 2023](https://pubmed.ncbi.nlm.nih.gov/36864519/), [Khoshkhoo et al. 2023](https://pubmed.ncbi.nlm.nih.gov/37126322/), [Krochmalnek et al. 2023](https://pubmed.ncbi.nlm.nih.gov/37900581/)).
- Most variants are placed in MTOR and PIK3CA.
- We characterise VAF in the final synthetic sample containing all 20 variants by droplet digital PCR (ddPCR-VAF).
- We sequenced this sample by whole exome capture and by ampliconSeq (amplification of the regions bearing mosaic variants). From the resulting BAM files, we can compute the BAM-VAF.

The primary purpose of this sample is to serve as a positive control for pathogenic mosaic variant detection by high throughput sequencing. The strengths of this sample are:
- "Truth" VAFs are determined by an orthogocal method which is the gold standard of absolute concentration measurement (ddPCR).
- It can be used as an end-to-end control i.e. it is processed through all stages of the analysis pipeline: sample preperation, sequencing, and bioinformatic analysis.

You can request an alliquot of this sample by contacting us (Tim Hughes and Asbjørn Holmgren - Department of Medical Genetics - Oslo University Hospital).


### Sample creation and characterisation using ddPCR

- [Word document describing creation of the synthetic DNA sample](010_sampleCreation/syntheticMosaic_README.docx). This document covers: sample naming, creation protocol, VAF verification, possible application of this sample)
- [Excel spreadsheet documenting oligos and ddPCR assays used](010_sampleCreation/variants_oligos_synthetic_sample_v1b4.xlsx)
- [Truth VCF file](010_sampleCreation/mosaic-v01b04_truthVAF.vcf): 20 variants with their ddPCR measured variant allele frequencies (VAF) in the final sample provided in the INFO field of the VCF file.


### Whole Exome Sequencing (Agilent + Illumina) of sample

We performed DNA capture using a whole exome kit and Illumina sequencing of the library
- [BAM file](020_sampleWholeExomeSeq/synthetic-mosaic_tumor.variantRegions.bam) at the relevant exons is available for inspection in IGV (b37 with decoy reference genome) 
- The oligos with mutations are covered with sequencing reads in a similar way to WT DNA (IGV screenshots for [AKT3](020_sampleWholeExomeSeq/IGV_screenshots/AKT3.png), [CACNA1D](020_sampleWholeExomeSeq/IGV_screenshots/CACNA1D.png),[PIK3CA](020_sampleWholeExomeSeq/IGV_screenshots/PIK3CA.png))
- All mosaic variants are represented in the sequencing data. Further, there is no systematic bias of the BAM-VAF (tendency to over- or underestimate the ddPCR-VAF) and the BAM-VAF can be used as an approximate indicator of the true VAF (“is usually roughly correct” but is not precise).
![Comparison of ddPCR VAF and BAM VAF](020_sampleWholeExomeSeq/ddPCR-VAFvsBAM-VAF.png)


### AmpliconSeq of sample

Awaiting the second sequencing and Asbjørn analysis.

How does ampliconSeq compare to WES on VAF accuracy? A better match between ddPCR and ampliconSeq could be due to the fact that both use amplicon based measurements.