
Para el estudio de la realidad usamos modelos matematicos, es decir herramientas de calculo numerico cuyos resultados cotejan con la realidad.

#MinimosCuadrados

Pares ordenados de Datos NO exactos

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

1) triangularizacion:
![[Pasted image 20260908233342.png]]

2) sustitucion inversa:
![[Pasted image 20260908233608.png]]

elemento pivot aii: elemento de la diagonal principal

Tecnicas de pivoteo (Se busca el mayor valor absoluto para poner como pivot):
-  Pivoteo parcial: En la columna. Cambio de filas.
![[Pasted image 20260909004938.png]]
-  Pivoteo total: Se busca en la matriz. Cambian filas/columnas (cambian incognitas).
![[Pasted image 20260909004947.png]]

*TRABAJAMOS CON DATOS INEXACTOS*

Aproximacion a una curva - Metodo de Minimos Cuadrados:
- Dados un conjunto de pares ordenados (x,y) y una familia de funciones
- Se intenta encontrar la funcion continua (de la familia de funciones) que mas se aproxime a los puntos datos, de acuerdo al criterio de minimo error cuadratico
![[Pasted image 20260909145004.png]]
![[Pasted image 20260909145700.png]]

Desviacion: Sumatoria de las diferencias entre los valores datos y los calculados con la curva de ajuste
![[Pasted image 20260909145848.png]]
se cancelan los valores positivos con los negativos. Hay que independizar. Asi evitamos tener desviacion 0.
![[Pasted image 20260909145924.png]]
pero al derivar en los minimos, el valor absoluto impide el calculo.
![[Pasted image 20260909150711.png]]
expresamos la funcion de aproximacion como sumatoria
![[Pasted image 20260909152810.png]]

Resultado -> Magnitud de error de esa funcion con los puntos datos
La que mejor aproxima es la que tenga S: menor.

Minimizacion del Funcional de Desviacion:
- Busco coeficientes c que minimicen el valor de S.
- Igualo derivadas parciales de S respecto a cada c, a cero.
*VER DESARROLLO*
![[Pasted image 20260909163506.png]]
Si derivamos respecto de todos los coeficientes c se forma una SEL cuadrada, y si la resolvemos encontramos las incognitas c obteniendo la funcion de aproximacion.

para una funcion de 3 terminos c1, c2, c3:
![[Pasted image 20260909165345.png]]
![[Pasted image 20260909165502.png]]

*RESUMEN*
![[Pasted image 20260909165848.png]]

#EcuacionesNoLineales 
Ecuacion con una variable elevada a una potencia distinta de 1 o que incluye funciones trascendentes (trigonometricas, algebraicas o polinomios de grado mayor a 1)

Se busca encontrar las raices, asi que se van a aproximar a ellas. SUCESIVAMENTE.

La aproximacion que cumpla con error propuesto, se toma como solucion aproximada.

intervalo [a,b] de la F(x). Las raices son cada valor Ɛ para el cual la funcion se anula f(Ɛ)=0.

Etapas:
- Aislamiento de raices
- Aplicacion del metodo para encontrarlas

Aislamiento: establecer intervalo lo mas pequeño posible, tal que contenga una unica raiz.
- Teorema 1: si una f(x) asume valores de signos opuestos en los extremos de un intervalo [a,b], entonces el intervalo contendrá al menos un punto Ɛ tal que f(Ɛ)=0.
![[Pasted image 20260911141735.png]]

*Condicion necesaria:
- SI SE CUMPLE: puede que exista 1 o un numero impar de raices.
- SI NO SE CUMPLE: puede que no existan raices o un numero par de raices.
![[Pasted image 20260911143333.png]]

*Condicion suficiente:
- La raiz Ɛ será unica en el intervalo si la derivada de f(x) existe y conserva su signo en todo el intervalo.

1) Proceso de AISLAMIENTO
- Construimos una tabla de pares ordenados y buscamos el cambio de signo (5 minimo) VERRR
- Graficar la funcion
- pasamos de f(x)=0 a f1(x)=f2(x) y buscamos la interseccion siendo estas las raices de f(x)
![[Pasted image 20260911144005.png]]

1) Proceso de MEJORAMIENTO o PUNTO FIJO
- Aproximaciones sucesivas: Mejores en cada paso.
  Reemplaza la funcion original f(x)=0 a x=G(x) tal que cualquier solucion de esta tambien lo sea de la original.
  ![[Pasted image 20260911144416.png]]
  Dado x0 aproximacion inicial:
	- Se puede calcular x1, x2, x3, ...
	- La sucesion x1, x2, x3 convergen a la raiz Ɛ
	- El limite Ɛ constituye un punto fijo en si mismo de G(x). Ɛ=G(Ɛ)
  
  ![[Pasted image 20260911153408.png]]
  Sean G(x) y G'(x) continuas en el intervalo, si se cumple la condicion de convergencia para todos los puntos en el intervalo y si la aproximacion inicial pertenece al intervalo
  entonces:
  ![[Pasted image 20260911153818.png]]
  converge a la raiz Ɛ
  
  DESARROLLO
  ![[Pasted image 20260911154643.png]]
  ![[Pasted image 20260911154858.png]]
  2.![[Pasted image 20260911154922.png]]
  El termino de la izquierda es $e_{k+1}$
  
  Se desarrolla Taylor, se desprecia $(x_k - \varepsilon)^2$ ya que es insignificante al estar tan cerca xk de e.
  $$G(x_k) = G(\varepsilon) + (x_k - \varepsilon) G'(\varepsilon) + \frac{(x_k - \varepsilon)^2}{2} G''(\varepsilon) + \dots$$
  Reemplazando esa aproximación lineal de Taylor en la resta del paso 2:$$x_{k+1} - \varepsilon = \left[ G(\varepsilon) + (x_k - \varepsilon) G'(\varepsilon) \right] - G(\varepsilon)$$
  Queda:
  $$x_{k+1} - \varepsilon \approx (x_k - \varepsilon) G'(\varepsilon)$$
  ![[Pasted image 20260911160936.png]]

- Metodo de Newton Raphson: Mayor velocidad de convergencia.
  Deduccion a partir de:
  - Se deriva de la serrie de Taylor.
  - Como un caso particular del punto fijo.

    DESARROLLO SERIE DE TAYLOR
    ![[Pasted image 20260911162630.png]]
    ![[Pasted image 20260911162658.png|188]]
    Cambiamos nombres X=Xk+1, a=Xk
	![[Pasted image 20260911162812.png]]

	DESARROLLO CASO PARTICULAR DE PUNTO FIJO
	