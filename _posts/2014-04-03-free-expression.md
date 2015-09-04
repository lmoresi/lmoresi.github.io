---
layout: post
title: 'Mathematics and Code'
date: 2014-04-03 10:47
modified: 2015-09-03
comments: true
categories: [Python, Mathematics, Underworld]
---
We've had a frantic phase of development in `Underworld` recently with a new `python` and `ipython` compatible version in the wings. Using the `ipython notebook` environment exclusively for a couple of weeks has rekindled my appreciation of `(multi)markdown` for documentation and the power of rendering mathematics with `mathjax`. I even gave a lecture this week using `ipython` to make slides _(I wouldn't actually recommend this, but it was interesting to be able do live demonstrations where I could modify my code to show off some numerical instabilities)_.

I wondered if there was a web-hosting or blogging site that had the  markdown, mathematics, code-highlighting capabilities of ipython notebooks, and I found [www.logdown.com](www.logdown.com "logdown"). This is what it can do:

## Mathematics

Display equations rendered with mathjax, first as a raw displayed equation

\\[
  S \frac{\partial h}{\partial t} + H = -\frac{\partial }{\partial x}
  \underbrace{\left( - K \frac{\partial h}{\partial x} \right)}_\text{flux}
 \\]

$$
   \xi

$$

<pre>
  \\[
  S \frac{\partial h}{\partial t} + H = -\frac{\partial }{\partial x}
  \underbrace{\left( - K \frac{\partial h}{\partial x} \right)}_\text{flux}
  \\]
</pre>  

and you can use inline equations so that you can explain what \\( {\partial h}/{\partial t} \\) means. In logdown: a blockquoted equation also works (it's probably a bug that this gets parsed as mathematics, but it is quite a nice way to add a label).

>  $$
  \frac{\partial {\mathbf u}}{\partial t}  +
  \left( {{{\mathbf u}}. \nabla } \right){{\mathbf u}}   =
  -\frac{1}{\rho }\nabla p  +  \textbf{F}  + \nu \nabla ^2{\mathbf u}
   $$
> Navier-Stokes equation




Recent versions of `mathjax` will parse `\begin{equation}` and `\end{equation}` (etc) tags successfully most of the time but this is not standard markup in any of the markdown extensions (including the logdown platform or iPython notebooks (based on github), pandoc, multimarkdown, etc. and so there is a competition between the different markup strategies.

The advantage of using the \\( \LaTeX \\) tags is that mathjax 2 will do equation numbering and cross references correctly within the document. At the moment, the best solution seems to be to double up the tags and use `\\[ \begin{equation}` and `\end{equation} \\]`. I can't comment on whether this violates how mathjax + markdown is supposed to work, but it does seem to be the most robust combination that I have tried. `\\( \ref{eq:blah} \\)` also seems the safest strategy.

<!--\\[-->
\begin{equation}
    \int_{\Gamma} \mathbf{F} \cdot d\Gamma +
    \int_{\Gamma} \rho \phi \mathbf{v} \cdot d\Gamma =
    \int_\Omega \nabla \cdot (\mathbf{F} + \rho \phi \mathbf{v}) d\Omega
\end{equation}
<!--\\]-->




## Code

Highlighted source code of equations in \\(\LaTeX\\) using the same \\\\( \\\\) and \\\\[ \\\\] tags which are commonly used to extend markdown for mathematics (including `ipython notebook`):

{% highlight latex %}
    \frac{\partial {\bf u}}{\partial t}  +
    \left( {{{\bf u}}. \nabla } \right){{\bf u}}   =
    -\frac{1}{\rho }\nabla p  +  \textbf{F}  + \nu \nabla ^2{\bf u}
{% endhighlight %}


scripts

{% highlight python %}
    #!/usr/bin/env python
    '''
      This example shows how you can add a set of particles to a swarm.
      Here the particles are layed out in a spiral configuration.
      Note that Scipy / Numpy are required for this example
    '''  
    import uwpytools

    # init using underworld 1.x XML files
    uwpytools.InitWithArgs("BuoyancyDrivenVanilla.xml PICellerator/PassiveTracerSwarm.xml")

    stgdict = uwpytools.GetCurrentDictionary()

    # set to initialise and solve
    stgdict["maxTimeSteps"]=-1
    stgdict["pauseToAttachDebugger"]=0
    stgdict["checkpointEvery"]=1
{% endhighlight %}

and C code (C-like code ... this is StGermain after all)

```C
#include <math.h>
#include <mpi.h>
#include <StGermain/StGermain.h>
#include <StgDomain/StgDomain.h>
#include <StgFEM/StgFEM.h>
#include <PICellerator/PICellerator.h>

#include "types.h"
#include "RheologyClass.h"
#include "StrainWeakening.h"
#include "YieldRheology.h"
#include "VonMises.h"
#include "ConstitutiveMatrix.h"

#include <assert.h>

/*
 * Textual name of this class -
 * This is a global pointer which is used for times when you need to refer to
 * class and not a particular instance of a class.
 */

const Type VonMises_Type = "VonMises";

/* Public Constructor */
VonMises* VonMises_New(
   Name                 name,
   AbstractContext*     context,
   StrainWeakening*     strainWeakening,
   MaterialPointsSwarm* materialPointsSwarm,
   double               minVisc,
   int                   strainRateTag,
   double               cohesion,
   double               cohesionAfterSoftening,
   Bool                 strainRateSoftening )

```

I think this is pretty impressive as a platform. I suppose the other question is how reliable the service actually turns out to be. We'll see ... but, if nothing else, the content is all in standard formats and can be re-used in many other places.
