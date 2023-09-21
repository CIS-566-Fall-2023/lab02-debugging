# Keyu Lu and Hanke(Leo) Wang-lab02-debugging
# Submission

Keyu Lu and Hanke(Leo) Wang

Shadertoy Link: [Submission](https://www.shadertoy.com/view/cdcczX)

Rendered Image: ![Rendered Image](https://github.com/uluyek/lab02-debugging/blob/main/CIS5660-Keyu-Hanke-Lab2.png)

1. **Aspect Ratio Correction**:
   
   Original:
   ```glsl
   H *= len * iResolution.x / iResolution.x; //This is just 1
   ```
   Corrected:
   ```glsl
   H *= len * iResolution.x / iResolution.y;
   ```

2. **Removal of Redundant `break` Statements**:
   We removed unnecessary `break` statements in the `computeMaterial` function following the `return` statements, making the code cleaner.

3. **Reflection Vector Calculation**:
    Original:
    ```glsl
    dir = reflect(eye, nor);
    ```
    Corrected:
    ```glsl
    dir = reflect(dir, nor);
    ```
   We corrected the reflection vector in the `sdf3D` function for accurate reflection rendering.

4. **UV Coordinates Calculation**:
    Original:
    ```glsl
    vec uv2 = 2.0 * uv - vec2(1.0);
    ```
    Corrected:
    ```glsl
    vec2 uv2 = 2.0 * uv - vec2(1.0);
    ```
   We corrected the `uv2` calculation in the `mainImage` function, ensuring the correct field of view and aspect ratio.

5. **Ray March limit Adjustments**
  The for loop limit in the `march` function is raised to `700`, as the original 64 is not sufficient enough.


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
