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

so the code snippet is:

	<hview element>.opts(clone=False)

where the `clone=False` parameter updates the element in place. So you don't have to
assigne the return value to a new element object. See the example below. A modification
on the getting started tuorial at http://holoviews.org/getting_started/Introduction.html

![20180214_112112.jpg](https://github.com/shawnwanderson/shawnwanderson.github.io/raw/master/images/hvew_reset_opts.png)
