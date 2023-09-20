# lab06-debugging

Shader Link: https://www.shadertoy.com/view/cd3yz2

Bug1: Apparently vec to vec2.
Bug2: In raycast(uv2, dir, eye, ref); we use uv2 instead of uv, uv2 transfer the orignal position to (0,0). When we use uv, the coordinate is wrong.
Bug3: In H *= len * iResolution.x / iResolution.y; We should / iResolution.y instead of iResolution.x. Cuz we want to generalize the length to the screen size.
Bug4: In dir = reflect(dir, nor); We should use dir to replace eye, eye is a position but we want the direction from eye.
