---
layout: post
title: Flattening and Unflattening Keras Model Weights
category: Programming
tags:
  - keras
  - python
  - deep learning
  - evolution strategies
  - ES
  - AI
  - RL
  - optimization
published: true
---

I am implementing an Evolutionary Strategies(ES) approach to Reinforcement Learning
benchmark problems from Gym as documented [here](https://github.com/LinuxIsCool/756project/blob/master/README.org). 
In ES you optimize parameters theta as a black box. Thus instead of training our keras
model with backpropagation we are directly optimizing the parameter space via random
perterbations (mutations) in a population, and then selection. Thus we would like to
extract model weights to be manipulated directly, hence the need for flattening and
unflattening of the weights, which can be done with the following code:

	import collections
	def flatten(weights):
	    w = []
	    for l in weights:
		if isinstance(l, collections.Iterable):
		    w = w + flatten(l)
		else:
		    w = w + [l]
	    return w

	shape = [2,3]
	def unflatten(weights, shape, model):
	    w = []
	    i = 0
	    for l, size in enumerate(shape):
		layer = model.layers[l].get_weights()
		params = layer[0]
		bias = layer[1]
		new_layer = []
		new_params = []
		new_bias = []
		for param in params:
		    new_params.append(weights[i:i+size])
		    i += size
		for b in bias:
		    new_bias.append(weights[i])
		    i += 1
		w.append(np.array(new_params))
		w.append(np.array(new_bias))
	    return w
	 


It took me an hour or so to get these right, so I am documenting them here 
incase I need to reference them again in the future.
