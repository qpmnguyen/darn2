# darn2

[![stability-wip](https://img.shields.io/badge/stability-wip-lightgrey.svg)](https://github.com/mkenney/software-guides/blob/master/STABILITY-BADGES.md#work-in-progress)

This is a planned successor to the original [darn project](https://github.com/krlmlr/darn) by Kirill Muller. 
The goal of this project is to provide an approach to R workflow management based on scripts. Please refer to the
[`targets` package](https://books.ropensci.org/targets/) for an approach that is more comprehensive and more idiomatically R. 
This package is for for individuals who are required to perform script-based analysis due to various reasons.  

Following is the text from the original version: 

The `darn` package allows the definition of Directed Acyclic R script Networks.
A DARN is a collection of R scripts where each can have a (possibly empty)
set of prerequisites (other scripts that must be run before, and whose output is processed further).
Each R script also defines a (possibly empty) set of R objects
which are exported for use by the dependent scripts.
Unlike `remake` and other approaches, the dependencies are declared directly in the R scripts.
By design, each script can also be run individually, unchanged.
This makes it particularly easy to develop data preparation and analysis scripts
interactively, and then effortlessly integrate them in the script network
without worrying too much about interdependencies.

Each R script declares its prerequisites via a call to `darn::init()`,
and its outputs via a call to `darn::done()`;
the latter is mandatory to make the script part of the DARN.
A `Makefile` can be created from these implicit dependencies.
Running `make` only runs those scripts that are newer than their outputs,
i.e., only does as much as necessary to build the entire project.
New, modified or deleted scripts are detected,
and the dependencies are updated accordingly.

