---
title: "Unified eDNA Metabarcoding Pipeline (Magdalena River Valley)"
excerpt: "End-to-end mammalian eDNA metabarcoding pipeline for Nanopore MinION data (83 soil samples, ~6M reads), achieving >99% consensus accuracy through automated ONT error correction. Senior thesis project at UT Austin.<br/>"
collection: portfolio
---

## Overview

This project serves as my senior honors thesis at the University of Texas at Austin, conducted in the DiFiore Lab (Dec 2024 – Present). It addresses a key challenge in conservation genomics: processing large volumes of noisy Oxford Nanopore sequencing data from environmental soil samples to reliably identify mammalian species.

## Problem

Oxford Nanopore Technology (ONT) sequencing produces high-throughput data but is susceptible to random base-call errors (~5–15% raw error rate). For environmental DNA (eDNA) metabarcoding — where you are identifying species from trace DNA in soil — this noise must be corrected to achieve reliable taxonomic assignments.

## Solution

A consolidated **Bash-scripted pipeline** implementing full end-to-end processing:

1. **Preprocessing & QC** — Adapter trimming, quality filtering (Cutadapt, NanoFilt)
2. **Consensus Clustering** — NGSpeciesID-based clustering to correct random ONT errors, achieving **>99% consensus accuracy**
3. **Taxonomic Assignment** — BLAST-based assignment against a custom reference library (12S, 16S rRNA markers)
4. **Database Integration** — GBIF, NCBI, and IUCN for species identification and IUCN conservation status
5. **Visualization** — ArcGIS for species range mapping across the Magdalena River corridor in Colombia

## Scale

- **83** soil samples from the Magdalena River Valley, Colombia
- **~6 million** raw Nanopore reads processed
- Custom DNA reference library established for Magdalena River mammals

## Skills & Tools

`Bash / Shell` `ONT MinION` `NGSpeciesID` `Cutadapt` `BLAST` `NCBI` `GBIF` `IUCN` `ArcGIS` `eDNA` `Conservation Genomics`
