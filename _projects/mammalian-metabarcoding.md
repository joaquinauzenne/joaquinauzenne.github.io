---
layout: project
title: "Mammalian Metabarcoding & Species-Range Visualization Platform"
org: "DiFiore Lab · UT Austin · Dec 2024–Present"
desc: "Developed an interactive web application presenting Nanopore eDNA genomic analyses as user-friendly interfaces for both scientific and public audiences, integrating sequencing results with geospatial species-range data for the Magdalena River Valley."
tags: [eDNA, ONT MinION, Bash, megaBLAST, ArcGIS, Conservation]
---

## Overview

This ongoing project builds a public-facing and scientifically rigorous web platform for communicating eDNA-based mammalian biodiversity assessments in the Magdalena River Valley (Colombia). The platform bridges raw Nanopore sequencing data and interactive geospatial visualizations accessible to non-specialists.

## Methods / Approach

- Collected environmental DNA (eDNA) water samples from field sites across the Magdalena River Valley drainage basin.
- Processed raw ONT MinION reads using NanoPlot (QC), Cutadapt (adapter trimming), and NGSpeciesID (consensus clustering and species identification).
- Performed taxonomic assignment via megaBLAST against curated NCBI reference databases.
- Developed a multi-audience web application layering sequencing results onto ArcGIS-hosted species distribution data, with separate views optimized for researchers and the general public.

## Key Results

- Successfully identified mammalian taxa from eDNA samples including several species of conservation concern in the Magdalena Valley.
- Platform supports real-time update of sequencing results as new field collections are processed.
- Geospatial overlays enable rapid cross-referencing of detected taxa against known range maps and IUCN status data.

## Tools & Technologies

- **ONT MinION / Nanopore** — long-read sequencing platform
- **NanoPlot, Cutadapt, NGSpeciesID** — QC, trimming, and species-level consensus calling
- **megaBLAST / NCBI** — taxonomic identification from consensus sequences
- **ArcGIS** — geospatial species-range data and map layers
- **Bash / Shell** — pipeline automation and HPC job submission (SLURM)
- **Web application** — interactive front-end for public and scientific audiences
