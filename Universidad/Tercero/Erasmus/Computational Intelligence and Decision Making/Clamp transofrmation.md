#extra/Theory/AI
Clamp transofrmation is used to deal with outliers. The procedure is to clamp all value sbetween an upper and lower threshold.

$$x_{i} = \begin{cases}  
lower & \quad \text{if} x_{i} < lower; \\
higher & \quad \text{if} x_{i} > higher; \\
x_{i}\text{, otherwise} \\
\end{cases}
$$