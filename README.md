---
title: "Sandbox Test Repository"
author: "Your Name"
date: "`r Sys.Date()`"
output: github_document
---

<!-- README.md is generated from README.Rmd. Please edit that file -->

```{r setup, include = FALSE}
knitr::opts_chunk_opts$set(
  collapse = TRUE,
  comment = "#>",
  fig.path = "man/figures/README-",
  out.width = "100%"
)
library(ggplot2)
library(dplyr)
```

# Sandbox Test Repository

<!-- badges: start -->
[![R-CMD-check](https://img.shields.io/badge/Status-Experimental-orange.svg)](https://github.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
<!-- badges: end -->

## Overview

Welcome to the **Sandbox Test Repository**! This repository serves as an experimental playground for testing R analytical pipelines, prototyping interactive data visualizations, and verifying GitHub Markdown document generation.

> **Note:** This is a test environment. Code structures and workflows contained here are subject to frequent experimentation.

---

## Features & Objectives

*   **Pipeline Testing:** Sandbox for testing data transformation and cleanup scripts using `tidyverse`.
*   **Dynamic Visualizations:** Automated generation of inline plots knitted directly to GitHub-ready markdown.
*   **R Markdown Integration:** Testing automated `.Rmd` $\rightarrow$ `.md` compilation workflows via `knitr`.

---

## Quick Start Example

Below is a quick demonstration of inline R code execution and data summary rendering within this document:

```{r summary-table}
# Quick dataset overview
mtcars %>%
  group_by(cyl) %>%
  summarise(
    Avg_MPG = mean(mpg, na.rm = TRUE),
    Avg_HP  = mean(hp, na.rm = TRUE),
    Count   = n()
  ) %>%
  knitr::kable(caption = "Summary Metrics by Cylinder Class")
```

### Visualizing Results

The code chunk below generates a figure that is automatically saved to `man/figures/` and linked dynamically in the final rendered `README.md`:

```{r sample-plot, dev='png'}
# Scatter plot demonstration
ggplot(mtcars, aes(x = wt, y = mpg, color = factor(cyl))) +
  geom_point(size = 3.5, alpha = 0.8) +
  geom_smooth(method = "lm", se = FALSE, linetype = "dashed") +
  scale_color_brewer(palette = "Set1", name = "Cylinders") +
  labs(
    title = "Vehicle Weight vs. Fuel Efficiency",
    subtitle = "Sample diagnostic visualization generated in R Markdown",
    x = "Weight (1,000 lbs)",
    y = "Miles Per Gallon (MPG)"
  ) +
  theme_minimal()
```

---

## Repository Structure

| Directory / File | Description |
| :--- | :--- |
| `README.Rmd` | Source document containing dynamic R code chunks |
| `README.md` | Compiled markdown file rendered for GitHub display |
| `R/` | Folder containing auxiliary helper functions |
| `data/` | Raw and processed test datasets |
| `man/figures/` | Rendered plots linked within the documentation |

---
