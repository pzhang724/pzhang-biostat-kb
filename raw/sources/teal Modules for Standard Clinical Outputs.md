---
title: "teal Modules for Standard Clinical Outputs"
source: "https://insightsengineering.github.io/teal.modules.clinical/latest-tag/"
author:
published:
created: 2026-04-30
description: "Provides user-friendly tools for creating and customizing clinical trial reports. By leveraging the teal framework, this package provides teal modules to easily create an interactive panel that allows for seamless adjustments to data presentation, thereby streamlining the creation of detailed and accurate reports."
tags:
  - "clippings"
---
![GitHub last commit](https://img.shields.io/github/last-commit/insightsengineering/teal.modules.clinical)

This package contains a set of standard `teal` modules to be used with `CDISC` data in order to generate many of the standard outputs used in clinical trials.

These modules include, but are not limited to:

- Data visualizations:
- Statistical model fits:
- Summary tables:
- Patient-level profile modules:
	- Table of basic information about chosen patient (`tm_t_pp_basic_info()`)
		- Plot of patient vitals over time (`tm_g_pp_vitals()`)
		- General timeline for individual patients (`tm_g_pp_patient_timeline()`)
		- …

Most modules in the package are implemented using functions from the R package [`tern`](https://insightsengineering.github.io/tern/) in order to produce their output.

Please see the [Teal Gallery](https://insightsengineering.github.io/teal.gallery/) and [TLG Catalog](https://insightsengineering.github.io/tlg-catalog/) for examples of `shiny` apps created using modules from this package.

## Installation

```
install.packages('teal.modules.clinical')
```

Alternatively, you might want to use the development version.

```
# install.packages("pak")
pak::pak("insightsengineering/teal.modules.clinical")
```

## Usage

To understand how to use this package, please refer to the [Getting Started](https://insightsengineering.github.io/teal.modules.clinical/latest-tag/articles/teal-modules-clinical.html) article, which provides multiple examples of code implementation.

## Playground

You can try out the package without installing it in the Shinylive:

- [stable](https://shinylive.io/r/editor/#code=NobwRAdghgtgpmAXGKAHVA6ASmANGAYwHsIAXOMpMAGwEsAjAJykYE8AKcqajGIgEwCu1OAGcMBOhFoFuASgA6EMAF8AukA)
- [development](https://shinylive.io/r/editor/#code=NobwRAdghgtgpmAXGKAHVA6ASmANGAYwHsIAXOMpMI1UgSxIGcAKAdzgCMAnAfVQGsA5jy5xURRgAIAvJILMAOmC4BaAK4Q6ANzhdGcJTMlKAFqVKpGiAPTXUJqFxhQdeuBlUbtu-RgAmcFpKuJKCcKQA8rQMEIpg7Nx8QiJiEkoAlJkKEAA2dNyOAJ7M5FA5GDBEfmo5cIwYBHmaBGXp2WAAvgC6QA)

## Getting help

If you encounter a bug or have a feature request, please file an issue. For questions, discussions, and staying up to date, please use the `teal` channel in the [`pharmaverse` slack workspace](https://pharmaverse.slack.com/).

## Acknowledgment

This package is the result of the joint efforts of many developers and stakeholders. We would like to thank everyone who has contributed so far!