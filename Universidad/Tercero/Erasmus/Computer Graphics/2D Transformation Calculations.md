#Laboratory/ComputerGraphics 
# Identifying a Transformation
Linear transformations preserving shape and size (scale of 1), can have 3 parameters.
- 2 Transfer parameter Tx and Ty
- Rotation angle determined as $\theta$
A transformation without any change of position or angle look slike this
$$\begin{bmatrix}x^{*} & y^{*} & 1\end{bmatrix} = \begin{bmatrix}x & y & 1\end{bmatrix}   
\bullet\begin{bmatrix} 1 & 0&0\\0&1&0  \\0&0&1 \end{bmatrix}$$
If all the parameters are applied it would change to:
$$\begin{bmatrix}x^{*} & y^{*} & 1\end{bmatrix} = \begin{bmatrix}x & y & 1\end{bmatrix}   
\bullet\begin{bmatrix} -\cos{\theta} & \sin{\theta}&0\\- \sin{\theta}&\cos{\theta}&0  \\T_{x}&T_{y}&1 \end{bmatrix}$$
## Translate Transformation
$$\begin{bmatrix}x^{*} & y^{*} & 1\end{bmatrix} = \begin{bmatrix}x & y & 1\end{bmatrix}   
\bullet\begin{bmatrix} 1 & 0&0\\0&1&0  \\T_x&T_y&1 \end{bmatrix}$$
The objective is to change the postion of the object, Where Tx and Ty are added to the x and y coordinates. 
![[Pasted image 20230102110142.png]]
$$\begin{bmatrix}x^{*} & y^{*} & 1\end{bmatrix} = \begin{bmatrix}3 & 2 & 1\end{bmatrix}   
\bullet\begin{bmatrix} 1 & 0&0\\0&1&0  \\4&3&1 \end{bmatrix} = \begin{bmatrix}7 & 5 & 1\end{bmatrix}$$
## Rotation Transformation
### Rotation from Origin point
$$\begin{bmatrix}x^{*} & y^{*} & 1\end{bmatrix} = \begin{bmatrix}x & y & 1\end{bmatrix}   
\bullet\begin{bmatrix} -\cos{\theta} & \sin{\theta}&0\\- \sin{\theta}&\cos{\theta}&0  \\0&0&1 \end{bmatrix}$$
Where thetha is the desired angle to rotate the object
### Rotation from a different point
In order to realize this transformation three steps must be followed.
1. Transfer to origin point
2. Rotate from origin
3. Transfer back
![[Pasted image 20230102110847.png]]
![[Pasted image 20230102110837.png]]

## Scaling Transformation
This is how the object is scalated from origin
![[Pasted image 20230102111115.png]]
To scale in points out from origin it is needed to do:
1. Transfer to origin point
2. Scale from origin
3. Transfer back
![[Pasted image 20230102111132.png]]
### Reflections
Reflecting from an axis is actually an scale of -1 in a given point of the diagonal of the transform matrix:
![[Pasted image 20230102111344.png]]
#### Reflecions from a point not in origin
This is a more complicated aproach as 5 steps are needed:
1. Transfer to origin
2. Rotate to align with x or y axis
3. Reflection about the coordinate axis
4. Rotate the angle of point 2 back
5. Transfer to the original point

## Shear Transformations
![[Pasted image 20230102112824.png]]
$$\begin{bmatrix}x^{*} & y^{*} & 1\end{bmatrix} = \begin{bmatrix}x & y & 1\end{bmatrix}   
\bullet\begin{bmatrix} 1 & L_y&0\\L_x&1&0  \\0&0&1 \end{bmatrix}$$

When the desried object is not in the origin this steps should be followed:
1. Move the object so that its base point coincides with the origin point . 
2. Rotate object to align its edge by one of the axes 
3. Perform shear in the direction of the coordinate axis. 
4. Rotate object with the same angle, but oposite direction 
5. Move the object to its original position (back in the opposite direction to point 1).