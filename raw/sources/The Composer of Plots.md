---
title: "The Composer of Plots"
source: "https://patchwork.data-imaginist.com/"
author:
published:
created: 2026-04-30
description: "The ggplot2 package provides a strong API for sequentially building up a plot, but does not concern itself with composition of multiple plots. patchwork is a package that expands the API to allow for arbitrarily complex composition of plots by, among others, providing mathematical operators for combining multiple plots. Other packages that try to address this need (but with a different approach) are gridExtra and cowplot."
tags:
  - "clippings"
---
The goal of `patchwork` is to make it ridiculously simple to combine separate ggplots into the same graphic. As such it tries to solve the same problem as `gridExtra::grid.arrange()` and `cowplot::plot_grid` but using an API that incites exploration and iteration, and scales to arbitrarily complex layouts.

## Installation

You can install patchwork from CRAN using `install.packages('patchwork')`. Alternatively you can grab the development version from github using devtools:

```
# install.packages("devtools")
devtools::install_github("thomasp85/patchwork")
```

## Basic example

The usage of `patchwork` is simple: just add plots together!

```
library(ggplot2)
library(patchwork)

p1 <- ggplot(mtcars) + geom_point(aes(mpg, disp))
p2 <- ggplot(mtcars) + geom_boxplot(aes(gear, disp, group = gear))

p1 + p2
```

![](https://patchwork.data-imaginist.com/reference/figures/README-example-1.png)

patchwork provides rich support for arbitrarily complex layouts with full alignment. As an example, check out this very readable code for nesting three plots on top of a third:

```
p3 <- ggplot(mtcars) + geom_smooth(aes(disp, qsec))
p4 <- ggplot(mtcars) + geom_bar(aes(carb))

(p1 | p2 | p3) /
      p4
```

![](https://patchwork.data-imaginist.com/reference/figures/README-unnamed-chunk-2-1.png)

## Learn more

patchwork can do so much more. Check out the guides for learning everything there is to know about all the different features:

- [Getting Started](https://patchwork.data-imaginist.com/articles/patchwork.html)
- [Assembling Plots](https://patchwork.data-imaginist.com/articles/guides/assembly.html)
- [Defining Layouts](https://patchwork.data-imaginist.com/articles/guides/layout.html)
- [Adding Annotation](https://patchwork.data-imaginist.com/articles/guides/annotation.html)
- [Aligning across pages](https://patchwork.data-imaginist.com/articles/guides/multipage.html)

## Code of Conduct

Please note that the patchwork project is released with a [Contributor Code of Conduct](https://patchwork.data-imaginist.com/CODE_OF_CONDUCT.html). By contributing to this project, you agree to abide by its terms.