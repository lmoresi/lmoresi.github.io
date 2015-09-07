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

 Underworld is based on the StGermain framework  


  underlying code structure is modular and object oriented; all important entities within the code (meshes, for example) being objects that allow proper inheritance

 On the other hand, the code is also well known for it's none-too-friendly `xml` based user interface and developers lament the complexity of the object model implemented in C. We have wondered for some time how to improve the user experience for newcomers and experts alike. We partnered with [CIG](www.geodynamics.org) to try to build a user-friendly version of underworld but, in the end, our various experiments with different approaches to running models have not significantly changed in ten years.



 The positive side of the  





### Some highlights

We have been through a number of iterations on the interface and
