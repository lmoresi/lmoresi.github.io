---
layout: page
title: Publications
modified: 2020-06-01
excerpt: "Publications — in reverse chronological order"
image:
  feature: site/DSC_5374.jpg
  credit: "Louis Moresi"
---



## Overview

  - [Google scholar](http://scholar.google.com.au/citations?user=f8WWAbgAAAAJ "Google scholar") citation tracking (h index 51 on 11600 citations).
  - Researchgate: [https://www.researchgate.net/profile/Louis_Moresi](https://www.researchgate.net/profile/Louis_Moresi "Researchgate")
  - ResearcherID: [http://www.researcherid.com/rid/H-1390-2011](https://www.researchgate.net/profile/Louis_Moresi "ResearcherID")
  - Orcid: [http://orcid.org/0000-0003-3685-174X](http://orcid.org/0000-0003-3685-174X "orcid")
  - Zotero: [http://www.zotero.org/lmoresi](http://www.zotero.org/lmoresi)


## Publicationos

_Note: this bibliography is automatically populated from my [zotero](http://www.zotero.org/lmoresi) page and may take a few moments to update._

<script>
for (let i = 2023; i >= 1995; i--) {
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




