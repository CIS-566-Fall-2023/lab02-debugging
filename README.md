# lab06-debugging
[Fixed Shader Link] (https://www.shadertoy.com/view/Dd3yz2)

# Submission
Team members: Yuhan Liu, Diana Ouyang
- BUG 1 (won't compile): uv2 needs to be a vec2, not a vec, found out by compiler
- BUG 2 (sphere are weird large): raycast needs to use uv2 instead of uv2; right next to bug1 by convenience
- BUG 3 (weird horizontal stretch): iResolution.x / iResolution.y instead of .x; guessed based on weird screen thing had to be related to resolution
- BUG 4 (no reflections): reflection uses the dir instead of the eye vector; checked reflection-related code
- BUG 5 (disappearing floor): raymarch didn't have enough iterations; took longest time, deduced was raymarch bc. bug involved sphere/floor intersection
