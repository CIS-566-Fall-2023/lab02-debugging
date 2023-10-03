# lab06-debugging

- Name:
  Tianyi Xiao

- [Link_To_My_Solution](https://www.shadertoy.com/view/cs3cz2)

- Bug List
1. `vec uv2 = 2.0 * uv - vec2(1.0); // found with compiler error, should change 'vec uv2' to 'vec2 uv2', to make the argument type right`
2. `H *= len * iResolution.x / iResolution.x; // the sphere is stretched, should change to  'iResolution.x / iResolution.y', to fit in the screen size`
3. `raycast(uv, dir, eye, ref); // screen is shifted, should use uv2 rather than uv`
4. `dir = reflect(eye, nor); // reflection result wrong, should use dir, which is the direction from eye to the intersection point`
5. `for(int i = 0; i < 64; ++i) { // no far ground, 64 is too small for ray casting iterations`

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
