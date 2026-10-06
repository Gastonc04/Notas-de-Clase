## Patrones de diseño

### Strategy
Ejercicio Estrella de la Muerte

Estructura // Dinamica

Uso de la estrategia 11, 12 y 13.

Si se crea la estrategia en el paso 8, tengo los tributos necesarios. Si lo hago en el paso 11, debo poner un atributo que me indique esa informacion que me falta. En este caso metodoCalculoSeleccionado: String.

En el 95% de los casos, la logica que ejecuta el Gestor se la delega a la Estrategia. Prestar especial atencion a los parametros y a los retornos.

El metodo de calculo que cumple con la interfaz metodoCalculo, devuelve una matriz de String 

![[IMG_0128.jpeg]]

Ej. que tienen Strategy: Crustacio cascarudo, Frigorifico, Gestion de eventos.

## Observer
Cuando se necesita que objetos se enteren que cambio el estado de un sujeto. Cambia algo en la situacion del sujeto, atributos, valores.


Ej. con Observer: Frigorifico, Gestion de eventos.