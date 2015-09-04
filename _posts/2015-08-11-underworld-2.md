---
layout: post
title: 'Underworld 2 '
date: 2015-08-11 22:33
comments: true
categories: 
---
# Underworld 2 

[Underworld](www.facebook.com/underworldcode) is our parallel, particle-in-cell, finite element geodynamics code. The code base has been around for 10 or so years now and has been largely debugged and is known to work well on hundreds to thousands of processors. We have engineered some pretty robust solver methods and lots of flexibility in dealing with complex rheology. The underlying code structure is modular and object oriented; all important entities within the code (meshes, for example) being objects that allow proper inheritance 

On the other hand, the code is also well known for it's none-too-friendly `xml` based user interface and developers lament the complexity of the object model implemented in C. We have wondered for some time how to improve the user experience for newcomers and experts alike. We partnered with [CIG](www.geodynamics.org) to try to build a user-friendly version of underworld but, in the end, our various experiments with different approaches to running models have not significantly changed in ten years.



The entire underworld team has been busy working on a new front end for 

