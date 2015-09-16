---
layout: post
title: 'Cartopy'
date: 2015-09-16 # YYYY-MM-DD hh:mm
published: true # Won't build unless true
comments: true
categories: ['software','teaching']
image: # default is used if blank. Otherwise use images stored in the _images/posts folder
  feature: "site/GlobalAgeMapEq.jpg"
  credit: Louis Moresi
---

The [cartopy](http://scitools.org.uk/cartopy/) tutorial materials from the python VIEPS course from 2015 are now available on my github teaching page under [Mapping](https://github.com/lmoresi/teaching-python/tree/master/Mapping). I like the simplicity of this package and I used it to help the class learn how to code in notebooks. Updated since then for the new notebook systems, cartopy 0.13 and with tools to download the sample data.

The installation of this package can be a little complicated as it needs `proj4` and `gdal` which didn't work with `pip`  for me. You also need the requests package to download data from the urls as given.

I prefer the way cartopy works to the obvious alternative (basemap). GMT in python is still a work in progress.
