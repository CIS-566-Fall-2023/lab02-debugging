# lab06-debugging

# Submission

Team: Thomas Shaw and Rain Yan

[Shader with bugs corrected](https://www.shadertoy.com/view/DscyR2)

1. First bug was the aspect ratio being calculated wrong. This one we found just by glancing through the code.
2. The second was `vec` being used instead of `vec2` for `uv2` - this led to a compilation error, which was easy to pinpoint.
3. The next one followed, where we saw only a quarter of the image on screen, so we tracked it down to some non-normalized coordinates.
4. We noticed reflections weren't working, so we looked into the code for finding reflection materials. While stepping through the code to understand it we noticed the `reflect` call was using the wrong parameters and fixed it.
5. Finally, the image had some "warping" around objects, which (as far as we know from raymarching experience) could be fixed by either increasing the base `t` value, or increasing step count. We increased step count from 64 to 128 and got a similar final image.

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
