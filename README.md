# Jochum-et-al-2025b

The data included here was used in the following publication, accepted for publication in Frontiers (2025):
## Changes in cultivation parameters impact cytochrome P450 gene transcription in HepaRG cells: implications for in vitro toxicological assessments
Kristina Jochum1, Veronika Städele1, Philip Marx-Stoelting1
1 German Federal Institute for Risk Assessment, Department of Pesticides Safety, Berlin, Germany

doi: 10.3389/fphar.2025.1690384

---------------------------------------------------------------------------------------
Briefly, transcriptional changes of 12 major CYP genes, i.e., CYP1A1, 1A2, 27A1, 2B6, 2C19, 2C8, 2C9, 2D6, 2E1, 3A4, 3A5, 8B1, in relation to changes in four cultivation parameters were investigated in HepaRG cells. To this end, HepaRG cells were cultivated according to two different methods (normal-density process: undifferentiated cells are seeded in culture plates and maintained for four weeks to complete differentiation; and high-density process: differentiated cells are seeded in culture plates and maintained for another two weeks to yield functional, differentiated cells) and analyzed by RT-qPCR. Cells were seeded at five densities per cultivation method and mRNA was extracted at two timepoints after completion of differentiation, also comparing extracts from undamaged and intentionally damaged cell monolayers.
This repository contains the obtained data and R file for data anlysis and evaluation using brms.

---------------------------------------------------------------------------------------
## Gene expression data

Contains normalized PCR data; GAPDH and GUSB were used as internal control genes for data normalization; deltaCt was calculted with Excel
For each sample, CTs of two technical replicates were averaged and ΔCT was calculated according to Schmittgen and Livak 2008 by subtracting the mean CT of two control genes from the CT of the gene of interest, thus correcting for PCR variability
biol_rep: independent experiments from 1 to 5
cultivation_method: 0 = normal-density, 1 = high-density
damage: 0 = undamaged; 1 = damaged
cell_amount: seeding cell number (10^6), see Table 1 in main manuscript
timepoint: 0 = 0; 1 = 2
deltaCt:  gene of interest Ct subtracted by the mean Ct of two control genes (see Schmittgen and Livak 2001)
gene: CYP gene (12)

---------------------------------------------------------------------------------------
## R script for data analysis

Contains the R script for performing the data analysis using brms for Bayesian multilevel modelling. 
Student-t distribution-based linear mixed models with ΔCT as the response variable were constructed. Damage, timepoint, cultivation method and cell number were included as fixed effects, and gene identity as a random intercept. Random slopes were included for all fixed effects within gene identity.
More information on statistical approach can be found in the supplementary material along with the main manuscript.

---------------------------------------------------------------------------------------
This project is licensed under the terms of CC-BY-4.0.

[![DOI](https://zenodo.org/badge/1054137728.svg)](https://doi.org/10.5281/zenodo.17380238)
