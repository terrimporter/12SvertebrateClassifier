# 12S Vertebrate Reference Set For The RDP Classifier 

[![DOI](https://zenodo.org/badge/391459819.svg)](https://zenodo.org/badge/latestdoi/391459819)  

This repository contains trained reference sets that can be used with the Ribosomal Database Project classifier (Wang et al., 2007) to taxonomically assign vertebrate 12S mitochondrial gene sequences.  The latest releases can be downloaded from https://github.com/terrimporter/12SvertebrateClassifier/releases

This classifier is suitable for classifying vertebrate 12S mitochondrial gene sequences to species rank.  Reference sequences were obtained from the NCBI nucleotide [accessed July 2021] and MitoFish [accessed March 2020].  Taxonomy is based on the NCBI taxonomy database.

## How to cite

You can cite this repository directly:  
Teresita M. Porter. (2021). terrimporter/12SvertebrateClassifier: 12S Vertebrate Classifier v2.0.0. Zenodo. https://zenodo.org/badge/latestdoi/391459819   

If you use a version of the classifier that contains sequences from MitoFish please also cite:
Sato, Y., Miya, M., Fukunaga, T., Sado, T., Iwasaki, W., Kumar, S. (2018) MitoFish and MiFish Pipeline: A mitochondrial genome database of fish with an analysis pipeline for environmental DNA metabarcoding. Molecular Biology and Evolution, 35: 1553.

If you use this reference set with the RDP classifier please also cite the naive Bayesian classification tool:  
Wang et al. (2007) Naïve Bayesian classifier for rapid assignment of rRNA sequences into the new bacterial taxonomy. Applied and Environmental Microbiology, 73: 5261.

## How to use

Decompress the tar.gz file:

$ tar -xvzf FileName.tar.gz

Use with the RDP classifier:

java -Xmx8g -jar /path/to/rdp_classifier_2.13/dist/classifier.jar classify -t /path/to/mydata_trained/rRNAClassifier.properties -o ClassifiedQueryFilename QueryFilename

# Releases

### v3.0.0 North American Reference Set \*\*NEW\*\*

This version was created from the NCBI nucleotide database [accessed March 9, 2023].  This version contains 3,706 reference sequences, 4,007 taxa in total including 1,868 species.  Set was filtered only include sequences at least 500bp+, sequences with no ambiguous bases, and records with Linnean binomial species names.  Non-vertebrate outgroup sequences were added.  Sequences were checked for human and non-vertebrate contaminants.  *This version of the database only includes GenBank records from North America.*  For a reference set that includes global species, use v2.0.0.  

### v2.0.0

These files are ready to be used with the RDP Classifier.  Created from the NCBI nucleotide database [accessed July 26, 2020].  Added additional 12S sequences from the 12S fish classifier available from https://github.com/terrimporter/12SfishClassifier that includes sequences from MitoFish [March 2020].  This version contains 19,654 reference sequences and 15,007 taxa at all ranks, including 9,564 species.  This version of the classifier is recommended if there is a needed emphasis on fish, otherwise v1.0.0 classification performance is slightly better with lower bootstrap support cutoffs needed to ensure accuracy.

### v2.0.0-ref

These files were used to train the RDP Classifier.  Provided here for reference only.  Includes a FASTA file and a taxonomy file.

#### Bootstrap support cutoffs, 99% accuracy:

Rank | 500 bp+ | 400 bp | 300 bp | 200 bp | 100 bp
--- |:---:|:---:|:---:|:---:|:---:
Superkingdom | 0 | 0 | 0 | 0 | 0
Kingdom | 0 | 0 | 0 | 0 | 0
Phylum | 0 | 0 | 0 | 0 | 0
Class | 0 | 0 | 0 | 0 | 20 
Order | 10 | 20 | 30 | 30 | 40 
Family | 50 | 50 | 50 | 50 | 50 
Genus | NA | NA | NA | NA | 95 
Species * | NA | NA | NA | NA | NA 

NA = No cutoff available will result in 99% correct assignments

#### Bootstrap support cutoffs, 95% accuracy:

Rank | Full | 400 bp | 300 bp | 200 bp | 100 bp
--- |:---:|:---:|:---:|:---:|:---:
Superkingdom | 0 | 0 | 0 | 0 | 0
Kingdom | 0 | 0 | 0 | 0 | 0
Phylum | 0 | 0 | 0 | 0 | 0
Class | 0 | 0 | 0 | 0 | 0
Order | 0 | 0 | 0 | 0 | 0 
Family | 0 | 0 | 0 | 0 | 10 
Genus | 30 | 40 | 40 | 40 | 50 
Species * | NA | NA | 95 | 95 | NA 

NA = No cutoff available will result in 95% correct assignments

#### Bootstrap support cutoffs, 90% accuracy:

Rank | Full | 400 bp | 300 bp | 200 bp | 100 bp
--- |:---:|:---:|:---:|:---:|:---:
Superkingdom | 0 | 0 | 0 | 0 | 0
Kingdom | 0 | 0 | 0 | 0 | 0
Phylum | 0 | 0 | 0 | 0 | 0
Class | 0 | 0 | 0 | 0 | 0
Order | 0 | 0 | 0 | 0 | 0 
Family | 0 | 0 | 0 | 0 | 0 
Genus | 0 | 0 | 0 | 0 | 20 
Species * | 60 | 60 | 60 | 60 | 80  

### v1.0.0

These files are ready to be used with the RDP Classifier.  Created from the NCBI nucleotide database [accessed July 26, 2020].  This version contains 16,801 reference sequences and 11,633 taxa at all ranks, including 7,277 species.

### v1.0.0-ref

These files were used to train the RDP Classifier.  Provided here for reference only.  Includes a FASTA file and a taxonomy file.

**Taxonomic assignment results should be filtered according to their bootstrap support values to reduce false positive assignments.**  Cutoffs are based on leave-one-sequence-out testing of non-singleton species. Here we recommend MINIMUM bootstrap cutoffs according to query length and assignment rank.  Assuming your query sequences are represented in the reference set, using the cutoffs presented in the first table below should ensure 99% accuracy.  If you wish to cast a wider net, you can use the second tables below for 95% or 90% accuracy.

#### Bootstrap support cutoffs, 99% accuracy:

Rank | 500 bp+ | 400 bp | 300 bp | 200 bp | 100 bp
--- |:---:|:---:|:---:|:---:|:---:
Superkingdom | 0 | 0 | 0 | 0 | 0
Kingdom | 0 | 0 | 0 | 0 | 0
Phylum | 0 | 0 | 0 | 0 | 0
Class | 0 | 0 | 0 | 0 | 20 
Order | 20 | 20 | 30 | 30 | 30 
Family | 50 | 40 | 50 | 50 | 50 
Genus | 95 | 90 | 90 | 90 | 90 
Species * | NA | NA | NA | NA | NA 

NA = No cutoff available will result in 99% correct assignments

#### Bootstrap support cutoffs, 95% accuracy:

Rank | Full | 400 bp | 300 bp | 200 bp | 100 bp
--- |:---:|:---:|:---:|:---:|:---:
Superkingdom | 0 | 0 | 0 | 0 | 0
Kingdom | 0 | 0 | 0 | 0 | 0
Phylum | 0 | 0 | 0 | 0 | 0
Class | 0 | 0 | 0 | 0 | 0
Order | 0 | 0 | 0 | 0 | 0 
Family | 0 | 0 | 0 | 0 | 10 
Genus | 0 | 0 | 0 | 20 | 30 
Species * | 95 | 90 | 90 | 95 | NA 

NA = No cutoff available will result in 95% correct assignments

#### Bootstrap support cutoffs, 90% accuracy:

Rank | Full | 400 bp | 300 bp | 200 bp | 100 bp
--- |:---:|:---:|:---:|:---:|:---:
Superkingdom | 0 | 0 | 0 | 0 | 0
Kingdom | 0 | 0 | 0 | 0 | 0
Phylum | 0 | 0 | 0 | 0 | 0
Class | 0 | 0 | 0 | 0 | 0
Order | 0 | 0 | 0 | 0 | 0 
Family | 0 | 0 | 0 | 0 | 0 
Genus | 0 | 0 | 0 | 0 | 0 
Species * | 20 | 40 | 50 | 50 | 70  

# References

Sato, Y., Miya, M., Fukunaga, T., Sado, T., Iwasaki, W., Kumar, S. (2018) MitoFish and MiFish Pipeline: A mitochondrial genome database of fish with an analysis pipeline for environmental DNA metabarcoding. Molecular Biology and Evolution, 35: 1553.

Wang, Q., Garrity, G. M., Tiedje, J. M., & Cole, J. R. (2007). Naive Bayesian Classifier for Rapid Assignment of rRNA Sequences into the New Bacterial Taxonomy. Applied and Environmental Microbiology, 73(16), 5261–5267. Available from https://sourceforge.net/projects/rdp-classifier/

# Acknowledgements

We acknowledge support from the Canadian federal Genomics Research & Development Initiative (GRDI), Metagenomics-Based Ecosystem Biomonitoring (Ecobiomics) project.

Last updated: May 2, 2023
