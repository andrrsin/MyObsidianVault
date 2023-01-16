#Theory/ComputerGraphics 

# Graphics system
The graphic system can be decomposed in two main parts:
- **Image Inputs Devices:** This devices are in charge on capturing real image and transforming them to digital images. Examples of such are:
	- 2D and 3D scanners
	- Graphic Tablets
	- Video cameras
- **Image Output Devices:** This elements show in the real world the results aftres processing image input. The examples of such are:
	- Display Screens
	- Printers
	- Plotters

# Our Visible spectrum
The light radiation is a fenomenom that affects our eye's retina and creates the perception of an image. This radiation is perceived as waves and in the human eye this waves have a limitation aproximately from 700 nm to 400 nm.
![[Pasted image 20221229200906.png]]
Note that the combination of such waves will give as a result the white color. Plus always keep in mind that: $frequency(THz) = \frac{1}{Wavelength(nm)}$
## Lightness vs Brightness
Keep in mind that light is seen directly from a light source or the light reflected from a surface.
```ad-warning
This lightness is commonly referred to the light reflected from a surface where as the brightness is referred to the light source. 
```

## Color Characteristics
- **Brightness:** Intensity of a light stream
- **[[Hue]]:** Pure color Information
- **Saturation:** Intensity of specific wavelengths. The human eye can observe up until 200
- **Contrast:** Difference between two characteristics
# Dynamic Range
In humans eye the dynamic range is the range from th elowest color we can see until the largest. This depending the devices changes drastically.
![[Pasted image 20221229203551.png]]
# Gamma value
THe visual information that is received is encoded using gamma values. This encoding is done to ensure that the results won't change drastically from one device to another. This is decoded using a gamma correction factor in the output devices following this formula:
$$V_{s}= I^\gamma$$
Being $V_s$ the Gamma corrected value. I the original value and $\gamma$ the gamma coeficient.
![[Pasted image 20221229204325.png]]
# Color models
Color model is a mathematical method to describe a color. They can be used to specify a **color space**.
There are several Color models classified:
- By Dependence
	- Device Dependence
		- RGB(A)
		- CMY(K)
	- Device Independent
		- Munsell
	- Perceptual
		- HSV
		- HSL
		- HSI
- By color mixing operations
	- Additive
		- RGB
		- HSV
	- Substractive
		- CMY(K)
| Color Model Type | Example                              |
| ---------------- | ------------------------------------ |
| Additive         | ![[Pasted image 20221229204853.png]] |
| Substractive     | ![[Pasted image 20221229204901.png]] |

## CIE XYZ Model
**XYZ** model represents the colors only using the light intensity it can be shown in a 2D space. It is based on the fact that Z is based on XY as follows:
$$x+y+z=1$$
![[Pasted image 20221229205401.png]]
The white color in the diagram is represented as $x=y=z=\frac{1}{3}$ 
### CIE Lab Model
This variation of the CIE XYZ has a L for lightness, an a for Green and Red components and a b for blue and yellow. It is used usually in Graphic editos to change from one color model to other. Note that it's device independent.
![[Pasted image 20221229205609.png]]
## HS* Models
These color models have two common characteristics:
- H stands for Hue
- S sands for Saturation
Depending the color model there will be another variable after.
```ad-warning
H is defined by employing the color wheel with the hue degrees of red color
```

This colormodels face a big prblem that is the fact of them not being able to represent all colors, however they are device independent.


### HSV
In this case the V stands for value
![[Pasted image 20221229205946.png]]
### HSL
In the case of HSL L stands for lightness
![[Pasted image 20221229210017.png]]

## YUV Model
The YUV model was used in the past for analogic TVs. In this model more bandwith was given to the luminance than the chromatic as it was more important.
- **Y:** Luminance
- **U:** Blue projection
- **V:** Red projection
# Digital structure of colors
The bit-depth or pixels for each colors remarks the number of colors a pc can use.
![[Pasted image 20221229210506.png]]
Each pixel has a mask of values typically this means that the volue of a pixel of colors will be 3 times the depth. This is later applied to matrixs of colors called channels. In that way it is represented the RGB colors in computers. where each element of the matrix is a value ranging between $[0,255]$ 
