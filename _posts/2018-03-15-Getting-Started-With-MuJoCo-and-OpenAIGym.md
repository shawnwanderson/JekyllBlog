---
layout: post
title: Getting Started With MuJoCo and OpenAI Gym
category: Computing
tags:
  - tutorial
  - Reinforcement Learning
  - AI
published: true
---

## Installing MuJoCo and mujoco-py

1. Get License
2. Download mjpro150
3. put mjpro150 in ~/.mujoco
# Noooot working: ERROR: GLEW initialization error: Missing GL version
# I guess we should try with 131
4. put mjkey.txt in ~/.mujoco, also in ~/.mujoco/mjpro150/bin
5. Now install it (instructions on website)
6. download mujoco-py
	git clone https://github.com/openai/mujoco-py ~/.mujoco/
7. install all the dependencies listed at: https://github.com/openai/mujoco-py/blob/master/Dockerfile
8. Add the path to the mujoco bin directory
	export LD_LIBRARY_PATH=$HOME/.mujoco/mjpro150/bin
9. 
	cd mujoco-py
	pip install -e .

## Installing OpenAI Gym and MuJoCo Environment
pip install gym
