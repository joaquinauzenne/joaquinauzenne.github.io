---
layout: project
title: "IdMiner — Bioinformatic Literature Search Tool"
org: "FRI EvoDevOmics · UT Austin · 2022"
desc: "Co-developed a Python-based academic literature search application querying PubMed and NCBI repositories for gene-associated publications to aid researchers in functional annotation of gene lists at scale."
tags: [Python, PubMed / NCBI, Functional Annotation, Transcriptomics]
---

## Overview

IdMiner automates large-scale literature retrieval for gene functional annotation. Researchers working with long gene lists from RNA-seq or other omics experiments often need to survey the literature for each gene's known functions — a process that is time-consuming when done manually. IdMiner streamlines this by batch-querying PubMed and NCBI programmatically.

## Methods / Approach

- Co-designed the application architecture to accept gene identifier lists (Ensembl IDs, gene symbols, or NCBI accessions) as input.
- Implemented automated queries to the PubMed E-utilities API and NCBI Gene database, retrieving titles, abstracts, and MeSH terms for each gene.
- Built output formatting modules to generate structured TSV/CSV reports and ranked publication summaries sorted by citation count and relevance.
- Integrated basic NLP keyword extraction to surface recurring biological themes across the retrieved literature for a given gene list.

## Key Results

- Reduced per-gene literature survey time from ~5 minutes (manual) to seconds at scale.
- Used internally within the FRI EvoDevOmics stream for functional annotation of differentially expressed genes in transcriptomic analyses.
- Demonstrated utility across gene lists of 100–10,000 entries without performance degradation.

## Tools & Technologies

- **Python** — core application logic, API querying, data parsing
- **Biopython / Entrez** — programmatic access to PubMed and NCBI databases
- **pandas** — data structuring and output report generation
- **NLP (NLTK / regex)** — keyword extraction from abstracts
