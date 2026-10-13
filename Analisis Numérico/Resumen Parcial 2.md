
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

