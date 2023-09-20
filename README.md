
Teammates: I worked alone for this lab!

ShaderToy Link: https://www.shadertoy.com/view/cscczj

- Bug #1: There was a compilation error because on line 97, uv2 was declared as a vec when it needed to be a vec2! After changing uv2 to a vec2, the shader compiled.

- Bug #2: Now that I had something on the screen, it looked like something was off with the camera, so I looked at the raycast() function. On line 11, the H value was set to * iResolution.x / iResolution.x instead of * iResolution.x / iResolution.y! Correcting the denominator fixed the stretched camera issue.

- Bug #3: It still looks like there is an issue with the camera, as the spheres are not really centered in view. The raycast function seemed ok, so I looked at mainImage() where it was being called. On line 100, the uv vector was passed-in instead of the uv2 vector! Now the scene is centered properly in our view.

- Bug #4: The next big issue is that the specular reflections are missing, so I took a look at the sdf3D function, and knew it had to be at/after line 74 because of the comment. On line 75, the reflect() function was being called with eye instead of the direction vector, so once I changed eye to dir, the reflections came back! :D


- Bug #5: I know something is still wrong with the edges of the sphere, but I'll submit this for now and come back if I have time :)