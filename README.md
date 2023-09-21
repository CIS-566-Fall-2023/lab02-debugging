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


team members: Rachel Lin, Amy Liu
link: https://www.shadertoy.com/view/Dd3yR2
bugs:
1. line 97: compiler error; changed vec to vec2
2. line 100: changed raycast call to take in uv2 instead of uv; noticed that the uv mapping was off
3. line 11: changed to divide by iResolution.y instead of iResolution.x; used to resolve horizontal stretching
4. line 75: changed reflect call to reflect dir across nor; noticed that reflections weren't showing up
5. line 18: increased iterations in march fn to march to a further distance; noticed that floor was being warped around the spheres
