---
layout: project
title: "Mammalian Metabarcoding & Species-Range Visualization Platform"
org: "DiFiore Lab · UT Austin · Dec 2024–Present"
desc: "Developed an interactive web application presenting Nanopore eDNA genomic analyses as user-friendly interfaces for both scientific and public audiences, integrating sequencing results with geospatial species-range data for the Magdalena River Valley."
tags: [eDNA, ONT MinION, Bash, megaBLAST, ArcGIS, Conservation]
---

## Overview

This project is my senior honors thesis at the University of Texas at Austin, conducted in the DiFiore Lab (Dec 2024 – Present). It encompasses two tightly coupled components: a **computational pipeline** that processes raw Nanopore sequencing data from 83 environmental soil samples (~6 million reads) into reliable mammalian species identifications, and an **interactive visualization platform** that makes those results accessible to both scientific and public audiences.

## Methods / Approach

**Pipeline — End-to-end Nanopore processing:**

- Collected environmental DNA (eDNA) soil samples from field sites across the Magdalena River Valley drainage basin, Colombia.
- Ran preprocessing and QC: adapter trimming (Cutadapt), quality filtering (NanoFilt), and run-level QC reporting (MultiQC).
- Performed consensus clustering via NGSpeciesID to correct random ONT base-call errors, achieving **>99% consensus accuracy** across 12S and 16S rRNA marker regions.
- Assigned taxonomy via megaBLAST against a custom mammalian reference library, with species identification and conservation status lookup through the GBIF Metabarcoding Data Toolkit API, NCBI, and IUCN.

**Visualization platform:**

- Developed a multi-audience web application layering sequencing results onto ArcGIS-hosted species distribution data, with separate views optimized for researchers and the general public.
- Platform allows users to explore species detections, geographic distributions, and IUCN conservation status interactively across the Magdalena River Valley corridor.

## Key Results

- Processed **83 soil samples** and **~6 million raw Nanopore reads** through a fully automated end-to-end pipeline.
- Achieved **>99% consensus accuracy** using NGSpeciesID-based clustering on 12S/16S rRNA amplicons.
- Successfully identified mammalian taxa including several species of conservation concern in the Magdalena Valley.
- Platform demonstrates the full arc: raw ONT reads → consensus sequences → taxonomic assignments → interactive visualization, bridging bioinformatic outputs and actionable conservation insight.

## Tools & Technologies

- **ONT MinION / Nanopore** — long-read sequencing platform
- **Cutadapt, NanoFilt, MultiQC** — adapter trimming, quality filtering, QC reporting
- **NGSpeciesID** — consensus clustering for ONT error correction
- **megaBLAST / NCBI** — taxonomic identification from consensus sequences
- **GBIF Metabarcoding Data Toolkit API** — species occurrence and range data integration
- **IUCN** — conservation status lookup
- **ArcGIS** — geospatial species-range data and map layers
- **Bash / Shell** — pipeline automation and HPC job submission (SLURM)
