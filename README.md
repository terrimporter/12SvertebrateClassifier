# 12S Vertebrate Reference Set For The RDP Classifier 

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5150728.svg)](https://doi.org/10.5281/zenodo.5150728)  

This repository contains trained reference sets that can be used with the Ribosomal Database Project classifier (Wang et al., 2007) to taxonomically assign vertebrate 12S mitochondrial gene sequences.  The latest releases can be downloaded from https://github.com/terrimporter/12SvertebrateClassifier/releases

## Note

This classifier is suitable for classifying vertebrate 12S mitochondrial gene sequences to species rank.  Reference sequences were obtained from the NCBI nucleotide [accessed July 2021].  Taxonomy is based on the NCBI taxonomy database.

## How to cite

You can cite this repository directly:
Teresita M. Porter. (2021). terrimporter/12SvertebrateClassifier: 12S Vertebrate Classifier v1.0.0 (v1.0.0). Zenodo. https://doi.org/10.5281/zenodo.5150728  

If you use this reference set with the RDP classifier please also cite the naive Bayesian classification tool:
Wang et al. (2007) Naïve Bayesian classifier for rapid assignment of rRNA sequences into the new bacterial taxonomy. Applied and Environmental Microbiology, 73: 5261.

## How to use

Decompress the tar.gz file:

$ tar -xvzf FileName.tar.gz

Use with the RDP classifier:

java -Xmx8g -jar /path/to/rdp_classifier_2.13/dist/classifier.jar classify -t /path/to/mydata_trained/rRNAClassifier.properties -o ClassifiedQueryFilename QueryFilename

# Releases

### 12S Vertebrate v1.0

Created from the NCBI nucleotide database [accessed July 26, 2020].  This version contains 16,801 reference sequences and 11,633 taxa at all ranks, including 7,277 species.

**Taxonomic assignment results should be filtered according to their bootstrap support values to reduce false positive assignments.**  Cutoffs are based on leave-one-sequence-out testing of non-singleton species. Here we recommend MINIMUM bootstrap cutoffs according to query length and assignment rank.  Assuming your query sequences are represented in the reference set, using the cutoffs presented in the first table below should ensure 99% accuracy.  If you wish to cast a wider net, you can use the second tables below for 95% or 90% accuracy.

#### Bootstrap support cutoffs, 99% accuracy:

Rank | 500 bp+ | 400 bp | 300 bp | 200 bp | 100 bp
--- |:---:|:---:|:---:|:---:|:---:
Superkingdom | 0 | 0 | 0 | 0 | 0
Kingdom | 0 | 0 | 0 | 0 | 0
Phylum | 0 | 0 | 0 | 0 | 0
Class | 0 | 0 | 0 | 0 | 0 
Order | 20 | 20 | 30 | 30 | ... 
Family | 50 | 40 | 50 | 50 | ... 
Genus | 95 | 90 | 90 | 90 | ... 
Species * | NA | NA | NA | NA | NA 

NA = No cutoff available will result in 99% correct assignments

#### Bootstrap support cutoffs, 95% accuracy:

Rank | Full | 400 bp | 300 bp | 200 bp | 100 bp
--- |:---:|:---:|:---:|:---:|:---:
Superkingdom | 0 | 0 | 0 | 0 | 0
Kingdom | 0 | 0 | 0 | 0 | 0
Phylum | 0 | 0 | 0 | 0 | 0
Class | 0 | 0 | 0 | 0 | 0
Order | 0 | 0 | 0 | 0 | ... 
Family | 0 | 0 | 0 | 0 | ... 
Genus | 0 | 0 | 0 | 20 | ... 
Species * | 95 | 90 | 90 | 95 | NA 

NA = No cutoff available will result in 95% correct assignments

#### Bootstrap support cutoffs, 90% accuracy:

Rank | Full | 400 bp | 300 bp | 200 bp | 100 bp
--- |:---:|:---:|:---:|:---:|:---:
Superkingdom | 0 | 0 | 0 | 0 | 0
Kingdom | 0 | 0 | 0 | 0 | 0
Phylum | 0 | 0 | 0 | 0 | 0
Class | 0 | 0 | 0 | 0 | 0
Order | 0 | 0 | 0 | 0 | ... 
Family | 0 | 0 | 0 | 0 | ... 
Genus | 0 | 0 | 0 | 0 | ... 
Species * | 20 | 40 | 50 | 50 | NA  

NA = No cutoff available will result in 90% correct assignments

# References

Wang, Q., Garrity, G. M., Tiedje, J. M., & Cole, J. R. (2007). Naive Bayesian Classifier for Rapid Assignment of rRNA Sequences into the New Bacterial Taxonomy. Applied and Environmental Microbiology, 73(16), 5261–5267. Available from https://sourceforge.net/projects/rdp-classifier/

# Acknowledgements

We acknowledge support from the Canadian federal Genomics Research & Development Initiative (GRDI), Metagenomics-Based Ecosystem Biomonitoring (Ecobiomics) project.

Last updated: July 31, 2020
