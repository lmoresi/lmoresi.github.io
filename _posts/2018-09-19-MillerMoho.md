---
layout: post
title: 'Alaska Moho Model'
date: 2018-09-19 # YYYY-MM-DD hh:mm
published: true # Won't build unless true
hidden: false # Will keep the post from appearing in the index (but can be previewed if the link is known)
comments: true
categories: ['geodynamics','stripy','seismology']
# image:
#  feature: "posts/Mill2015-05-03 10.01.27 HDR.png"
#  credit: Louis Moresi
---

# Alaska Moho: an example of reproducible research

![](posts/MillerMoho/MohoSurfaceGradient-ClusteredGrids.png)

Making your research reproducible means that you provide the entire workflow from data, through software and post-processing freely available. Not only can somebody repeat your experiments and verify them, they can build upon them. In lab-based disciplines, there are many further challenges, but in research that is predominantly based on data processing, this ought to be an achievable goal.

We are releasing all of the background for our recent paper on the Alaska Moho (Miller & Moresi, 2018) to make it transparent and reproducible. Open source software is one thing (the software and raw moho picks are available through `pip install miller_alaskamoho_srl2018`), but to manage
versions and operating system changes, we have packaged everything in a docker container (see [this earlier post](http://www.moresi.info/posts/Reproducible-Results-Docker/) for a long-winded discussion on why).

Since the software we release is also used to interpolate the surfaces, and not everyone wants to install docker, we also make
all our notebooks available in the cloud with everything pre-configured. You can launch it [here](https://mybinder.org/v2/gh/lmoresi/miller-moho-binder/publication) and try it out.

[![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/lmoresi/miller-moho-binder/publication)

The software is also tracked on Zenodo

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1459110.svg)](https://doi.org/10.5281/zenodo.1459110)

#### Reference

Miller, M. S., and L. Moresi (2018), Mapping the Alaskan Moho, Seismological Research Letters, 1–7, doi:10.1785/0220180222.
