# lab06-debugging

Link to solution with bugs corrected: https://www.shadertoy.com/view/Ds3czj

1. Line 97: Changed vec to vec2; console was displaying a syntax error
2. Line 100: Changed uv to uv2. I noticed that uv2 wasn't being used
3. Line 11: Changed the second iResolution.x to iResolution.y. Spotted since it was strange to multiply and divide by the same variable
4. Line 75: Changed eye to dir in the reflect inputs. Knew there was an issue with the specular since the reflections weren't showing, and thought it made more sense to pass in dir than eye
5. Line 18: Made i loop for a larger number of iterations. Saw that the back "clipping plane" wasn't as far as the desired output, so thought to make it march for more steps

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
