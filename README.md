# lab06-debugging

Hansen Yi and Kisha Yan

https://www.shadertoy.com/view/csccR2

Bugs
1. There was a typo in line 97, vec instead of vec2, we found it because the shadertoy did not compile and gave a warning.
2. We changed the second iResoultion.x to iResolution.y in line 11. We found it because the resolution of the screen seemed stretched and multiplying by iResolution.x / iResolution.x was just multiplying by 1.
3. In line 100, we changed uv to uv2. We found it because we realized for the raycast that the input should range from -1 to 1 as opposed to just 0 to 1.

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
