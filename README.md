# how-body-site-shapes-the-human-microbiome

Diversity and composition across gut, tongue, skin, and palm
BIOL 5340 — Module 12 Project
Authors: Reel Elsadig (1002056688) & Aya Hassan (1002216886)

# Research question

How do bacterial community composition and diversity differ across four human body sites — gut, tongue, skin (cheek), and right palm — within and between individuals over time?
Our hypothesis is that the microbiome differs more by body site than by person or by time, and that quantifying that baseline is what makes disease–microbiome studies interpretable.

# Dataset
Public tutorial data from the QIIME 2 "Moving Pictures" tutorial (QIIME 2 2024.10):
- 2 individuals, 4 body sites, 5 timepoints (first timepoint right after antibiotic use)
- 34 samples
- Single-end Illumina HiSeq reads, Earth Microbiome Project V4 16S rRNA protocol, 515F/806R primers
- Data: https://docs.qiime2.org/2024.10/tutorials/moving-pictures/
- Sample metadata: https://data.qiime2.org/2024.10/tutorials/moving-pictures/sample_metadata.tsv

# Repository contents
File / folder - What it is
- README.md - This file — project overview, pipeline, and usage
- ai_usage.md - How AI tools were used in this project and how outputs were verified
- notebook/- Jupyter notebook with the full QIIME 2 + Python workflow
- figures/ - Taxa bar plots, alpha-diversity box plots, and PCoA plots generated from the notebook
- report/- The project report (draft and final)

# Pipeline
1. Import the demultiplexed sequence data into QIIME 2
2. Demultiplex and inspect sequence quality
3. Denoise with DADA2 → feature table + representative sequences
4. Taxonomy assignment against a 16S reference classifier
5. Alpha diversity — Shannon index, Faith's PD, observed features
6. Beta diversity — Bray–Curtis and UniFrac distances, PCoA plots
7. Group comparisons by body site — PERMANOVA
8. Differential abundance — ANCOM
9. Stretch goal — random forest classifier (scikit-learn) predicting body site from composition

# Requirements
- QIIME 2 (2024.10) installed via conda — install early; the environment is large
- Python 3 with Jupyter, pandas, and scikit-learn (for the classifier)

# Usage
1. Install QIIME 2 following https://docs.qiime2.org/2024.10/install/
2. Download the Moving Pictures data and sample_metadata.tsv from the links above
3. Open the notebook in notebook/ and run it top to bottom — it executes the full pipeline and writes all figures to figures/

# Evaluation
- Diversity differences by body site quantified with PERMANOVA p-values
- Classifier performance measured by accuracy against chance
- Success = the pipeline runs end-to-end reproducibly and all figures regenerate from the notebook

# Timeline
- Week 1: data download, QIIME 2 setup, import / demultiplex / denoise
- Week 2: diversity analyses, ANCOM, classifier
- Week 3: figures, interpretation, finalize notebook + report

# AI use
See ai_usage.md.
