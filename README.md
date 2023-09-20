# Kyra Clark & Saksham Nagpal - Lab 2
[Link to Shadertoy](https://www.shadertoy.com/view/DsccRj)

## Bugs, and how we found them!
1. **Bug 1 - Line #97 :** It was just a vec and not a vec2. We pressed compile, and the compilation failed and pointed us teo that line.
2. **Bug 2 - Line #100 :** The raycast function was using uv instead of uv2. We identified that the spheres' positions were way off on the screen when rendered, so we looked closely at the UVs being used, and found the bug in the mainImage function where the rendering was happening.
3. **Bug 3 - Line #18 :** We increased the max no. of iterations on our march function from 64 to 200. We noticed a weird warp around the edges of the sphere, which we identified from the slides that it happens when we terminate our raymarch too early and we lose out on details.
4. **Bug 4 - Line #11 :** H was being calculated with a multiplication factor of iResolution.x / iResolution.x, we changed the denominator to iResolution.y . We noticed the spheres were squashed, so we narrowed the issue down to 2 places - (i) either the SDF sampling is weird, or (ii) the raycast function is doing something funky. It was the latter.
5. **Bug 5 - Line #75 :** The reflect function was using 'eye' instead of 'dir'. The specular highlights were missing, so we knew the function to look at was sdf3D where the specular highlights get calculated. Looking there, we expected the reflect function to have a direction vector as input to reflect that along the input normal, but a vec3 position (i.e. eye) was being sent as the input instead, which was sus.
