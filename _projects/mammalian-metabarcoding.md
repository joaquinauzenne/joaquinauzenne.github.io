---
layout: project
order: 1
title: "Mammalian Metabarcoding & Species-Range Visualization Platform"
org: "DiFiore Lab · UT Austin · Dec 2024–Present"
desc: "83 soil samples and ~6M Nanopore reads turned into mammalian species calls, then layered onto ArcGIS range data for researchers and the public."
tags: [eDNA, ONT MinION, Bash, megaBLAST, ArcGIS, Conservation]
---

## Overview

My senior honors thesis in the DiFiore Lab, in two tightly coupled parts: a **computational pipeline** that processes raw Nanopore sequencing data from 83 environmental soil samples (~6 million reads) into reliable mammalian species identifications, and an **interactive visualization platform** that makes those results accessible to both scientific and public audiences.

## Approach

**Pipeline — end-to-end Nanopore processing:**

- Collected environmental DNA (eDNA) soil samples from field sites across the Magdalena River Valley drainage basin, Colombia.
- Ran preprocessing and QC: adapter trimming (Cutadapt), quality filtering (NanoFilt), and run-level QC reporting (MultiQC).
- Performed consensus clustering via NGSpeciesID to correct random ONT base-call errors, achieving **>99% consensus accuracy** across 12S and 16S rRNA marker regions.
- Assigned taxonomy via megaBLAST against a custom mammalian reference library, with species identification and conservation status lookup through the GBIF Metabarcoding Data Toolkit API, NCBI, and IUCN.
- Built a multi-audience web application layering sequencing results onto ArcGIS-hosted species distribution data, with separate views for researchers and the general public.

## Key results

- Processed **83 soil samples** and **~6 million raw Nanopore reads** through a fully automated end-to-end pipeline.
- Achieved **>99% consensus accuracy** using NGSpeciesID-based clustering on 12S/16S rRNA amplicons.
- Identified mammalian taxa including several species of conservation concern in the Magdalena Valley.
- Demonstrated the full arc: raw ONT reads → consensus sequences → taxonomic assignments → interactive visualization.

## Tools & methods

- **ONT MinION / Nanopore** — long-read sequencing platform
- **Cutadapt, NanoFilt, MultiQC** — adapter trimming, quality filtering, QC reporting
- **NGSpeciesID** — consensus clustering for ONT error correction
- **megaBLAST / NCBI** — taxonomic identification from consensus sequences
- **GBIF Metabarcoding Data Toolkit API** — species occurrence and range data integration
- **IUCN** — conservation status lookup
- **ArcGIS** — geospatial species-range data and map layers
- **Bash / Shell** — pipeline automation and HPC job submission (SLURM)
