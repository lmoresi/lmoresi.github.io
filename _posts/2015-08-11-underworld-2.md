---
layout: post
title: 'Underworld 2 '
date: 2015-08-11 22:33
comments: true
categories: ['Underworld','Python']
image:
  feature: "posts/2015-05-03 10.01.27 HDR.png"
  credit: Louis Moresi
---



[Underworld](www.facebook.com/underworldcode) is our parallel, particle-in-cell, finite element geodynamics code.  For the past year or so, the  [Underworld](www.facebook.com/underworldcode) team has been  working on a refurbished user interface. We've known for a long time that it needed to be done but we finally bit the bullet.

We settled on turning underworld into a python code for two main reasons: 1) because many of our dependencies already have python bindings and 2) as we move more towards integrating with observations, it is necessary to interface with packages to pre-process data, many of which are python based or wrapped. I just thought of another one: 3) because we could. The tools for wrapping codes into python make this job much less scary than before.

### Background

The C code base has been around for about 10 years now, has been extensively debugged and is known to work well on hundreds to thousands of processors. We have engineered some pretty robust solver methods and lots of flexibility in dealing with complex rheology. I was pretty nervous about disrupting this part of the code no matter how much we needed to improve the user-interface.

Underworld is based on the StGermain framework [1] which is modular and object oriented; all important entities within the code (meshes, for example) being objects that allow proper inheritance and multiple, independent copies. Unfortunately, the objects have always needed to be described in largely-static xml files which have caused many levels of anxiety and trauma for the users. Developers have also had trouble with the complexity of the object model implemented in C and relatively simple code hacks by smart users (i.e. geophysicists !) were virtually impossible.

We have been through a number of different iterations on how to improve the user experience for newcomers and experts alike. We partnered with CIG to try to build a user-friendly version of underworld but, in the end, our various experiments with different approaches to running models have not significantly changed how people use the code.

I was concerned that we would not be in a position to support our users and maintain the code in future without taking steps to build a workable open-source community of user / developers (as happened with Citcom). John Mansour convinced me that a python interface would be a workable environment for geophysicist users to develop new functionality by building from low-level, parallel efficient underworld bricks. I didn’t really believe him but, the power of swig [LINK] to build a prototype interface in a few days, proved me wrong.

We have been through a number of iterations on the interface and

### Some highlights

We have been through a number of iterations on the interface and

### Teaching tools

### Parallelism and HPC
