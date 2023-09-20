# lab06-debugging

## Aboudi Rai | Submission:
### Result
[My Debugging Scene](https://www.shadertoy.com/view/cd3czj)
### Bugs
1. Line 97: There was a syntax error where a `vec2` was accidentally written as `vec`.
2. Line 100: `uv` was fed into raycast instead of `uv2`
3. Line 11: Height was not being multiplied by correct aspect ratio. Switched to `H *= len * iResolution.x / iResolution.y` 
4. Line 18: Increased iteration count in `march(...)` to 256 to allow all parts of the floor to be hit.
5. Line 75: reflection was erroneously done about `eye` and `nor` rather than `dir` and `nor`. 

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
