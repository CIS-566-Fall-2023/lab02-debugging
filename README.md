# lab06-debugging

# Members
- Chang Liu

# Link
- [https://www.shadertoy.com/view/msKcRR](https://www.shadertoy.com/view/msKcRR)

# Bugs Found
See comments in code
```GLSL
void raycast(vec2 uv, out vec3 dir,
             out vec3 eye, out vec3 ref) {
    eye = rotateY(vec3(0.0, 0.0, 15.0), sin(iTime * 0.1) * 3.14159 * 0.5);
    ref = vec3(0.0, 0.0, 0.0);
    
    float len = tan(3.14159 * 0.125) * distance(eye, ref);
    vec3 H = normalize(cross(vec3(0.0, 1.0, 0.0), ref - eye));
    vec3 V = normalize(cross(H, eye - ref));
    V *= len;

    // ============================== bug2 ===================================
    // the aspect ratio wasn't correct
    // iResolution.x / iResolution.x ---> iResolution.x / iResolution.y

    H *= len * iResolution.x / iResolution.y;
    vec3 p = ref + uv.x * H + uv.y * V;
    dir = normalize(p - eye);
}

void march(vec3 origin, vec3 dir, out float t, out int hitObj) {
    t = 0.001;

    // ============================== bug5 ===================================
    // march more times so rays won't be terminated early

    for(int i = 0; i < 256; ++i) { 
        vec3 pos = origin + t * dir;
    	float m;
        sceneMap3D(pos, m, hitObj);
        if(m < 0.01) {
            return;
        }
        t += m;
    }
    t = -1.0;
    hitObj = -1;
}


vec3 computeMaterial(int hitObj, vec3 p, vec3 d, vec3 n) {
    switch(hitObj) {
        case 0:
        // Center sphere
        return vec3(1.0, 0.67, 0.67);
        break;
        case 1:
        // Back sphere
        return vec3(0.67, 1.0, 0.67);
        break;
        case 2:
        // Front sphere
        return vec3(0.67, 0.67, 1.0);
        break;
        case 3:
        // Floor
        float t = floor(mod((sin(p.x) + sin(p.z)) * 0.5, 2.0));
        return mix(vec3(0.7, 0.4, 0.2), vec3(1.0), t);
        break;
        case -1:
        // Background
        break;
    }
    return vec3(255.0, 229.0, 119.0) / 255.0;
}

Intersection sdf3D(vec3 dir, vec3 eye) {
    float t;
    int hitObj;
    march(eye, dir, t, hitObj);
    
    if(t == -1.0) {
        return Intersection(t, skyColor(dir),
                            vec3(eye + 1000.0 * dir),
                            -1);
    }

    vec3 isect = eye + t * dir;
    vec3 nor = computeNormal(isect);
    
    vec3 material = computeMaterial(hitObj, isect, dir, nor);
    
    // ============================== bug4 ===================================
    // it was 'dir = reflect(eye, nor)', which was wrong

    dir = reflect(dir, nor);
    march(isect + dir * 0.01, dir, t, hitObj);
    vec3 specReflCol;
    if(hitObj == -1) {
        specReflCol = skyColor(dir);
    }
    else {
        vec3 isect2 = isect + t * dir;
        nor = computeNormal(isect2);
        specReflCol = computeMaterial(hitObj, isect2, dir, nor);
    }
    float fresnel = 1.0 - max(0.0, dot(normalize(eye - isect), nor));
    fresnel = 0.25 + 0.75 * fresnel;
    vec3 sdfColor = mix(material, specReflCol * material, fresnel);
    
    return Intersection(t, sdfColor, isect, hitObj);
}

void mainImage( out vec4 fragColor, in vec2 fragCoord ) {
    // Normalized pixel coordinates (from 0 to 1)
    vec2 uv = fragCoord/iResolution.xy;
    // [-1, 1]

    // ============================== bug4 ===================================
    // it was 'vec uv = ...', which caused a compilation error

    vec2 uv2 = 2.0 * uv - vec2(1.0);
    
    vec3 dir, eye, ref;

    // ============================== bug3 ===================================
    // uv2 instead of uv should be passed here

    raycast(uv2, dir, eye, ref);
    fragColor = vec4(sdf3D(dir, eye).color, 1.);
    
}
```

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
