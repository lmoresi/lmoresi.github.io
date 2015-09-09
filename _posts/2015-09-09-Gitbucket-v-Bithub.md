---
layout: post
title: 'Gitbucket v. Bithub v. roll-your-own'
date: 2015-09-09 12:00
comments: true
published: true
categories: ['underworld']
#image: # default is used if blank. Otherwise use images stored in the _images/posts folder
#  feature: "posts/2015-05-03 10.01.27 HDR.png"
#  credit: Louis Moresi
---

The days of running a webserver quietly on some machine in the corner are long gone but what happens when you need services like repositories for code management, a user forum and other shared space for a distributed team project ? Increasingly people turn to online development sites such as [Github](http://www.github.com) or [Bitbucket](http://www.bitbucket.org). We recently decided to move to an external, online provider for our [Underworld2](/posts/underworld-2) code.

Monash university has been the manager of our Underworld web site through the [eResearch Centre](https://platforms.monash.edu/eresearch/) but Universities are not always well set up to handle distributed organisations with external collaborators. For Underworld2, we wanted to try out bitbucket and github so that we could broaden the use of the code, have more structure around the network of contributors and do a better job of keeping track of who is using the code and on what platforms (particularly which HPC systems).

Both platforms work well for a small open-source development team. If you like `git` then either platform is fine. If you don't care about which revision control system you use then either platform is fine too. We have pruned our codebase significantly with
[Underworld2](/posts/underworld-2) and have signficantly restructured the code that remains, so a fresh start was fine for us.

Bitbucket is well integrated with tools which monitor the health of the code and track issues. It has a more flexible models for small projects which are not open source and it allows different revision control systems. Github feels more like a fast-growing frontier town in the open source territory. It is more dogmatic about the way code should be done and it feels a little more freewheeling than Bitbucket.

We chose Github.

Two things made a difference: 1) website hosting (like this one) and the ability to point a custom domain at the site, 2) when we asked around, we found that students tended to use github for their projects and prefer it to bitbucket and the same appears to be true of developers that we work with (like the [CIG](www.geodynamics.org)).

Maybe three things. CogentOA also adopted github as a platform for reviewable code. So I started using github more and I also found some of my academic collaborators writing papers with `latex` + `git`. Peer pressure, perhaps, or great minds thinking alike. It crossed my mind that github is going to house all the world's code and a lot of the research algorithms before too long and apparently, there too I am not original

"... The odds of Github meeting a fate similar to that of the Library of Alexandria are slim."
{: .fancyquote}

[The Problem With Putting All the World’s Code in GitHub](http://www.wired.com/2015/06/problem-putting-worlds-code-github) — though the author of that article doesn't seem to get the git model of distributing out the repository.
