# RNA-seq Analysis Code for Immune Checkpoint Study in Humans and Dogs

This repository contains R code associated with the publication: **"Barking Up the Right Tree: Immune Checkpoint Signatures of Human and Dog Cancers"**, preprint DOI: [https://doi.org/10.1101/2024.06.26.600825](https://doi.org/10.1101/2024.06.26.600825). Currently in review at *PLOS Computational Biology*.

## Overview

This code starts from quantified RNA-seq count data in TSV format and performs normalization (using DESeq2) and downstream analyses. The raw RNA-seq files were obtained from public datasets, with sources and processing described in the manuscript. Code is structured as a single `.Rmd` file, organized into chunks. The analysis was developed early in my PhD using R, and I did not use containerization at that time (like renv). Care was taken to ensure the code runs, but R can break across systems and versions. If the code is useful for you but does not run on your setup, feel free to reach out - I’m happy to help.

## Directory Structure

```
project-root/
├── Analysis.Rmd              # Main R Markdown analysis script
├── BarkingUpTree.Rproj       # RStudio project file
├── INPUT/                    # Kallisto .tsv files and GTF (not tracked by Git)
├── OUTPUT/                   # Output tables and figures (not tracked by Git)
├── README.md                 # Project description and metadata
└── .gitignore                # Ignore rules for Git
```

## How to Run

Clone the repository, obtain the data as described in the next section, open `BarkingUpTree.Rproj` in Rstudio (recommended). Open `Analysis.Rmd`, install the required R packages listed on top of the file, and run it section by section.

## Data

All required input files - including the GTF annotation, raw quantification files from Kallisto, filtered expression matrices from EBI, and marker gene lists - are deposited on Zenodo: [10.5281/zenodo.15463426](https://doi.org/10.5281/zenodo.15463426). To run the R script, copy these files into the `INPUT/` directory.

The DESeq2-processed dataset (`BarkingUpTree_DDS_processed.RData`), which serves as the source for all downstream tables and figures, is also available on Zenodo. It can be loaded directly into R.


## Reproducibility Notes

This analysis was originally developed under Windows 10 (R 4.2.3) using RStudio 2022.07.0. However, the current version of the code was rerun on Linux Mint 22.1 (R 4.3.3) with RStudio 2025.05.0 and the current release of all packages.
