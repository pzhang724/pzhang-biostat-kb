---
title: "GSWEP4R Workshop - 3 An R Package Engineering Workflow"
source: "https://openpharma.github.io/workshop-r-swe-mtl/slides/03_workflow.html#/title-slide"
author:
  - "[[Daniel]]"
published: 2023-10-15
created: 2026-04-29
description:
tags:
  - "clippings"
---
## 3 An R Package Engineering Workflow

`openstatsware` Workshop: Good Software Engineering Practice for R Packages

## Motivation

**From an idea to a production-grade R package**

Example scenario: in your daily work, you notice that you need certain one-off scripts again and again.

The idea of creating an R package was born because you understood that “copy and paste” R scripts is inefficient, and on top of that, you want to share your helpful R functions with colleagues and the world…

## Professional Workflow

![](https://openpharma.github.io/workshop-r-swe-mtl/slides/thumbnails/workflow1.jpg)

## Typical work steps

1. Idea
2. Concept creation
3. Validation planning
4. Specification:
	1. User Requirements Spec (URS),
		2. Functional Spec (FS), and
		3. Software Design Spec (SDS)

5. R package programming
6. Documented verification
7. Completion of formal validation
8. R package release
9. Use in production
10. Maintenance

## Workflow in Practice

![](https://openpharma.github.io/workshop-r-swe-mtl/slides/thumbnails/workflow2.jpg)

## Frequently Used Workflow in Practice

1. Idea
2. R package programming
3. Use in production
4. Bug fixing
5. Use in production

6. Bug fixing + Documentation
7. Use in production
8. Bug fixing + Further development
9. Use in production
10. Bug fixing + …

Bad practice!

Why?

## Why practice good engineering?

Cost distribution among software process activities

![](https://openpharma.github.io/workshop-r-swe-mtl/slides/03_workflow_files/figure-revealjs/unnamed-chunk-1-1.png)

[doi:10.14569/IJACSA.2020.0110375](https://dx.doi.org/10.14569/IJACSA.2020.0110375)

## Why practice good engineering?

Origin of errors in system development

![](https://openpharma.github.io/workshop-r-swe-mtl/slides/03_workflow_files/figure-revealjs/unnamed-chunk-2-1.png)

[Boehm, B. (1981). Software Engineering Economics. Prentice Hall.](https://dl.acm.org/doi/10.5555/539425)

## Why practice good engineering?

- Don’t waste time on maintenance
- Be faster with release on CRAN
- Don’t waste time with inefficient and buggy further development

- Fulfill regulatory requirements <sup>1</sup>
- Save refactoring time when the Proof-of-Concept (*PoC*) becomes the release version
- You don’t have to be shy any longer about inviting other developers to contribute to the package on [GitHub](https://github.com/)

## Why practice good engineering?

Invest time in

- requirements analysis,
- software design, and
- architecture…

… but in many cases the workflow must be workable for a single developer or a small team.

## Workable Workflow

![](https://openpharma.github.io/workshop-r-swe-mtl/slides/thumbnails/workflow3.jpg)

## Suggestion for a Workable Workflow

1. Idea
2. Design docs
3. R package programming
4. Quality check (see [Ensuring Quality](https://openpharma.github.io/workshop-r-swe-mtl/slides/04_quality.html))
5. Publication (see [Publication](https://openpharma.github.io/workshop-r-swe-mtl/slides/06_publication.html))
6. Use in production

## Example - Step 1: Idea

Let’s assume that you used some lines of code to create simulated data in multiple projects:

```
dat <- data.frame(
    group = c(rep(1, 50), rep(2, 50)),
    values = c(
        rnorm(n = 50, mean = 8, sd = 12),
        rnorm(n = 50, mean = 14, sd = 11)
    )
)
```

Idea: put the code into a package

## Example - Step 2: Design docs

1. Describe the purpose and scope of the package
2. Analyse and describe the requirements in clear and simple terms (“prose”)

| Duty | must, shall | “must have” |
| --- | --- | --- |
| Desire | should | “nice to have” |
| Intention | may | “optional” |

## Example - Step 2: Design docs

**Purpose and Scope**

The R package *simulatr* shall enable the creation of reproducible fake data.

**Package Requirements**

*simulatr* **shall** provide a function to generate normal distributed random data for two independent groups. The function **must** allow flexible definition of sample size per group, mean per group, standard deviation per group. The reproducibility of the simulated data **must** be ensured via an optional seed. It **should** be possible to print the function result. The package **may** also facilitate graphical presentation of the simulated data.

## Example - Step 2: Design docs

UML Diagram

![](https://openpharma.github.io/workshop-r-swe-mtl/slides/resources/simulatr.png)

## Example - Step 3: Packaging

**R package programming**

1. Create basic package project (see [R Packages](https://openpharma.github.io/workshop-r-swe-mtl/slides/02_r_packages.html))
2. C&P existing R scripts (one-off scripts, prototype functions) and refactor <sup>1</sup> it if necessary
3. Create R generic functions
4. Document all functions

## Example - Step 3: Packaging

One-off script as starting point:

```
sim.data <- function(n1, n2, m1, m2, s1, s2) {
    data.frame(
        group = c(rep(1, n1), rep(2, n2)),
        values = c(
            rnorm(n = n1, mean = m1, sd = s1),
            rnorm(n = n2, mean = m2, sd = s2)
        )
    )
}
```

## Example - Step 3: Packaging

Refactored script:

```
getSimulatedTwoArmMeans <- function(n1, n2, mean1, mean2, sd1, sd2) {
    data.frame(
        group = c(rep(1, n1), rep(2, n2)),
        values = c(
            rnorm(n = n1, mean = mean1, sd = sd1),
            rnorm(n = n2, mean = mean2, sd = sd2)
        )
    )
}
```

Almost all functions, arguments, and objects should be self-explanatory due to their names.

## Example - Step 3: Packaging

Define that the result is a list <sup>1</sup> which is defined as class <sup>2</sup>:

```
getSimulatedTwoArmMeans <- function(n1, n2, mean1, mean2, sd1, sd2) {
    result <- list(n1 = n1, n2 = n2, 
         mean1 = mean1, mean2 = mean2, sd1 = sd1, sd2 = sd2)
    result$data <- data.frame(
        group = c(rep(1, n1), rep(2, n2)),
        values = c(
            rnorm(n = n1, mean = mean1, sd = sd1),
            rnorm(n = n2, mean = mean2, sd = sd2)
        )
    )
    # set the class attribute
    result <- structure(result, class = "SimulationResult")
    return(result)
}
```

## Example - Step 3: Packaging

The output is impractical, e.g., we need to scroll down:

```
x <- getSimulatedTwoArmMeans(n1 = 50, n2 = 50, mean1 = 5, mean2 = 7, sd1 = 3, sd2 = 4)
x
```

```
$n1
[1] 50

$n2
[1] 50

$mean1
[1] 5

$mean2
[1] 7

$sd1
[1] 3

$sd2
[1] 4

$data
    group     values
1       1  7.1141343
2       1  4.9315856
3       1  6.8486559
4       1  5.4232044
5       1  2.0878172
6       1  7.9193614
7       1  5.0556225
8       1  3.4090045
9       1  9.7855215
10      1  3.8303040
11      1  3.7302685
12      1  4.3866876
13      1  9.8628574
14      1  4.1734530
15      1  2.6518951
16      1  2.2552217
17      1 11.0663756
18      1  3.9420508
19      1  2.7530683
20      1  1.8982550
21      1  9.7836621
22      1  7.7106822
23      1  1.4399343
24      1  3.3501130
25      1  4.2583536
26      1  3.8472150
27      1  0.2564559
28      1  6.5326474
29      1  6.5880382
30      1  9.4028417
31      1 -0.9343407
32      1  1.9990465
33      1  4.0288828
34      1  7.4840710
35      1  0.1842904
36      1  5.9709388
37      1  7.6466984
38      1  9.3550466
39      1  2.0881370
40      1 -2.1755447
41      1  2.9977860
42      1  6.7294280
43      1  8.3300580
44      1  4.2954388
45      1  2.6732828
46      1  8.7928899
47      1  1.3333301
48      1  0.6293590
49      1  9.5145804
50      1 11.6575330
51      2  2.4621112
52      2 10.3836529
53      2  4.5212149
54      2  3.9959644
55      2  4.5571831
56      2  1.7348850
57      2  4.0642302
58      2  6.3167981
59      2  1.4109089
60      2  6.9872869
61      2 12.2999664
62      2 10.4135432
63      2  8.2688656
64      2  8.3836911
65      2 10.0665325
66      2  6.8688208
67      2  0.6668342
68      2  3.5497866
69      2  6.5461608
70      2  9.0016588
71      2 -0.6333340
72      2  5.9230671
73      2  9.8329140
74      2  6.6980313
75      2  2.8278715
76      2  9.7458649
77      2 15.4828345
78      2  7.0957971
79      2  1.5220685
80      2  1.9195722
81      2  9.9000047
82      2  1.4549744
83      2  6.6066112
84      2  8.0371548
85      2 10.1152841
86      2 12.3816661
87      2  4.7092046
88      2 12.5869406
89      2 11.9338095
90      2  9.2895885
91      2  4.9470729
92      2  2.4782172
93      2  5.0117435
94      2 12.4354892
95      2  7.2910415
96      2  2.7287502
97      2  3.4961628
98      2  9.4721105
99      2  8.7174763
100     2  6.7803903

attr(,"class")
[1] "SimulationResult"
```

Solution: implement generic function `print`

## Example - Step 3: Packaging

Generic function `print`:

- [Code](#tabset-1-1)
- [Roxygen](#tabset-1-2)
- [Output](#tabset-1-3)

```
print.SimulationResult <- function(x, ...) {
    args <- list(n1 = x$n1, n2 = x$n2, 
        mean1 = x$mean1, mean2 = x$mean2, sd1 = x$sd1, sd2 = x$sd2)
    
    print(list(
        args = format(args), 
        data = dplyr::tibble(x$data)
    ), ...)
}
x
```

```
#' @title
#' Print Simulation Result
#'
#' @description
#' Generic function to print a \`SimulationResult\` object.
#'
#' @param x a \code{SimulationResult} object to print.
#' @param ... further arguments passed to or from other methods.
#' 
#' @examples
#' x <- getSimulatedTwoArmMeans(n1 = 50, n2 = 50, mean1 = 5, 
#'      mean2 = 7, sd1 = 3, sd2 = 4, seed = 123)
#' print(x)
#'
#' @export
```

```
$args
   n1    n2 mean1 mean2   sd1   sd2 
 "50"  "50"   "5"   "7"   "3"   "4" 

$data
# A tibble: 100 × 2
   group values
   <dbl>  <dbl>
 1     1   7.11
 2     1   4.93
 3     1   6.85
 4     1   5.42
 5     1   2.09
 6     1   7.92
 7     1   5.06
 8     1   3.41
 9     1   9.79
10     1   3.83
# ℹ 90 more rows
```

## Exercise

![](https://openpharma.github.io/workshop-r-swe-mtl/slides/thumbnails/exercise.jpg)

## Preparation

1. Download the unfinished R package [simulatr](https://openpharma.github.io/workshop-r-swe-mtl/slides/download/simulatr.zip)
2. Extract the package zip file
3. Open the project with RStudio
4. Complete the tasks below

## Tasks

- [Task 1](#tabset-2-1)
- [Task 2](#tabset-2-2)
- [Task 3](#tabset-2-3)
- [Task 4](#tabset-2-4)
- [Task 5](#tabset-2-5)
- [Task 6](#tabset-2-6)
- [Task 7](#tabset-2-7)

Add assertions to improve the usability and user experience

**Tip on assertions**

Use the package [checkmate](https://cran.r-project.org/package=checkmate "checkmate: Fast and Versatile Argument Checks") to validate input arguments.

Example:

```
playWithAssertions <- function(n1) {
  checkmate::assertInt(n1, lower = 1)
}
playWithAssertions(-1)
```

Error in playWithAssertions(-1): Assertion on ‘n1’ failed: Element 1 is not >= 1.

Add three additional results:

1. n total,
2. creation time, and
3. allocation ratio

**Tip on creation time**

`Sys.time()`, `format(Sys.time(), '%B %d, %Y')`, `Sys.Date()`

Add an additional result: `t.test` result

Add an optional *alternative* argument and pass it through `t.test`:

```
alternative = c("two.sided", "less", "greater")
```

Implement the generic functions `print` and `plot`.

**Tip on print**

Use the plot example function from above and extend it.

**Tip on plot**

Use R base [plot](https://bookdown.org/rdpeng/exdata/the-base-plotting-system-1.html) or [ggplot2](https://cran.r-project.org/package=ggplot2) to create a grouped boxplot of the fake data.

*Optional extra tasks:*

- Implement the generic functions `summary` and `cat`
- Implement the function `kable` known from the package [knitr](https://cran.r-project.org/package=knitr) as generic. *Tip*: use
	```
	kable <- function(x) UseMethod("kable")
	```
	to define kable as generic

*Optional extra task <sup>1</sup>:*

Document your functions with [Roxygen2](https://cran.r-project.org/package=roxygen2)

## References

- Gillespie, C., & Lovelace, R. (2017). Efficient R Programming: A Practical Guide to Smarter Programming. O’Reilly UK Ltd. \[[Book](https://amzn.to/3GU8HUW) | [Online](https://csgillespie.github.io/efficientR/)\]
- Grolemund, G. (2014). Hands-On Programming with R: Write Your Own Functions and Simulations (1. Aufl.).  
	O’Reilly and Associates. \[[Book](https://amzn.to/3QD7DeL) | [Online](https://rstudio-education.github.io/hopr/)\]
- Rupp, C., & SOPHISTen, die. (2009). Requirements-Engineering und -Management: Professionelle, iterative Anforderungsanalyse für die Praxis (5. Ed.). Carl Hanser Verlag GmbH & Co. KG. \[[Book](https://amzn.to/3DdwiBe)\]
- Wickham, H. (2015). R Packages: Organize, Test, Document, and Share Your Code (1. Aufl.). O’Reilly and Associates. \[[Book](https://amzn.to/34U0Fyj) | [Online](https://r-pkgs.org/)\]
- Wickham, H. (2019). Advanced R, Second Edition.  
	Taylor & Francis Ltd. \[[Book](https://amzn.to/3uLnxLd) | [Online](https://adv-r.hadley.nz/)\]

3 An R Package Engineering Workflow openstatsware Workshop: Good Software Engineering Practice for R Packages Daniel October 16, 2023