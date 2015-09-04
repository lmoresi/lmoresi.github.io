---
layout: post
title: 'Mathematics and Code'
date: 2014-04-03 10:47
modified: 2015-09-03
comments: true
categories: [Python, Mathematics, Underworld]
---

This post was originally written for the "logdown" platform but I recently ported the whole lot across to github and their jekyll-based environment. I have therefore generalised my comments and I am showing only what works on github too. [ **Sept 4, 2015** ]
{: .notice}

We've had a frantic phase of development in `Underworld` recently with a new `python` and `ipython` compatible version in the wings. Using the `ipython notebook` environment exclusively for a couple of weeks has rekindled my appreciation of `(multi)markdown` for documentation and the power of rendering mathematics with `mathjax`. I even gave a lecture this week using `ipython` to make slides _(I wouldn't actually recommend this, but it was interesting to be able do live demonstrations where I could modify my code to show off some numerical instabilities)_.

I wondered if there was a web-hosting or blogging site that had the  markdown, mathematics, code-highlighting capabilities of ipython notebooks, and I found [www.logdown.com](www.logdown.com "logdown"). This is what it can do:

## Mathematics

Display equations rendered with mathjax as a raw displayed equation
<pre>
  \\[
  S \frac{\partial h}{\partial t} + H = -\frac{\partial }{\partial x}
  \underbrace{\left( - K \frac{\partial h}{\partial x} \right)}_\text{flux}
  \\]
</pre>  
Producing:
\\[
  S \frac{\partial h}{\partial t} + H = -\frac{\partial }{\partial x}
  \underbrace{\left( - K \frac{\partial h}{\partial x} \right)}_\text{flux}
 \\]


and you can use inline equations so that you can explain, for example, what \\( {\partial h}/{\partial t} \\) means by using \\\\( ... \\\\) tags.

Although  `mathjax` will parse `\begin{equation}` and `\end{equation}` (etc) markup successfully in some documents, it can be pretty hit and miss just how the different processing engines will battle it all out. Luckily, mathjax is [highly configurable](http://docs.mathjax.org/en/latest/tex.html) and you can usually find some combination of things that work. If you do use the latex `begin` / `end` tags, then it is possible to switch on equation numbering and labels. Who knows if this is really portable. Here is an example that works, I just had to be careful to escape the backslashes (i.e. `\\begin{equation}`)

\\begin{equation}
    S \frac{\partial h}{\partial t} + H = -\frac{\partial }{\partial x}
    \underbrace{\left( - K \frac{\partial h}{\partial x} \right)}_\text{flux}
\\end{equation}

\\begin{equation}
    \nabla \cdot \phi = 0
\\end{equation}



## Code

Code highlighting is also platform dependent. Markdown does this in a variety of ways, with Github using fenced code blocks and logdown adopting their strategy. In Jekyll, I found it hard to have consistent code block detection and highlighting without using the `liquid`  `{ % highlight language % }` and `{ % endhighlight % }` tags

{% highlight latex %}
    \frac{\partial {\bf u}}{\partial t}  +
    \left( {{{\bf u}}. \nabla } \right){{\bf u}}   =
    -\frac{1}{\rho }\nabla p  +  \textbf{F}  + \nu \nabla ^2{\bf u}
{% endhighlight %}

python scripts:

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

{% highlight c %}
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
{% endhighlight%}

I highly recommend the logdown platform. If you are using github, though, it is not too much of a stretch to get things working directly with Jekyll and keep everything in one spot. We'll see, I suppose !
