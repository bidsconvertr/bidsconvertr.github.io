---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home

---

<!-- README.md is generated from README.Rmd. Please edit that file -->

# BIDSconvertR 


<!-- <figure>-->
<!-- <img align="right" height="150" src="../../inst/figure/BIDSconvertR.png" alt="BIDSconvertR logo"/>-->
<!-- <figcaption>The BIDSconvertR logo, created with </figcaption>-->
<!-- </figure>-->



<!-- badges: start -->

[![DOI](https://zenodo.org/badge/448850893.svg)](https://zenodo.org/badge/latestdoi/448850893)
[![BIDS](https://img.shields.io/badge/BIDS-v1.7.0-blue)](https://bids-specification.readthedocs.io/en/v1.7.0/)
[![Github](https://img.shields.io/github/v/release/bidsconvertr/bidsconvertr.svg)](https://github.com/bidsconvertr/bidsconvertr)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

|![BIDSconvertR]({{ site.baseurl }}/assets/BIDSconvertR.png){: width="150" } | The hexagonal sticker was made using the [iconspackage](https://github.com/mitchelloharawild/icons) and based on the MRI svg graphics provided by Flaticon and mavadee [FlaticonLink](https://www.flaticon.com/free-icons/mri). |



<!-- badges: end -->

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

----

## Aim

[BIDSconvertR](https://github.com/bidsconvertr/bidsconvertr) aims to provide a workflow that can:

- do the task inside of the R environment
- convert DICOM data to NIfTI (with the awesome [dcm2niix (v1.0.20230411)](https://github.com/rordenlab/dcm2niix) or [install a custom version]({{ site.baseurl }}/usage_notes/#installation-of-other-versions))
- structure this data according to the [BIDS specification](https://bids-specification.readthedocs.io/en/stable/)
- validate the compatibility with BIDS with the [BIDS validator](https://github.com/bids-standard/bids-validator)
- visualize the images with [papayaViewer](https://rii-mango.github.io/Papaya/) and [papayaWidget](https://github.com/muschellij2/papayaWidget)

----
## Features

- continuous application
  - lazy processing of already existing files 
  - easy application during data collection in ongoing studies
- user-friendliness (minimal terminal interaction required)
  - user dialog with message boxes guiding the users through the workflow
  - Shiny App (GUI) for sequence editing and data inspection
- file cleaning 
  - Renaming of subject-IDs or session-IDs with regular expressions.
  - Renaming of session-IDs
- BIDS validation
  - verification (color-coded) of sequence-IDs (comparing the entered sequence-IDs to regular expressions according to BIDS)
  - implemented validation with [BIDS-Validator](https://bids-standard.github.io/bids-validator/) (Website/Docker)
- quality control 
  - user-friendly ([papayaWidget](https://github.com/muschellij2/papayaWidget) image viewer) for BIDS datasets
- pseudonymized BIDS output (only metadata)
  - all potentially identifiable metadata was removed from images and JSONs


{: .warning } 
Only the metadata contained within the BIDS folder is free of potentially identifiable information. Follow the legal terms when sharing your dataset and consider additional defacing, pseudonymization, or both.

----
## Workflow visualization

![Workflow]({{ site.baseurl }}/assets/BIDSconvertR_workflow.png)

----
# How to cite: 

Wulms, Niklas. 2022. *BIDSconvertR*. Zenodo.
<https://doi.org/10.5281/ZENODO.5878407>.

----
## Milestones / To-Do's

- publish the BIDSconvertR
- testing the tool on MAC systems 
- create Docker container
- move image viewer into separate package
- adapt code to CRAN requirements