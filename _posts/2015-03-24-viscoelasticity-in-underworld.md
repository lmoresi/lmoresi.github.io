---
layout: post
title: 'Viscoelasticity in Underworld'
date: 2015-03-24 06:10
comments: true
categories: 
---

Viscoelasticity has been a hidden feature of **Underworld** for some time now, initially in the _experimental_ branch (alpha testing) and more recently, in the mainstream version. We did not officially release or document this implementation because it had not gone through peer review. Now, however, with Rebecca Farrington's recent paper on viscoelastic stresses in subducting plates, the benchmarking has been published and it is time to let everyone have a go with the implementation.

The implementation itself is very similar to that in **Ellipsis** but I think we simplified the flow of the code considerably this time. The Underworld version is both 2D and 3D, and has a second order stress update (see benchmarks). Rebecca's paper has a streamlined notation which, I think, is much closer to the physics of the problem even though we realise it is a bit dense !

If you want to try out these models, then you should first contact [Rebecca](mailto:rebecca.farrington@monash.edu). As usual, any problems should be addressed to the [underworld forum](https://underworldproject.org/forums/) first of all. 

**Farrington, R.J., Moresi, L.N., Capitanio, F.A., 2014. The role of viscoelasticity in subducting plates. Geochemistry, Geophysics, Geosystems 15, 4291–4304. doi:10.1002/2014GC005507**

## Summary of the science results

<img src="http://user-image.logdown.io/user/7331/blog/7268/post/258347/wSpwDgEbQEiZBh4cfNLO_FarringtonEtAl.png" height="500" align="right">

Subduction of tectonic plates into Earth’s mantle occurs when one plate bends beneath another at convergent plate boundaries. The characteristic time of deformation at these convergent boun- daries approximates the Maxwell relaxation time for olivine at lithospheric temperatures and pressures, it is therefore by definition a viscoelastic process. While this is widely acknowledged, the large-scale features of subduction can, and have been, successfully reproduced assuming the plate deforms by a viscous mecha- nism alone. However, the energy rates and stress profile within convergent margins are influenced by visco- elastic deformation. In this study, viscoelastic stresses have been systematically introduced into numerical models of free subduction, using both the viscosity and shear modulus to control the Maxwell relaxation time. The introduction of an elastic deformation mechanism into subduction models produces deviations in both the stress profile and energy rates within the subduction hinge when compared to viscous only mod- els. These variations result in an apparent viscosity that is variable throughout the length of the plate, decreasing upon approach and increasing upon leaving the hinge. At realistic Earth parameters, we show that viscoelastic stresses have a minor effect on morphology yet are less dissipative at depth and result in an energy transfer between the energy stored during bending and the energy released during unbending. We conclude that elasticity is important during both bending and unbending within the slab hinge with the resulting stress loading and energy profile indicating that slabs maintain larger deformation rates at smaller stresses during bending and retain their strength during unbending at depth.

## Summary of the implementation

### Stress History


The numerical implementation of the FEM-PIC integration within Underworld requires the stress history to be carried on a particle that is immersed in the fluid and is advected and rotated as required by the velocity  \\( \mathbf{u} \\).  As such the stress history tensor must be transported into the current reference frame. This is possible by introducing a new operator \\( \mathcal{T} \\) that ensures the stress on the transported particle, p, at location \\( \mathbf{x} \\) and time \\(t\\) is objective under advection and rotation over the interval \\(\Delta t\\).

  \\[
\stackrel{\vee}{\tau} _{ij} ^{t} (t, \mathbf{x}, \mathbf{u})  
=  \mathcal{T} _{\Delta t}^{x _p ^{t}}\big(\tau _{ij}^{t-\Delta t}\;(\mathbf{x} _p^{t-\Delta t}), \mathbf{x}, \mathbf{u} \big)
= \mathcal{L} _{1}( \tau _{ij} ^{t-\Delta t},\mathbf{x},\mathbf{u}) +
 \mathcal{L} _{2}( \tau _{ij} ^{t-\Delta t},\mathbf{x},\mathbf{u})
  \\]   


where \\( \mathcal{L} _1 = u _k . \partial\tau _{ij} / \partial x _k \\) accounts for advection through a velocity field given by \\(u _k\\) and \\(\mathcal{L} _2 = \tau _{ik} w _{kj} + \tau _{jk} w _{ki}\\) is the Jaumann stress rate and accounts for rotation.  

Taking a first order integration of the rotation term, \\(\mathcal{L} _2\\), produces values tangential to the rotation, thus providing an unconditionally unstable solution.
Integration of the Jaumann derivative with a minimum 2nd order accurate method is required to produce stable solutions to the rotation of the stress history term through a velocity field.

It should also be noted that there are other terms which may be added to this definition accounting for other changes in reference frame including stretching by way of the Oldroyd derivative as discussed at length by Harder in 1991.

Including these additional terms couples stress and pressure adding a considerable complication that is not required for mathematical consistency (See Eringen) and  are not addressed further in this study.

### The Elastic Timestep

A decoupling of the observation time and numerical time step is required.
This can be achieved by introducing an elastic timestep, \\( \Delta t_e \\), that ensures the required observation time is resolved, distinct from the smaller numerical timestep, \\(\Delta t_c\\).

Since \\( \Delta t _e > \Delta t _c \\), we must store the stress history over several timesteps.  This can be achieved by introducing a new term, \\( \tilde{\mathcal{T}} 
\\), being the stress history term defined across \\(n\\) numerical time steps of size \\( \Delta t _c\\).
The stress at current time \\( t \\) is then defined as

\\[
\tau _{ij}(\mathbf{x} _p^t) = 2\eta _{\rm{eff}}D _{ij}(\mathbf{x} _p^t) + \frac{\eta _{\rm{eff}}}{\mu\Delta t _e} \tilde{\mathcal{T}} _{\Delta t _e}^{\,x _p^t}(\stackrel{\vee}{\tau} _{ij}^{t-\Delta t _e})
\\]

Note the presence of \\( \Delta t _ e \\) in both the definition of \\( \tilde{\mathcal{T}} \\) and in the denominator of the preceding term, with \\( \eta _ {\rm{eff}} \\) now defined as \\( ( \eta\Delta t _e ) / ( \alpha + \Delta t _e) \\). Moresi et al, 2003, showed that a running average of the stress history could be used, defined as

\\[
T _{ij}^{t}(\mathbf{x} _p^{\, t})  = \big( 1 - \phi \big)\; \tilde{\mathcal{T}} _{\Delta t _c}^{\,x _p^t} \Big( T _{ij}^{t-\Delta t _c}(\mathbf{x} _p^{\,t-\Delta t _c}) \Big)  + \phi \tau _{ij}^{\,t}(\mathbf{x} _p^{\,t})
\\]

where \\(\phi = \Delta t _c / \Delta t _e < 1 \\), recalling here that the transport operator has ensured the stresses are advected and rotated into the current reference frame. 

## References

Eringen, A.C., 1980. Mechanics of continua /2nd edition/. Huntington, NY, Robert E. Krieger Publishing Co., 1980. 606pp.

Farrington, R.J., Moresi, L.N., Capitanio, F.A., 2014. The role of viscoelasticity in subducting plates. Geochemistry, Geophysics, Geosystems 15, 4291–4304. doi:10.1002/2014GC005507

Harder, H., 1991. Numerical simulation of thermal convection with Maxwellian viscoelasticity. J. Non-Newtonian Fluid Mech. 39, 67–88.

Moresi, L.N., Dufour, F., Muhlhaus, H.B., 2002. Mantle convection modeling with viscoelastic/brittle lithosphere: Numerical methodology and plate tectonic modeling. Pure And Applied Geophysics 159, 2335–2356. doi:10.1007/s00024-002-8738-3

Moresi, L.N., Dufour, F., Muhlhaus, H.B., 2003. A Lagrangian integration point finite element method for large deformation modeling of viscoelastic geomaterials. Journal of Computational Physics 184, 476–497. doi:10.1016/S0021-9991(02)00031-1

Moresi, L.N., Quenette, S., Lemiale, V., Mériaux, C., Appelbe, W., Mühlhaus, 2007. Computational approaches to studying non-linear dynamics of the crust and mantle. Phys. Earth Planet. Inter. 163, 69–82. doi:10.1016/j.pepi.2007.06.009


