
## U1: Señales y Sistemas

Diversas aplicaciones.

Hay señales y sistemas de tiempo discreto $x[t]$ y tiempo continuo $x(t)$. Enfocamos en SLIT (Sistemas Lineales Invariantes en el Tiempo).

Señales: Patron de variaciones. Se representan como funciones de una o mas variables independientes.

Transformaciones de la variable independiente:
- **Reflexión o inversión temporal ($x[-n]$ o $x(-t)$):** Invierte la señal respecto al origen ($n=0$ o $t=0$), equivalente a reproducir una grabación en sentido contrario.
- **Escalamiento lineal de tiempo ($x(2t)$, $x(t/2)$):** Modifica la escala temporal comprimiendo o expandiendo la señal (por ejemplo, reproducir al doble o a la mitad de velocidad).
- **Desplazamiento en el tiempo ($x[n - n_0]$ o $x(t - t_0)$):** Mantiene la misma forma de la señal pero la traslada horizontalmente en el eje temporal. Resulta clave en aplicaciones como radar, sonar o procesamiento de señales sísmicas debido a las diferencias de tiempo de propagación entre receptores.

![[Pasted image 20261008121200.png]]

---

Sistemas: Proceso donde una señal de entarada x(t) se transforma en una salida y(t).
![[Pasted image 20261011152918.png]]

Señales: Describen fenomenos fisicos. Se representan como funciones de 1 o + variables dependientes respecto a 1 o + variables independientes.

Nos enfocamos en señales de una variable independiente (tiempo):
t -> Tiempo continuo
n -> Tiempo discreto (se toman muestras)

Transformaciones de señales en tiempo continuo:
- Desplazamiento:
  ![[Pasted image 20261011154024.png|187]]
  ![[Pasted image 20261011154055.png]]

- Escalamiento:
  ![[Pasted image 20261011154146.png]]
  ![[Pasted image 20261012184831.png]]
  
- Reflexion:
  
  ![[Pasted image 20261012184906.png]]
  ![[Pasted image 20261012184929.png]]
  
Procedimiento: Desplazamiento, Reflexion, Escalar.

Operaciones entre señales: Suma, resta y multiplicacion.

Escalon unitario μ(t)
![[Pasted image 20261014182034.png|381]]

Transformaciones en Escalon unitario
![[Pasted image 20261014182106.png]]
![[Pasted image 20261014182353.png]]

### Impulso unitario y desplazado

![[Pasted image 20261029204059.png|323]]

Desplazado
![[Pasted image 20261029204504.png|324]]

Para ser un impulso unitario tiene como CONDICION FUNDAMENTAL: Area=1, es decir la integral del impulso desde -inf a +inf debe ser 1.

![[Pasted image 20261029202844.png|369]]

Tambien se tiene el impuslo unitario desplazado delta(t-t0).

Representacion incremental del impulso
![[Pasted image 20261029203727.png|320]]![[Pasted image 20261029203816.png|333]]

### Escalon unitario y desplazado

![[Pasted image 20261029204024.png|307]]
DISCONTINUA EN t=0

Desplazado
![[Pasted image 20261029204227.png|307]]

Incremental
![[Pasted image 20261029204419.png|349]]

IMPORTANTE: t es asi
![[Pasted image 20261030121705.png|565]]

e elevado a -t es asi, si es t esta invertido
![[Pasted image 20261030121921.png|436]]

Si se hace sumatoria de impulsos obtengo un tren de impulsos.

El escalon unitario es la integral de la funcion impulso unitario
![[Pasted image 20261030132254.png|215]]

El escalon unitario es discontinuo en t=0, por lo que se hace el limite con el escalon unitario del incremento para cuando el incremento tiende a 0.
![[Pasted image 20261030132520.png]]

![[Pasted image 20261030134147.png]]


## Propiedades de los sistemas. SLIT. Convolucion

### Propiedades de los sistemas

- Sistemas con/sin memoria: Si la salida de un sistema en un tiempo t depende de la entrada en ese mismo instante de tiempo t, es sin memoria.
- Invertibilidad: Si a la salida de nuestro sistema y(t) le aplicamos otro sistema (el inverso), este arroja por salida a nuestra entrada original x(t). Debe producir salidas diferentes con entradas diferentes(Invertible). 
  ![[Pasted image 20261030152258.png]]
- Causalidad: Los valores de la salida en un tiempo t dependen de los valores de entrada en el mismo tiempo t y/o anteriores. Es con memoria. Se le llama no anticipativo por que no anticipa los valores futuros de la entrada.
  ![[Pasted image 20261030152455.png|334]]
- Estabilidad: La entrada es acotada para cualquier tiempo t, la salida tambien lo es para todo tiempo t. No puede volverse infinita la salida si la entrada fue finita.
- *Invarianza en el tiempo:* Cuando un desplazamiento en el tiempo de entrada produce el mismo desplazamiento en el tiempo de salida.
  ![[Pasted image 20261030154233.png|318]]
- *Linealidad:* Si conocemos 2 entradas de un sistema y sus respectivas salidas, se debe cumplir el Principio de Superposicion (La respuesta a una combinacion lineal de entradas sera la misma combinacion lineal aplicada a las salidas)
  ![[Pasted image 20261030155035.png]]

Sistema identidad: y(t)=x(t)

### Sistemas Lineales Invariantes en el Tiempo: SLIT

Una señal cualquiera en tiempo continuo puede ser descompuesta en una combinacion lineal de señales de impulsos desplazados en el tiempo y con altura x(kΔ).Δ
![[Pasted image 20261030165216.png|299]]

DESARROLLO EN HOJA

### Convolucion

y(t) = x(t) * h(t)

Si la entrada en un SLIT es el impulso unitario, la salida es la respuesta al impulso h(t). El sistema esta completamente caracterizado por h(t).

![[Pasted image 20261030180810.png]]




---

Para demostrar la integral de convolucion voy a escudriñamiento
Tener en cuenta en el elemento neutro, x(0).u(t) siendo x(0) la altura de la señal y u(t) el impulso, la multiplicacion es un impulso estirado, en criollo.

VER BIEN DEFINICION DE SERIE DE FOURIER, PARA QUE SE USA
Representar una señal periodica...

![[Pasted image 20261028145259.png]]
Prestar atencion a que no se superpongan para pasar al dominio x(t)


Enventanado: 

Responder UNICAMENTE lo que se le pregunta, en practico aplicar propiedades.