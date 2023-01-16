# Introduction
#Theory/ComputerGraphics 
In model ligthing there are 3 main models
- Global and local
- Direct and Indirect
- Sharp and soft shadows
We will study them in more depth.
# Global an Local lighting
Global effect for the whole scene, several parameters change the whole picture of the scene(The sun light in blender)
Created from local sources can only affect a limited region of the scene, you can control the
direction, intensity, shadows...(Any other light source but the global one in blender)
![[Pasted image 20221231125859.png]]
## Global lighting
There are three main types of lighting:
- **Backlight:** This light is created in all directions(Gives more bright to the scene)
- **Ambient Occlusion:** The shadows are created in contact point pixels.
- **HDRI:** Every pixel iluminates a bit every scene

## Local Lighting
There are two main types of lights
- Point source: The point source emits light from a point in all directions
- Spotlight: The spotlight acts like a flash with a given angle.
- Direct source: The rays emanate from one direction and the position of the source doesn't matter
- Flat Source: They are point sources spreaded over a flat surface
- Object surface: The rays pread over the normals of an object
![[Pasted image 20221231131108.png]]

# Direct and Indirect Lighting
Direct lighting is calculated in real time in the Eevee engine, however the indirect reflections are more realistic and they are developed by Cycles engine. An indirect reflection is whichever second reflection of the rays.

![[Pasted image 20221231130343.png]]

## Direct Lighting
Direct Illumination also called(TA) It's the first contact of a light ray with the camera after reflecting only once in an object. 

Indirect reflects can be pre calculated so they are simulated

## Inderect Lighting
The Indirect Lighting (NA) are the subsequent calculations of surface contacts from the TA. Every contact the ray loses intensity so usually from the 4th the image is changed really few. When using transparent objects it's important there are lots of contacts. However keep in mind this slows the rendering.

### Reflection using BRDF
This technique needs of the following requirements
- If the reflection is reversed, the function returns the same
- The probability of reflection must be positive
- The reflection cannot generate more intensity
- If the reflectance is of 100% all rays must be reflected
# Sharp and Soft shadows
This determines how the shadows are processed wethere a softer and more progressive way or a sharpened one.
