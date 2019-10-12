---
layout: page
title: Publications
modified: 2015-09-04
excerpt: "Publications — in reverse chronological order"
image:
  feature: site/DSC_5374.jpg
  credit: "Louis Moresi"
---

{% include  _toc.html %} <!-- lmth.cot_  grrrrrrr can be heard all across syntax highlighting land -->


<script>
for (let i = 2019; i >= 1995; i--) {
   document.write(`<h2 > ${i} </h2>` );
   document.write(`<div id=year${i}>` + `Loading ${i} publications </div>` );

    fetch(`https://api.zotero.org/users/6049345/publications/items?format=bib&style=apa&linkwrap=1&q=${i}`)
				.then(function (response) {
					return response.text();
				})
				.then(function(body) {
					document.getElementById("year"+i).innerHTML = body;
				});
    document.write("<br/>")
}
</script>


## Overview

May 2019 — 128 publications in journals, books and refereed conference papers.

  * h-index 38 from 5200 citations (on 118 items indexed by Web of Science).
  * [Google scholar](http://scholar.google.com.au/citations?user=f8WWAbgAAAAJ "Google scholar") citation tracking (h index 43 on 7500 citations).
  * Researchgate: [https://www.researchgate.net/profile/Louis_Moresi](https://www.researchgate.net/profile/Louis_Moresi "Researchgate")
  * ResearcherID: [http://www.researcherid.com/rid/H-1390-2011](https://www.researchgate.net/profile/Louis_Moresi "ResearcherID")
  * Orcid: [http://orcid.org/0000-0003-3685-174X](http://orcid.org/0000-0003-3685-174X "orcid")

## _Selected_ Publications (Chronologically)

    0.  Yang, T., L. Moresi, M. Gurnis, S. Liu, D. Sandiford, S. Williams and F. A. Capitanio. "Contrasted East Asia and South America tectonics driven by deep mantle flow." Earth and Planetary Science Letters 517: 106-116, 2019

    0.  Beucher, R., L. Moresi, J. Giordani, J. Mansour, D. Sandiford, R. Farrington, L. Mondy, C. Mallard, P. Rey, G. Duclaux, O. Kaluza, A. Laik and S. Morón. UWGeodynamics: A teaching and research tool for numerical geodynamic modelling. Journal of Open Source Software 4(36), 2019

    0.  Boneh, Y., Schottenfels, E., Kwong, K., van Zelst, I., Tong, X., Eimer, M., Miller, M. S., Moresi, L., J. M. Warren, D. A. Wiens, M. Billen, J. Naliboff, Z. Zhan, Intermediate depth earthquakes controlled by incoming plate hydration along bending-related faults, Geophysical Research Letters,  Accepted, March 19, 2019

    0.  Morón, S., P. A. Cawood, P. W. Haines, S. J. Gallagher, S. Zahirovic, C. J. Lewis and L. Moresi. "Long-lived transcontinental sediment transport pathways of East Gondwana." Geology, 2019

    0.  Miller, M. S., and L. Moresi (2018), Mapping the Alaskan Moho, Seismological Research Letters, 1–7, doi:10.1785/0220180222.

    0. Garber, J. M., Maurya, S., Hernandez, J.-A., Duncan, M.S., Zeng,L., Zhang, H.L., Faul, U., McCammon, C., Montagner, J.-P., Moresi, L., Romanowicz, .A., Rudnick, R. L., Stixrude, L., Multidisciplinary constraints on the abundance of diamond and eclogite in the cratonic lithosphere,(2018), Geochemistry, Geophysics, Geosystems, 19, 2062-2086

    0.  J. Pall, J., Zahirovic, S., Doss, S., Hassan, R., Matthews, K. J., Cannon, J., Gurnis, M., Moresi, L., Lenardic, A., and Müller, R. D.: The influence of carbonate platform interactions with subduction zone volcanism on palaeo-atmospheric CO2 since the Devonian (2018), Clim. Past Discuss., 14, 857-870, https://doi.org/10.5194/cp-2017-112.

    0. T. Yang, L. Moresi, D. Zhao, D. Sandiford, and J. Whittaker (2018), Cenozoic lithospheric deformation in Northeast Asia and the rapidly-aging Pacific Plate, Earth and Planetary Science Letters, 492, 1–11, doi:10.1016/j.epsl.2018.03.057.

    0. Beall, A. P., L. N. Moresi, and C. M. Cooper (2018), Formation of cratonic lithosphere during the initiation of plate tectonics, Geology, 46(6), 487–490, doi:10.1130/G39943.1.

    0. B. Mather, S. McLaren, D. Taylor, S. Roy, and L. Moresi (2018), Variations and controls on crustal thermal regimes in Southeastern Australia, Tectonophysics, 723, 261–276, doi:10.1016/j.tecto.2017.12.015.

    0. Mondy, L. S., P. F. Rey, G. Duclaux, and L. Moresi, The role of asthenospheric flow during rift propagation and breakup, Geology, 46(2), 103–106, doi:10.1130/G39674.1,  (2017).

    0. Yang, T., L. Moresi, D. Müller, and M. Gurnis, Oceanic Residual Topography Agrees With Mantle Flow Predictions at Long Wavelengths, Geophys. Res. Lett., 152(3), 566–28, doi:10.1002/2017GL074800,  (2017).

    0. A. Beall, L. Moresi, T. Stern, Dripping or Delamination? A Range of Mechanisms for Removing the Lower Crust or Lithosphere, Geophysical Journal International, 210 (2), 671-692, (2017).

    0. Cooper, C. M., M. S. Miller, and L. Moresi, The structural evolution of the deep continental lithosphere, Tectonophysics, 695, 1–89, doi:10.1016/j.tecto.2016.12.004, (2016).

    0. O'Neill, C., A. Lenardic, M. Weller, L. Moresi, S. Quenette, and S. Zhang (2016), A window for plate tectonics in terrestrial planet evolution? Physics of the Earth and Planetary Interiors, 255, 80–92, doi:10.1016/j.pepi.2016.04.002.

    0. W. Sharples, L. N. Moresi, M Velic, M. A. Jadamec, D. A. May, Simulating faults and plate boundaries with a transversely isotropic plasticity model. Physics of the Earth and Planetary Interiors 252, 77-90  (2016).

    0. Sharples, W., L. N. Moresi, M. A. Jadamec, and J. Revote, Styles of rifting and fault spacing in numerical models of crustal extension, Journal of Geophysical Research-Solid Earth, 120(6), 4379–4404, doi:10.1002/2014JB011813 (2015).

    0. P. Betts, L. Moresi, M.S. Miller, D. Willis, Geodynamics of oceanic plateau and plume head accretion and their role in Phanerozoic orogenic systems of China. Geoscience Frontiers, doi: 10.1016/j.gsf.2014.07.002 (2015)

    0. L. Moresi, D. Willis, Time Dependent Behaviour of Congested Subduction, Elements, 11(2), APRIL 2015, electronic supplement, DOI: 10.13140/RG.2.1.1099.2169 or [elements URL](http://www.elementsmagazine.org/supplements/e11_2_Moresi_Willis_Movies.html)

    0. Aivazpourporgou, S., Thiel, S., Hayman, P.C., Moresi, L.N., Heinson, G., 2015. Decompression melting driving intraplate volcanism in Australia: Evidence from magnetotelluric sounding 1–9. doi:10.1002/(ISSN)1944-8007 (2015)

    0. Farrington, R.J., Moresi, L.N., Capitanio, F.A., The role of viscoelasticity in subducting plates. Geochemistry, Geophysics, Geosystems 15, 4291–4304. doi:10.1002/2014GC005507 (2014)

    0. S. Quenette, Yufei Xi, J. Mansour, L. Moresi, and D. Abramson, Underworld-GT applied to Guangdong, a tool to explore the Geothermal potential of the crust, J. of Earth Sciences (accepted Oct 2014)

    0. W. Sharples, M. A. Jadamec, L. N. Moresi, F. Capitanio, Overriding Plate Controls on Subduction Evolution,  J. Geophys. Res. (B) , doi: 10.1002/2014JB011163 (2014)

    0. Moresi, L.N., Betts, P.G., Miller, M.S., and Cayley, R.A., 2014, The Dynamics of Continental Accretion: Nature, doi:10.1038/nature13033.

    0. L. Moresi, Earth science: A resolution of the Archaean paradox. Nature 501, 496–497, doi:10.1038/501496a 2013.

    0. P. Betts, W. Mason, L. Moresi,  The influence of mantle plumes on subduction zone dynamics, Geology, 40,  739-742, 2012

    0. F. A. Capitanio, D. R. Stegman, L. N. Moresi, and W. Sharples. Upper plate controls on deep subduction, trench migrations and deformations at convergent margins. Tectonophysics, 483(1-2):80–92, 2010.

    0. A. Asgari and L. Moresi. Multiscale Particle-In-Cell Method: From Fluid to Solid Mechanics, Advanced Methods for Practical Applications in Fluid Mechanics, S. Jones (Ed.), ISBN: 978-953-51-0241-0, InTech, DOI: 10.5772/26419. 2012

    0. W. G.  Mason, L. Moresi, P. G. Betts, and M. S. Miller. Three-dimensional numerical models of the influence of a buoyant oceanic plateau on subduction zones. Tectonophysics, 483(1-2):71–79, 2010.
    0. A. Lenardic, A. M. Jellinek, and L. Moresi. A climate induced transition in the tectonic style of a terrestrial planet. Earth Planet. Sci. Lett., 271(1-4):34–42, 2008.

    0. D. May and L. Moresi. Preconditioned iterative methods for Stokes flow problems arising in computational geodynamics. Phys. Earth Planet. Inter, 171(1-4):33–47, 2008.

    0. L. Moresi, S. Quenette, V. Lemiale, C. Mériaux, W. Appelbe, and Mühlhaus. Computational approaches to studying non-linear dynamics of the crust and mantle. Phys. Earth Planet. Inter, 163:69–82, 2007.

    0. L. Moresi, H.-B. Mühlhaus, V. Lemiale, and D. May. Incompressible viscous formulations for deformation and yielding of the lithosphere. In G.D. Karner, G. Manatschal, and L. Pinheiro, eds., Imaging, Mapping, and Modeling extensional processes and Systems, v. Special Publication 282, pages 457–472. The Geological Society. 10.1144/SP282.19, 2007.

    0. W. P. Schellart, J. Freeman, D. R. Stegman, L. Moresi, and D. A. May. Evolution and diversity of subduction zones controlled by slab width. Nature, 446:308–311, 2007.

    0. A. Lenardic, L. Moresi, A. M. Jellinek, and M. Manga. Continental insulation, mantle cooling, and the surface area of oceans and continents. Earth Planet. Sci. Lett., 234:317–333, 2005.

    0. C. J. O’Neill, L. Moresi, and A. L. Jaques. Geodynamic controls on diamond deposits: Implications for Australian occurrences. Tectonophysics, 404:217–236, 2005.

    0. A. Lenardic, L. Moresi, and H. Muhlhaus. Longevity and stability of cratonic lithosphere: Insights from numerical simulations of coupled mantle convection and continental tectonics. J.Geophys. Res.-Solid Earth, 108: 2303, 2003.

    0. L. Moresi, F. Dufour, and H. B. Muhlhaus. A Lagrangian integration point finite element method for large deformation modeling of viscoelastic geomaterials. J. Computational Physics, 184:476–497, 2003.

    0. L. Moresi, H.-B. Muhlhaus, F. Dufour. Viscoelastic formulation for modelling of plate tectonics. H.-B. Muhlhaus, A. Dyskin, E. Pasternak, eds., In Bifurcation and Localization in Soils and Rocks, 337–344, Balkema, Rotterdam, 2001.

    0. F. Boschetti, L. Moresi. Interactive inversion in geosciences. Geophysics, 66:1226–1234, 2001.

    0. M. Gurnis, L. Moresi, R. D. Muller. Models of mantle convection incorporating plate tectonics: the australian region since the cretaceous. In M. A. Richards, R. Gordon, R. van der Hilst, eds. AGU Geophysical Monograph 21, 211–238. American Geophysical Union, 2000.

    0. S. J. Zhong, M. T. Zuber, L. Moresi, M. Gurnis. Role of temperature-dependent viscosity and surface plates in spherical shell models of mantle convection. J. Geophys. Res.-Solid Earth, 105:11063–11082, 2000.

    0. L. Moresi, M. Gurnis, S. J. Zhong. Plate tectonics and convection in the Earth’s mantle: Toward a numerical simulation. Computing In Science and Engineering, 2:22–33, 2000.

    0. A. Lenardic, L. Moresi, H. Muhlhaus. The role of mobile belts for the longevity of deep cratonic lithosphere: The crumple zone model. Geophys. Res. Lett., 27:1235–1238, 2000.

    0. P. M. Burgess, L. N. Moresi. Modelling rates and distribution of subsidence due to dynamic topography over subducting slabs: is it possible to identify dynamic topography from ancient strata?  Basin Research, 11:305–314, 1999.

    0. L. Moresi, V. S. Solomatov. Mantle convection with a brittle lithosphere: thoughts on the global tectonic styles of the Earth and Venus. Geophys. J. Int., 133:669–682, 1998.

    0. L. Moresi, A. Lenardic. Three-dimensional numerical simulations of crustal deformation and subcontinental mantle convection. Earth Planet. Sci. Lett., 150:233–243, 1997.

    0. L. Moresi, M. Gurnis. Constraints on the lateral strength of slabs from three dimensional dynamic flow models. Earth Planet. Sci. Lett., 138:15–28, 1996.

    0. L. Moresi, S. J. Zhong, M. Gurnis. The accuracy of finite element solutions of stokes’ flow with strongly varying viscosity. Phys. Earth Planet. Inter., 97:83–94, 1996.

    0. L. N. Moresi, V. S. Solomatov. Numerical investigation of 2d convection with extremely large viscosity variations. Phys. Fluids, 7:2154–2162, 1995.

    0. L. Moresi, B. Parsons. Interpreting gravity, geoid, and topography for convection with temperature-dependent viscosity - application to surface features on Venus. J. Geophys. Res.-Planets, 100:21155–21171, 1995.


## Other Scholarly Contributions

   0. L. Moresi. Computational Plate Tectonics and the Geological Record in the Continents, SIAM News, December 2015; [URL](https://sinews.siam.org/DetailsPage/tabid/607/ArticleID/685/Computational-Plate-Tectonics-and-the-Geological-Record-in-the-Continents.aspx)
