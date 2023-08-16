---
layout: default
title: Installation
permalink: /installation/
nav_order: 3
has_toc: true
---

# Installation 

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

----

# Requirements

## R-environment

{: .note } 
- R (4.3.1)
 - RStudio (recent version)
 - R packages installed:
   - 'devtools'
   - 'shiny'
   - 'bidsconvertr'


----

## Input data

The input data must have the following structure:

  -   an input folder containing all folders with DICOM data

-   …/subjects/sessions/DICOM
-   one folder per subject, for example: “00001”, “00002”
-   these folders containing the session data, each of which contains the DICOM data
-   …/sessions/subjects/DICOM
-   cross-sectional (at least one folder named ‘crosssectional’ or a custom session name)
-   one folder per session, for example: “session_1”, “session_2”
-   these folders, which contain DICOM data in separate folders
for each subject, e.g. “00001”, “00002”
- if you have any additional file structures, please contact me, so that I can include them.

----

# Install R, dependencies and RStudio

All code was tested with R Version 4.3.1, RTools43, and Tidyverse V 1.3.2.

### Windows

Download and install a recent [R version (V 4.3.1)](https://cran.r-project.org/bin/windows/base/){: .btn .btn-green }.

Download and install [Rtools43](https://cran.r-project.org/bin/windows/Rtools/rtools43/rtools.html){: .btn .btn-green } according to
your R-version (V 4.3.1). It is required to install the packages.

Download and install [RStudio](https://www.rstudio.com/products/rstudio/download/#download){: .btn .btn-green }.

### Debian/Ubuntu

To install R and its dependencies, enter the following commands into the terminal.

``` bash
wget -qO- https://cloud.r-project.org/bin/linux/ubuntu/marutter_pubkey.asc | sudo gpg --dearmor -o /usr/share/keyrings/r-project.gpg

echo "deb [signed-by=/usr/share/keyrings/r-project.gpg] https://cloud.r-project.org/bin/linux/ubuntu jammy-cran40/" | sudo tee -a /etc/apt/sources.list.d/r-project.list

sudo apt update

sudo apt install --no-install-recommends r-base

sudo apt install r-base-dev

sudo apt install libcurl4-openssl-dev libssl-dev libxml2-dev libfontconfig1-dev
```

Install
[RStudio](https://www.rstudio.com/products/rstudio/download/#download){: .btn .btn-green }.

Then “Right-Click -\> Open With -\>Software Install” should help in
the installation.

### Mac

We need some collaborators, who try out the BIDSconvertR on a Mac system. Contact me, if you are interested.

---- 
# Install the BIDSconvertR

{: .note } 
Please install R in accordance with the instructions. From here, copy & paste the following commands into RStudio's 'console' panel.

Known issues:
- If you are asked to install the package from binary source files select "yes". 
- If you are asked to update packages, you can skip this step via '3' or update the packages via '1' or '2'.
- If there is a 'installation of package ‘devtools’ had non-zero exit status' error message, identify the package (here 'devtools') with the error message and install it manually via 'install.packages("package_name")'.



Both packages must be installed only once. 
The `devtools` package is required to install packages from Github.

``` r
install.packages("shiny")
install.packages("devtools")
```



Using the command below, you can now install the most recent development version of `BIDSconvertR`.

``` r
devtools::install_github(repo = "bidsconvertr/bidsconvertr")
```