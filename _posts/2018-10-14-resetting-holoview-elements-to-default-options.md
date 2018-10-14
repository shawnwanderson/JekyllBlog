---
published: true
layout: post
category: Dev
tags:
  - python
  - workflow
  - visualization
---

It took me the longest time to figure out how to reset the cmap option on a 
holoview Image object. It turns out, calling the opts() function with no
arguments will reset the opts to the defaults. It is important to understand
the difference between opts and options. Read more [here](http://holoviews.org/getting_started/Customization.html): 

![20180214_112112.jpg](https://github.com/shawnwanderson/shawnwanderson.github.io/raw/master/images/hvew_reset_opts.png)
