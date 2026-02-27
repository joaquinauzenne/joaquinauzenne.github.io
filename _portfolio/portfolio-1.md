---
title: "Mammalian eDNA Metabarcoding Pipeline & Species-Range Visualization Platform"
excerpt: "End-to-end mammalian eDNA metabarcoding pipeline for Nanopore MinION data (83 soil samples, ~6M reads) achieving >99% consensus accuracy, paired with an interactive web platform presenting sequencing results and geospatial species-range data for the Magdalena River Valley. Senior thesis project at UT Austin.<br/>"
collection: portfolio
---

## Overview

This project is my senior honors thesis at the University of Texas at Austin, conducted in the DiFiore Lab (Dec 2024 – Present). It encompasses two tightly coupled components: a **computational pipeline** that processes raw Nanopore sequencing data from environmental soil samples into reliable mammalian species identifications, and an **interactive visualization platform** that makes those results accessible to both scientific and public audiences.

---

## Part 1: Unified eDNA Metabarcoding Pipeline

### Problem

Oxford Nanopore Technology (ONT) sequencing produces high-throughput data but is susceptible to random base-call errors (~5–15% raw error rate). For environmental DNA (eDNA) metabarcoding — where species are identified from trace DNA in soil — this noise must be corrected to achieve reliable taxonomic assignments.

### Solution

A consolidated **Bash-scripted pipeline** implementing full end-to-end processing:

1. **Preprocessing & QC** — Adapter trimming, quality filtering (Cutadapt, NanoFilt, MultiQC)
2. **Consensus Clustering** — NGSpeciesID-based clustering to correct random ONT errors, achieving **>99% consensus accuracy**
3. **Taxonomic Assignment** — megaBLAST-based assignment against a custom reference library (12S, 16S rRNA markers)
4. **Database Integration** — GBIF Metabarcoding Data Toolkit API, NCBI, and IUCN for species identification and conservation status
5. **Output** — Consensus sequences ready for longitudinal population and dispersal analyses

### Scale

- **83** soil samples from the Magdalena River Valley, Colombia
- **~6 million** raw Nanopore reads processed
- Custom DNA reference library established for mammals along the Magdalena River

---

## Part 2: Species-Range Visualization Platform

### Problem

Raw metabarcoding outputs — taxonomic assignment tables, BLAST results, and species occurrence records — are not interpretable by non-computational audiences. Conservation decisions and public engagement require accessible, interactive interfaces.

### Solution

An interactive web application that:
- Presents Nanopore eDNA genomic analyses through clean, navigable interfaces for both scientific and lay audiences
- Integrates sequencing results directly with **geospatial species-range data** via ArcGIS for the Magdalena River Valley corridor
- Allows users to explore species detections, geographic distributions, and IUCN conservation status interactively
- Bridges the gap between raw bioinformatic outputs and actionable conservation insight

### Impact

- Makes eDNA biodiversity data from the Magdalena River accessible beyond the research lab
- Supports both scientific peer review and public science communication
- Demonstrates the full arc: raw ONT reads → consensus sequences → taxonomic assignments → interactive visualization

---

## Skills & Tools

`Bash / Shell` `ONT MinION` `NGSpeciesID` `Cutadapt` `MultiQC` `megaBLAST` `NCBI` `GBIF API` `IUCN` `ArcGIS` `Python` `Geospatial Analysis` `Data Visualization` `eDNA` `Conservation Genomics` `Science Communication`
