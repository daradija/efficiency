# efficiency

- sentido inverso, backpropagation.

Usar para tener concurrencia:
- las múltiples salidas 
- el batch

- hacer la hesiana, recordarla. Verificación con cálculo simbólico.

Significados:
- En este contexto que es el prunning? no propagar lo menos significativo. Limitar combinaciones.
- Los del batch se suman, eso que significa?

# Decidir donde aplicarlo
Posibilidades:
- Los precios de las casas.
- Los coches de carrera.
- Los brazos robóticos.

# Practicar con simbolismo.

Calculemos la matriz Hessiana de la función:

$$
f(x, y) = x^3 + 2xy + y^2
$$


Usaremos `SymPy` para obtener la Hessiana. Veamos el código y su ejecución:

La matriz Hessiana de la función \( f(x, y) = x^3 + 2xy + y^2 \) es:

$$
H_f =
\begin{bmatrix}
6x & 2 \\
2 & 2
\end{bmatrix}
$$

```python
import sympy as sp

# Definir variables simbólicas
x, y = sp.symbols('x y')

# Definir la función escalar f(x, y)
f = x**3 + 2*x*y + y**2

# Calcular el gradiente (vector de primeras derivadas)
grad_f = [sp.diff(f, var) for var in (x, y)]

# Calcular la matriz Hessiana (matriz de segundas derivadas)
hessian_f = sp.Matrix([[sp.diff(grad, var) for var in (x, y)] for grad in grad_f])

# Mostrar la matriz Hessiana
hessian_f
```
Una red 