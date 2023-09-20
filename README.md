# lab06-debugging

# Submitting
 - Names: Kevin Zhang
 - Link: https://www.shadertoy.com/view/cscyz2
 - Bug line 11: fixed resolution ratio from .x to .y
 - Bug line 18: fixed precision by increasing range from 64 to 300
 - Bug line 75: reflection taking in eye instead of direction vector, eye -> dir
 - Bug line 97: not compiling, vec needs to be vec2
 - Bug line 100: using uv instead of uv2 for raycast, uv->uv2
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
