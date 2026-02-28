---
layout: project
title: "COVID-19 Spatiotemporal Network Dynamics"
org: "Dept. of Integrative Biology · UT Austin · Oct–Dec 2024"
desc: "Built spatial network time-series models of U.S. COVID-19 spread (32M cases, Apr 2020–Apr 2021) with R/Shiny interactive maps, dashboards, and weighted network centrality statistics to identify transmission hubs and inform public health intervention strategies."
tags: [R / Shiny, Network Analysis, Time Series, Epidemiology]
---

## Overview

This project modeled the spatiotemporal dynamics of U.S. COVID-19 transmission using a weighted network framework applied to county-level case data. The goal was to identify transmission hubs and characterize how disease spread evolved across geographic regions over time.

## Methods / Approach

- Assembled and cleaned a dataset of ~32 million U.S. COVID-19 cases (April 2020–April 2021) sourced from the New York Times county-level repository.
- Constructed temporal network graphs where nodes represent U.S. counties and edge weights encode normalized case-flow between adjacent regions across weekly time windows.
- Computed weighted network centrality statistics (degree, betweenness, eigenvector centrality) to rank counties by their role in facilitating spread.
- Built an interactive R/Shiny dashboard with animated choropleth maps and centrality timelines, enabling exploration of transmission dynamics by week and region.

## Key Results

- Identified persistent super-spreader hubs in major metropolitan corridors (NYC, LA, Chicago) that drove early national spread.
- Detected a secondary wave of hub emergence in rural Midwest counties during fall 2020, reflecting shifts in mobility and mitigation policy.
- Network centrality metrics preceded case-count peaks by 1–2 weeks in several regions, suggesting utility as an early warning signal.

## Tools & Technologies

- **R** — data wrangling (`dplyr`, `tidyr`), network construction (`igraph`), statistical modeling
- **Shiny** — interactive dashboard with animated maps and timeline controls
- **ggplot2 / leaflet** — visualization layers for choropleth and network overlays
- **SARIMA** — time-series decomposition to isolate trend from seasonal noise
