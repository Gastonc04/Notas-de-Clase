ecuacion lineal: polinomio 1er grado. (incognitas en distintos terminos elevadas a 1 y x una cte.)

sistema de ecuaciones lineales: conjunto.
![[Pasted image 20260908225727.png]]

a: coeficientes, x: incognitas, b: terminos ind.

resolver sist: calcular las incognitas para que se cumplan todas las ec.

se expresa matricialmente: A (m x n) coef, X (n x 1) incog, B (m x 1) term. ind.
A.x=b

clasificacion:
- Incompatibles (sin solucion)
- Compatibles (con solucion)
	-  Determinados (solucion unica n x n) <- Trabajamos con esta
	-  Indeterminados (infinitas soluciones)

sistemas mal condicionados: pequeñas variaciones en los datos = grandes variaciones en la solucion

metodos de resolucion:
-  Metodos directos (solucion exacta, numero finito de operaciones) <- Trabajamos con estos
	-  metodo de eliminacion de gauss*
	-  metodo de eliminacion de gauss jordan
	-  metodo de factorizacion de cholesky
	-  metodo de factorizacion de crout
-  Metodos indirectos (aproximacion lineal, mejores en cada paso sucesivo) <- en muchas incognitas o sistemas mal condicionados
	-  metodo de gauss seidel

metodo de eliminacion de gauss*
1) triangularizacion: matriz a triangular superior (0 debajo de diagonal principal)
2) sustitucion inversa: despeje de incognitas con las soluciones encontradas

nota: para hacer 0. el que va a volver a 0 / el que se vuelve 0
![[Pasted image 20260908232414.png]]

