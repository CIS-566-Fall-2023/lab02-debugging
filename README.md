# lab06-debugging

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

# Jiefu Ling Updated
- Team members: Jiefu Ling, Alex Fu
- [Link to solution](https://www.shadertoy.com/view/cd3yR2)
- Bugs:
  1. vec uv2. It missed the 2 after vec2. I found this error through the compiler error.
  2. H *= len * iResolution.x / iResolution.x;  It should be H *= len * iResolution.x / iResolution.y; I found this error by checking line by line. Aspect should be x / y not x / x;
  3. raycast(uv, dir, eye, ref);  It should be raycast(uv2, dir, eye, ref); I found this error by checking through the main process of the shader.
  4. dir = reflect(eye, nor); It should be dir = reflect(dir, nor); Because the reflection seems not correct. 
