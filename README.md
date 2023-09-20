# lab02-debugging

1. Amy Liu and Rachel Lin
2. https://www.shadertoy.com/view/Dscczj
3. - The first bug was just that uv2 was a vec class instead of vec2 class. We found this because it is a compile time error and showed up.
   - The second bug was that we were inputting the uv variable into raycast instead of uv2. I found this just because I was confused where uv2 was being used, and saw it simply wasn't being used anywhere.
   - The third bug was that our H variable in raycast was dividing by iResolution.x and did not utilize iResolution.y. I saw this because I saw the ratio of the spheres was off.
   - The fourth bug was with reflect. This took a while, but once we found out what the difference between eye and dir was, it made it more simple.

# Submission
- Create a pull request to this repository
- In the README, include the names of both your team members
- In the README, create a link to your shader toy solution with the bugs corrected
- In the README, describe each bug you found and include a sentence about HOW you found it.
- Make sure all three of your shadertoys are set to UNLISTED or PUBLIC (so we can see them!)
