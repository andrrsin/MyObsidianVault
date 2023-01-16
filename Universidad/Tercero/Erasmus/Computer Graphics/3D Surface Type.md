#Theory/ComputerGraphics 
# Composition of a 3DScene
A 3D scene is composed of 6 main elements. The file, the scenes, inside a scene there are models which are formed by a group or collection of objects. Then there are also surfaces and structural elements.

- Objects are composed of a set of surfaces
	- An object is a 3D representation of the 2D surfaces
	- They can be either solid monoliths or shells
- Surfaces are 2D structures that at any point (u,v) can describe the tangents and the normal.
	- There are different types of Surfaces such as.
		- Polygon networks
		- Parametric surfaces(Created with mathematical expressions)
		- Bezier splines
		- Monolith  geometry

# Dealing with Surfaces
In this point the surfaces are studied in deep concer, figuring techniques and different types of surfaces.
## Surface Types
### Polygon Networks
They are made of three structural components, such as vertex, edge and face. This are defined by an edge being the join of two vertex, and a face being the closed join of various vertex. A face would define a part of a finite 2D plane or 3D space.

**Network resolution** marks the precision of a polygon network the resolution is measured by the density of a grid and the number of vertex of such. There are two cateogires for polygon networks:
1. **Low poly:** They are composed of hundreds or thousands of polygons
2. **High poly:** They are composed of hundreds of thousands or millions of polygons.

The main advantages are the simple modeling they create and that this can be directly processed by GPUs. However the network may have low accuracy as it consumes a lot of resources.

```ad-warning
Concave polygons should be avoided, instead use convex polygons
```
When scanning objects Delaune scan is done that is joining the three closest generated vertex  forming triangles.
### Parametric Surfaces
This way of making surfaces is based on creating a function that is followed to create an object.  The formula has a common description as $S(u,v)=(x(u,v),y(u,v),z(u,v))$ For example:
![[Pasted image 20221230172522.png]]
The main problem this surface technique arises is that not all surfaces can be described with formulas and the polygon grid must be created beforehand. However it can be easily obtained the normal + the form won't change with different resolutions.

### Spline Surfaces
A spline is an interpolating function from which every values can be obtained intermediating with such. Its basic elements are: Vertex, weights, degree and node vector.
