---
layout: page
title: Software
excerpt: "A List of Articles"
modified: 2015-09-04
excerpt: "Software - Underworld and friends"
image:
  feature: site/GlobalAgeMapEq.jog
  credit: "Louis Moresi"
---

{% include  _toc.html %} <!-- lmth.cot_  grrrrrrr  in syntax highlighting land -->


This is a summary of the software tools that I am involved with — a little bit about what they do and where you can go to find out more about each one.

## Work in progress

  - Python and iPython enabled version of Underworld (aka Underworld2)
  - gLucifer in the cloud: webGL rendering version of the standalone app
  - Badlands surface process code with parallel/matrix formulation
  - GPlates interface
  - Spherical Underworld
  - Robust solvers

## Codes

**Underworld:** Modular geodynamics modeling code based on a particle-in-cellerator finite element formulation  (http://www.underworldproject.org and http://www.facebook.com/underworldcode). High performance, parallel, version of the Ellipsis algorithm developed as a community code with support from Australian infrastructure funding schemes. Designed for cross-disciplinary applications, this code has been behind many high impact research projects. Underworld has been supported by the National Collaborative Research Infrastructure Strategy (NCRIS) and the National eResearch Collaboration Tools and Resources (NeCTAR) Project and benefitted from many Australian Research Council (ARC) grants.

**CITCOM:** multigrid, 3D Cartesian Finite Element Code for mantle convection (freely available for researchers on request); Parallel and Spherical version available from http://www.geodynamics.org. Over the past 10 years, the global/spherical version of Citcom has become the mostly widely used community code in computational mantle dynamics.

**gLucifer:** Finite element analysis and visualization system with emphasis on particle methods (developed in conjunction with the AuScope and VPAC). Highly efficient transfer of information from simulations running on remote parallel supercomputers, server-based rendering etc.

**Ellipsis** and **Ellipsis3d:** Particle-in-Cell finite element code for geodynamics (prototype, no longer under active development - 2D/3D version distributed through http://www.geodynamics.org )

**Badlands:** Badlands is a collection of different codes all of which are intended to work with Underworld. Some of the codes are intended to model detailed stratigraphy in basins at relatively short timescale, others are more focused on broad brush descriptions of the interaction between dynamic topography and surface transport / erosion / deposition. This is a collaboration with the University of Sydney and Caltech.

## Publications

Moresi, L., Dufour, F., and Muhlhaus, H.B., 2002, Mantle convection modeling with viscoelastic/brittle lithosphere: Numerical methodology and plate tectonic modeling: Pure And Applied Geophysics, v. 159, no. 10, p. 2335–2356, doi: 10.1007/s00024-002-8738-3.   (Ellipsis)

Moresi, L., Dufour, F., and Muhlhaus, H.B., 2003, A Lagrangian integration point finite element method for large deformation modeling of viscoelastic geomaterials: Journal of Computational Physics, v. 184, no. 2, p. 476–497.  (Ellipsis)

Moresi, L., Quenette, S., Lemiale, V., Mériaux, C., Appelbe, W., Mühlhaus, 2007, Computational approaches to studying non-linear dynamics of the crust and mantle: Phys. Earth Planet. Inter, v. 163, p. 69–82, doi: 10.1016/j.pepi.2007.06.009. (Underworld)

## Software related Articles

{% for category in site.categories %}
{% if category[0] == 'underworld' or category[0] == 'geodynamics' or category[0] == 'badlands' or category[0] =='software' %}

{% for posts in {{category }} %}
 {% for post in posts %}
  {% if post.title %}
  <b> <a href="{{ post.url }}">{{ post.title }}</a> </b> &mdash; {{ post.excerpt | strip_html | truncate: 200 }}

  {% endif %}  
 {% endfor %}
{% endfor %}

{% endif %}  
{% endfor %}
