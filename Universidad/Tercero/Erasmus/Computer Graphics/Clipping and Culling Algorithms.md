#Theory/ComputerGraphics 
Scenes may have lots of objects which can slow down the performance. Clipping and Culling are two techniques to avoid such.
- **Clipping** removes objects or object parts that are outside of visible area

- **Occlusion Culling** removes object parts that are obstructed by parts of the same object that
	are closer to a viewer
# Clipping
![[Pasted image 20230101233752.png]]
Clipping in 2D spaces occurs in a plane, just as the example shows. In 3D it is determined by a box or truncated pyramid. (Example is vad fire graphics in old games)
| Clipping Technique | Description                           | Pros/Cons                       | Special algorithms                                                        |
| ------------------ | ------------------------------------- | ------------------------------- | ------------------------------------------------------------------------- |
| Point Clipping     | Used to visualize particles           | Simple and fast                 |                                                                           |
| Line Clipping      | Lines intersecting the CW are trimmed | Varies depending the algorithms | Cohen-Sutherland, Midpoint, Cyrus-Beck, Liang Barksy, Nicholl-Lee-Nicholl |

## Cohen-Sutherland
The space is divided in 9 parts containing each 4 bits, Only the CW is set to 0, therefore each endpoint contains information whether they are inside or out.
![[Pasted image 20230101235059.png]]
After this algorithm is applied:
```cs
if(C1 or C2 == 0000)
	fully visible
if(C1 and C2 != 0000)
	fully invisible
else
	Intersect the corresponding line
```
## Midpoint subdivision
Line is divided in two iteratively until the error is small enough. Quite simmilar to [[Newton's approximation]].

# Culling
There are three main types of culling:
- **Backface Culling:** Ignores the polygons facing away
- **Contribution Culling:** Ignores objects that are too far away
- **Occlusion Culling:** Ignores objects positioned behind opaque ones.
## Backface Culling
A polygon is facing the camera when the angle between the normal n  and the triangle-camerav  is less than 90º if v · n > 0 the object is not displayed.

Backface is not desired for not convex objects or transparent objects.
### Z-Buffer algorithm
![[Pasted image 20230102001819.png]]
We always take the closest z-buffer as it means it is closer to the camera. Scenes are "painted with colors being polygons".
### Painter Algorithm
Further objects are drawn first and closest are last.
![[Pasted image 20230102002008.png]]


### Ray Tracing
Ray tracing can be used to render photo realistic images but is too slow for real
time rendering. Rays are cast from every pixel of the screen and its distance to the closest object, the ray tracer can manage reflection and refraction. It doesnt employ coherence.
