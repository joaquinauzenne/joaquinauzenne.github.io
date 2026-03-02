---
layout: project
title: "IdMiner — Bioinformatic Literature Search Tool"
org: "FRI EvoDevOmics · UT Austin · 2022–2023"
desc: "Co-developed a Python-based automated literature mining tool using BeautifulSoup to query PaperBLAST (1M+ papers across PubMed and NCBI) for gene-associated publications, validating 40+ differentially expressed gene annotations in frog embryonic transcriptomics research."
tags: [Python, PaperBLAST, Web Scraping, Functional Annotation, Transcriptomics]
---

## Overview

IdMiner automates large-scale literature retrieval for gene functional annotation, developed to address a core bottleneck in transcriptomics research: manually validating the biological significance of differentially expressed genes is slow, inconsistent, and difficult to scale. The tool was built in collaboration with **Dr. Santiago Radio** of the Departamento de Genomica, Instituto de Investigaciones Biológicas Clemente Estable (IIBCE), in partnership with UT Austin's FRI EvoDevOmics lab.

## Problem

After running differential gene expression analyses (DESeq2, WGCNA), researchers are left with lists of 40+ DEGs that require manual literature review to confirm whether their associated biological process annotations are well-supported in the scientific literature. This process is time-consuming and not reproducible at scale.

## Methods / Approach

- Co-designed the application architecture to accept lists of differentially expressed genes as input (gene symbols or identifiers).
- Implemented automated queries to the **PaperBLAST** database, which indexes 1M+ scientific papers across PubMed, NCBI, and related repositories.
- Used **BeautifulSoup** for HTML parsing to programmatically extract gene-term relationships, relevant abstracts, and biological process annotations from PaperBLAST search results.
- Built output formatting modules to return ranked, structured reports of validated biological process terms supported by the literature.
- Applied to validate **40+ DEGs** from frog embryonic transcriptomics experiments within the FRI EvoDevOmics stream.

## Key Results

- Reduced manual literature review time dramatically for DEG validation workflows — from hours to seconds at scale.
- Validated **40+ differentially expressed genes** from frog embryonic transcriptomics (DESeq2 / WGCNA) analyses.
- Provided reproducible, auditable gene-term annotations across **1M+ indexed scientific papers**.
- Enabled scalable DEG annotation as a standard step in the FRI EvoDevOmics transcriptomics pipeline.

## Tools & Technologies

- **Python** — core application logic, query construction, data parsing
- **BeautifulSoup** — HTML parsing of PaperBLAST search result pages
- **PaperBLAST** — literature database indexing 1M+ papers (PubMed, NCBI, and more)
- **pandas** — structured output report generation
- **DESeq2 / WGCNA** — upstream differential expression workflows that IdMiner was built to support

---

*IdMiner was built as a research tool by Dr. Santiago Radio of the Departamento de Genomica, Instituto de Investigaciones Biológicas Clemente Estable in collaboration with UT Austin's FRI EvoDevOmics lab.*
