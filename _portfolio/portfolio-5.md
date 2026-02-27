---
title: "IdMiner: Automated Scientific Literature Mining Tool"
excerpt: "A Python-based tool using BeautifulSoup to automate searches across 1M+ scientific papers in PaperBLAST (PubMed, NCBI), validating gene-term relationships for differentially expressed gene lists.<br/>"
collection: portfolio
---

## Overview

Developed during my time at FRI EvoDevOmics, University of Texas at Austin (2022–2023) to address a core bottleneck in transcriptomics research: manually validating the biological significance of dozens of differentially expressed genes is slow, inconsistent, and difficult to scale.

## Problem

After running differential gene expression analyses (DESeq2, WGCNA), researchers are left with lists of 40+ DEGs that require manual literature review to confirm whether their associated biological process annotations are well-supported in the scientific literature. This process is time-consuming and not reproducible at scale.

## Solution

**IdMiner** automates this workflow end-to-end:

1. Takes a list of differentially expressed genes as input
2. Queries the **PaperBLAST** database (which indexes PubMed, NCBI, and other repositories) programmatically
3. Uses **BeautifulSoup** for HTML parsing to extract relevant gene-term relationships from paper abstracts and metadata
4. Returns a ranked, structured output of validated biological process terms supported by the literature — across 1M+ indexed scientific papers

## Impact

- Reduced manual literature review time dramatically for DEG validation workflows
- Provided reproducible, auditable gene-term annotation for downstream pathway analysis
- Applied to validate 40+ DEGs from frog embryonic transcriptomics experiments

## Skills & Tools

`Python` `BeautifulSoup` `PaperBLAST` `PubMed` `NCBI` `Web Scraping` `Bioinformatics` `Transcriptomics` `Automation`

---

*IdMiner was built as a research tool at UT Austin's FRI EvoDevOmics lab. Contact me if you're interested in the codebase or methodology.*
