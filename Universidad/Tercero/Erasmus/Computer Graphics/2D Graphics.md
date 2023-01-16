#Theory/ComputerGraphics 

# Spatial Discretization
It consists on dividing 2D analog images in small areas of a fixed size. This has a main problem that is some information may disappear or change.
![[Pasted image 20221229215421.png]]
## Discretization problems
- Ambiguities
- N-meanings
- Overlap
- "Dead" pixels
- Errors of aproximation
# Quantization
Dividing equally a set of characteristics to form a limited of equal number ranges. In this way only the number of range is what it's stored.

![[Pasted image 20221229220053.png]]
# Raster graphics
A raster image is defined as an array of separate points or pixels, in a discrete way. For each dot the color and brightness is specified. This is more in depth studied in the unit [[Rasterization]]. Its advantages are that It's the base of many input and output devices  and it doesn't depend on the software. However it makes it difficult to use it with text and it's hardware dependent.
## Data structure of Rasterization
- Raster Matrix: A matrix containing the data with a size of m x n.
- Column: It is the m part of the matrix
- Line: They are the n or the rows of the matrix

```ad-note
Rasterization can be 2D or 3D
```
There are several ways of representing a raster depending the devices:
- DPI (dots per inch) for printers
- PPI (pixels per inch) for monitors
- LPI (lines per Inch) for rasters
- SPI(samples per inch) for scanners
![[Pasted image 20221229221434.png]]

# Vector Graphics
The vector graphic images are made of a basic element called primitives. These represent geometric shapes that are open or closed but composed of primitives. The files will store only the data of the primitives. Some 2D primitives are:
- Dot
- Section
- Arc
- Circles
- Polygons
These primitives have attributes such as Color,Layer,Line type, scaling...
The main problem the vector graphics face is the imposibility to automate input of graphical information and the dependency on software, plus the limited scope t has due to its limitations.However it requires small data it's easy to edit, it can be easily converted raster and it has really high accuracy.

# Other Graphics
- Fractals
- Polygon Graphics
