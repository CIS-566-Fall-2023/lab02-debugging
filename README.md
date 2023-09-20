# lab06-debugging

# Team members

No team members.

# Shader Toy Links

[Fork 566 Debugg gehanzh 366](https://www.shadertoy.com/view/cs3yR2)

# Bugs

1. At first it just doesn't compile. So I found that it should be `vec2` instead of `vec` in line 97.

2. Transformation looks wrong. So I look into `raycast` function and found that in line 11 there's a typo `iResolution.x / iResolution.y` instead of `iResolution.x / iResolution.x`.

3. Transformation is still wrong but there is nothing wrong in `raycast` function. So I found that `raycast` is called with wrong parameters in line 100. The first parameter should be `uv2` instead of `uv`.
4. The material doesn't look specular. And I noticed that eye vector is passed to `reflect` function, which is definitely wrong. Change it to `dir` and it looks the same as the reference.
5. Reflection doesn't look the same as the reference. It is because number of iterations is too small. 

6. (Not sure if it's a bug) It looks like Schlick's approximation is used to compute fresnel but `pow` is missing, so I fixed and it looks more specular now.
# Setup 

Create a [Shadertoy account](https://www.shadertoy.com/). Either fork this shadertoy, or create a new shadertoy and copy the code from the [Debugging Puzzle](https://www.shadertoy.com/view/flGfRc).

Let's practice debugging! We have a broken shader. It should produce output that looks like this:
[Unbelievably beautiful shader](https://user-images.githubusercontent.com/1758825/200729570-8e10a37a-345d-4aff-8eff-6baf54a32a40.webm)

It don't do that. Correct THREE of the FIVE bugs that are messing up the output. You are STRONGLY ENCOURAGED to work with a partner and pair program to force you to talk about your debugging thought process out loud.

Extra credit if you can find all FIVE bugs.

# Submission
- Create a pull request to this repository
- In the README, include the names of both your team members
- In the README, create a link to your shader toy solution with the bugs corrected
- In the README, describe each bug you found and include a sentence about HOW you found it.
- Make sure all three of your shadertoys are set to UNLISTED or PUBLIC (so we can see them!)
