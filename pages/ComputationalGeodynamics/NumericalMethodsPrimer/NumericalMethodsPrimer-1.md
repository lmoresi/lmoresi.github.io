---
layout: page
title: "Computational Geodynamics: Introduction to Numerical Methods"
date: 2015-09-17
modified: 2015-09-17
image:
  feature: pages/MundusSubterraneusBanner.jpg
  credit: "Athanasius Kircher, Mundus subterraneus (1664/65)"
---

\\[
\newcommand{\dGamma}{\mathbf{d}\boldsymbol{\Gamma}}
\newcommand{\erfc}{\mbox{\rm erfc}}
\newcommand{\curly}{\sf }
\newcommand{\Red     }[1]{\textcolor[rgb]{0.7,0.0,0.0}{ #1}}
\newcommand{\Green   }[1]{\textcolor[rgb]{0.0,0.7,0.0}{ #1}}
\newcommand{\Blue    }[1]{\textcolor[rgb]{0.0,0.0,0.7}{ #1}}
\newcommand{\Emerald }[1]{\textcolor[rgb]{0.0,0.7,0.3}{ #1}}
\\]



## Introductory Remarks

We have considered the application of mathematical reasoning to construct models of the behaviour of physical systems. Unfortunately, most of these models do not have analytic solutions or the solutions are so complicated that they don't help us understand the problem. The alternative is to solve such problems numerically (approximately). Such solutions are also possible for far more elaborate systems than we would even consider trying to obtain exact solutions for.

On the other hand, numerical modeling only provides solutions to mathematical equations and only approximate solutions at that. Unless the modeler has an understanding of the methods and the models themselves, then the output of some computer code may be terribly misleading.

It is always necessary to design a numerical experiment as carefully as one would a physical experiment --- although it won't blow up and kill you. It is possible to change the laws of physics in the numerical model often inadvertantly, so a careful analysis of the problem first is not a bad idea.

This part of the course contains some really hard material. This is deliberate because the workings of most computer codes are actually based on some astonishingly intricate mathematics. This is really intended to provide a decent reference for people coming back to use finite elements or other numerical methods later.
