# riskmetric

[![Travis build status](https://travis-ci.org/pharmaR/riskmetric.svg?branch=master)](https://travis-ci.org/pharmaR/riskmetric)
[![Coverage status](https://codecov.io/gh/pharmaR/riskmetric/branch/master/graph/badge.svg)](https://codecov.io/github/pharmaR/riskmetric?branch=master)
 
`riskmetric` is a collection of risk metrics to evaluate the quality of R
packages.

_This package is in experimentation. Final considerations about design are being
considered, but core concepts are considered final._

## Background

The risk of using an R package is evaluated based on a number of metrics meant
to evaluate development best practices, code documentation, community engagement
and development sustainability. We hope to provide a framework to quantify risk
by assessing these metrics. This package serves as a starting point for
exploring the heterogeneity of code quality, and begin a broader conversation
about the validation of R packages. Primarily, this effort aims to provide some
context for validation within regulated industries.

## Quick Start

### Installation

`riskmetric` is not yet on CRAN. Until it is, install using `devtools`.

```r
devtools::install_github("pharmaR/riskmetric")
```

### Example

Scrape metadata locally or remotely, then assess that metadata and score it to
estimate risk. For each package, derive a composite measure of risk, or a
collection of individual scores which can be easily used to generate validation
reports.

```r
library(dplyr)
library(riskmetric)

pkg_ref(c("riskmetric", "utils", "tools")) %>%
  as_tibble() %>%
  assess() %>%
  score() %>%
  mutate(risk = summarize_risk(.))
```

## Get Involved

`riskmetric` is centrally a community project. Comfort with a quantification of
risk comes via consensus, and for that this project is dependent on close
community engagement. There are plenty of ways to help:

- Share the package
- File [issues](https://github.com/pharmaR/riskmetric/issues) when you encounter bugs
- Weigh in on proposed metrics, or [suggest a new one](https://github.com/pharmaR/riskmetric/issues/new?labels=Metric%20Proposal)
- Help us devise the best way to summarize risk into a single score
- Help us keep documentation up to date
- Contribute code to tackle the metric backlog
