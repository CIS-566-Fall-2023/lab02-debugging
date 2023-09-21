# lab06-debugging

Team members: Will, Debby

Shadertoy link: https://www.shadertoy.com/view/dstcRj 

Bugs found:

1. Fixed vec-> vec2 syntax error bug, to make it run normally.
2. Changed aspect ratio in the raycast function to iResolution.x / iResolution.y because noticed the camera was stretched.
3. Fixed mainImage to use uv2 instead of uv because noticed it wasn't using uv2, the correct camera position.
4. Noticed the intersection code wasn't using the direction of the raycast and using the eye position instead, so changed dir = reflect(eye, nor) to dir = reflect(dir, nor).
5. The render distance was shorter than it shouldve been so increased max raymarch distance from 64 to 300.

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
