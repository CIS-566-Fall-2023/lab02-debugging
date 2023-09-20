# lab06-debugging: Utkarsh Dwivedi and Linda Zhu

# Setup 

Create a [Shadertoy account](https://www.shadertoy.com/). Either fork this shadertoy, or create a new shadertoy and copy the code from the [Debugging Puzzle](https://www.shadertoy.com/view/flGfRc).

Let's practice debugging! We have a broken shader. It should produce output that looks like this:
[Unbelievably beautiful shader](https://user-images.githubusercontent.com/1758825/200729570-8e10a37a-345d-4aff-8eff-6baf54a32a40.webm)

It don't do that. Correct THREE of the FIVE bugs that are messing up the output. You are STRONGLY ENCOURAGED to work with a partner and pair program to force you to talk about your debugging thought process out loud.

Extra credit if you can find all FIVE bugs.

## Our fixed shader toy: https://www.shadertoy.com/view/cd3yzj.

# Bugs Corrected (5.5?)
1. Compile error --> The variable type for uv in mainImage() was a vec, instead of a vec2.
2. Scene was off the screen --> raycast() was using the NDC coordinates uv, instead of uv2 in the screen space.
3. Shapes seemed stretched horizontally (in the x-axis) --> The half vector H in raycast() was calculated wrong. It was doing len * iResolution.x / iResolution.x, which is just len. Instead we should correct the dividend to iResolution.y.
4. No reflection on the material --> When calculating specular reflection, dir was reflecting the eye position with respect to the normal, which doesn't make sense. Instead dir should be reflect(dir, nor).
5. The amount of floor seen is less --> In march(), the maximum number of iterations was 64 so we terminated too early. Instead we just changed it to 256 to make more tiling visible. **In addition, we added a constraint on the maximum distance t to be 100. This might not be the 6th bug for the ray marching algorithm but definitely an optimization.**


# Submission
- Create a pull request to this repository
- In the README, include the names of both your team members
- In the README, create a link to your shader toy solution with the bugs corrected
- In the README, describe each bug you found and include a sentence about HOW you found it.
- Make sure all three of your shadertoys are set to UNLISTED or PUBLIC (so we can see them!)
