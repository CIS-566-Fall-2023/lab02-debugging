# lab06-debugging

# Name & Link
### Janet Wang
https://www.shadertoy.com/view/DdccR2

# Bugs
### 1. Line 97: should write vec2
It's reminded by the compiler.
### 2. Line 100: Should use uv2 in raycast.
It's quite obvious when I read the mainImage() function line by line.
### 3. Line 11: Should be H *= len * iResolution.x / iResolution.y;
The geometry of the balls are weird, and the problem should be in raycast or sdf. And when looking at the raycast function, it's clear that H should be multiplied by Aspect ratio, which is iResolution.x / iResolution.y.
### 4. Line 11: Should be H *= len * iResolution.x / iResolution.y;
The balls are missing their reflections, so I read the code about relection in sdf. Somehow the input of reflect() was eye, it's meaningless and should be dir.

