---
layout: page
title: Research
modified: 2015-09-04
excerpt: "A short research statement"
image:
  feature: DSC_5374.jpg
  credit: "Louis Moresi"
toc: true
---


I am trying to understand the thermal-mechanical evolution of the Earth through geological time. This includes the fundamental question of how convective heat loss from the deep Earth is expressed mechanically as plate tectonics, the role of continents in the modulating this expression, the interaction between processes on this planetary scale with instabilities at the lithospheric scale — whether rheological or mechanical in nature, the influence of atmospheric feedbacks on the solid earth, and the signatures of all these processes  that we can expect to find through geophysical observation of the present day Earth, and in the long-term geological record.

Much of the complexity in the surface expression of mantle flow can be attributed to the non-linear nature of the constitutive laws.  The Earth, on geological timescales, behaves as a non-linear viscoelastic fluid with a finite strength due to small-scale processes such as faulting and ductile shear localization which can be treated through the theory of plasticity.  The underlying processes which we treat in this manner introduce complexity in that they introduce a significant dependence on the stress, strain, and thermal histories of the fluid representation. Plasticity is typically a phenomenological description of the material response to stresses and is cast in terms of the stress state of the material (from which the motions follow); in the Earth, stresses are less well known than the kinematics and much is likely to be learned from plasticity models which are founded on the kinematics of surface motions.

## Computational Plate Tectonic Modeling

<img class="right" src="http://user-image.logdown.io/user/7331/blog/7268/static_page/7524/8gnGWcRNKd6ncgnWVqvw_ImagesForResearchStatement.png" alt="Plate models and Shear Bands" >



My principal tool for these investigations is numerical modelling. In our discipline we face the combined challenges of efficient computation at a large scale, multiple scales of interacting physics, enormous variations in material properties in space and time, and history dependence of rheology. These challenges demand the development of suitable computational methods and very fast, robust numerical solution techniques. My contribution has been the development of particle based finite element methods and multigrid solvers which are robust in the face of very large viscosity contrasts.

I am a firm believer in the open-source distribution of software as a mechanism for advancing the baseline of competency in computational modelling in the discipline as a whole. Open source promotes the development of self-supporting communities of practice and the broadest possible sharing of expertise. My own software (Citcom, Ellipsis, Underworld) has all been released under open source licence to the community and grown through collaborative efforts.

## Some history

I worked with Slava Solomatov on the first numerical convection simulations with temperature dependent viscosity which varied by up to 12 orders of magnitude. The stagnant lid regime we found is observed on most solid planets and moons in the solar system that are still active. The work was extended to cover non- linear viscous constitutive laws and the scaling generalized. We also published the first paper demonstrating the role of brittle behaviour in the lithosphere in the emergence of plates from thermal convection for different planets. We derived heat-flow and stress scalings for plate-like convection styles and examined the influence of strain softening and elasticity on the persistence of plate-boundaries. Simple plasticity laws in convection models are now widely used in the modelling community for long-term Earth evolution and in understanding the tectonic style of super- Earth exoplanets.

Early work with Mike Gurnis quantified the relative strength of the subducting lithosphere using 3D numerical models constrained by gravity and dynamic topography. The continuation of these models into dynamically evolving, 3D slab simulations created a new understanding of how subduction zones evolve in time. Work with Schellart, Stegman, Capitanio and our co-workers has transformed the way people understand convergent margins as 3D systems with highly complex, evolving geometry. These papers begin to show how the continental record can capture the complex time-and-space variations in subduction zones, and how this might be used as another constraint on ancient subduction history.

I collaborated with Adrian Lenardic on coupled heat flow and deformation of the mantle and the continental crust. In a number of papers, we examined the competing effects of buoyancy in thermochemical convection and applied the results to understanding the development of instabilities beneath the continental lithosphere and their surface signatures (deep flow patterns, dynamic topography, free air gravity). Our work showed that the buoyant crust plays a significant role in the thermal and mechanical evolution of the mantle despite being a relatively small component by volume in this large scale system: it can modify the convection pattern, particularly the location and strength of downwelling instabilities, and strongly alter the surface heat flow pattern.

These problems required significant advances in numerical capability to deal with realistic, history- dependent, rheological properties in complicated geometries. Shijie Zhong and I developed robust and accurate multigrid solvers which could handle very strong viscosity variations, Hans Mühlhaus and I worked on methods which could handle history dependence and viscoelastic stresses in convection problems, and I have led efforts to create parallel implementations to solve high resolution problems in three dimensions. To make this work more accessible, I collaborated with Fabio Boschetti on methods for combining precise numerical models with imprecise geological interpretation and intuition.

These three main threads: robust solvers, advanced computational rheology and cutting edge subduction models – are combined in my most recent work. This considers 4D continental deformation as a consequence of subduction zone evolution and mantle flow, combining very high resolution subduction models with strong localisation in the over-riding plate to understand the accretion of exotic terranes and the influence of plumes on subduction dynamics.
