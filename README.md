# pribilof-pollock

> Code is always in development  
>  
> This document is for informational purposes only and does not necessarily represent the views or official position of the Department of Commerce, the National Oceanic and Atmospheric Administration, or the National Marine Fisheries Service.

---

## Maintainers

This code is primarily maintained by:

- **Sophia Wassermann**

Alaska Fisheries Science Center  
National Marine Fisheries Service  
National Oceanic and Atmospheric Administration  
Seattle, WA 98195

---

## Overview

This repository contains code to estimate abundance and biomass indices for walleye pollock in the Pribilof Islands using a spatiotemporal index model. The workflow combines haul-level catch data, survey information, and environmental covariates to generate region-specific estimates for pollock within defined distance-based areas around the islands.

The analysis includes both model-based estimates from a delta-gamma spatiotemporal framework and design-based comparisons using the `gapindex` package, with outputs saved for reporting and reproducibility.

---

## Application Structure

The project is organized around a small set of R scripts and supporting directories:

### Core model scripts

- `R/pribs_pollock.R`  
  Fits the primary spatiotemporal index model, builds prediction grids, estimates regional abundance and biomass, and writes index outputs and diagnostic plots.

- `R/design_based.R`  
  Pulls design-based biomass and abundance estimates from the `gapindex` package and compares them with model-based results.

- `R/pollock_data_pull.R`  
  Downloads or prepares the pollock data used in the analysis.

- `R/prib_areas.R`  
  Defines the Pribilof region polygons and associated prediction grids used to calculate local indices.

- `R/compare_kts.R`  
  Compares model outputs across different mesh resolutions or knot settings.

### Supporting project files

- `data/`  
  Stores processed model inputs, CPUE data, and derived datasets used for fitting and prediction.

- `shapefiles/`  
  Contains geospatial data and mesh files used to define survey areas and prediction grids.

- `results/`  
  Folder for model output, diagnostics, index tables, and summary figures.

- `pribilof-pollock.Rproj`  
  RStudio project file for working on the project in a consistent environment.

### General workflow

- Prepare survey and environmental covariate data  
- Define Pribilof region polygons and prediction grids  
- Fit the spatiotemporal abundance model  
- Estimate abundance and biomass for each area and year  
- Compare model-based outputs with design-based estimates  
- Save output products for reporting and reproducibility

---

# NOAA README

This repository is a scientific product and is not official communication of the National Oceanic and Atmospheric Administration, or the United States Department of Commerce. All NOAA GitHub project content is provided on an “as is” basis and the user assumes responsibility for its use. Any claims against the Department of Commerce or Department of Commerce bureaus arising from the use of this GitHub project will be governed by all applicable Federal law.

Any reference to specific commercial products, processes, or services by service mark, trademark, manufacturer, or otherwise, does not constitute or imply their endorsement, recommendation or favoring by the United States Government, Department of Commerce, or National Oceanic and Atmospheric Administration.

---

# NOAA License

Software code created by U.S. Government employees is not subject to copyright in the United States (17 U.S.C. §105).

The United States/Department of Commerce reserve all rights to seek and obtain copyright protection in countries other than the United States for Software authored in its entirety by the Department of Commerce employees, or for those portions of the work copied from foreign works. The Department of Commerce reserves the right to restrict or remove content from this repository that is not in compliance with those terms.

---

<img src="https://raw.githubusercontent.com/nmfs-general-modeling-tools/nmfspalette/main/man/figures/noaa-fisheries-rgb-2line-horizontal-small.png" height="75" alt="NOAA Fisheries">

[U.S. Department of Commerce](https://www.commerce.gov/) |  
[National Oceanographic and Atmospheric Administration](https://www.noaa.gov) |  
[NOAA Fisheries](https://www.fisheries.noaa.gov/)
