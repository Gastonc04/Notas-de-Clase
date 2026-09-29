(Traer resuelto los proximos patrones)
## Patrones de diseño

### State
Patron de comportamiento. Resuelve la logica compleja de una clase, al estar en determinado estado se implementa una logica condicional. Se crea una nueva clase por estado.

Principios:
- Interfaz: Conjunto de firmas que van a ser implementadas (codigo) por clases.

	Tener una clase cliente (En terminos de C/S) que apunta a la clase interfaz que esta tenga clases que heredan e implementan el metodo de la interfaz.

- Delegacion: Hacer un pasamanos. Un objeto no hace nada cuando recibe el mensaje, y se lo pasa completamente a otro.

LEER 1ER CAPITULO DE GAUS, PARA PARCIAL 3 SI O SI

1) Hay que interpretar la consigna.
Por ejemplo en consultorio dice en la consigna: "...comportamiento variable...", esto es un indicio.

2) Lectura de CU asociado.
Caso de uso 3. Identificar cuando hay estado y comportamiento variable.
Paso 18 cumple.

3) Identificacion de las clases de analisis afectadas.
Contexto: Turno
Clases afectadas: CambioEstado, Estado, MotivoCancelacion (creo)

4) Identificar del fragmento de la comunicacion afectada (Secuencia o Comunicacion).

---

ANOTACION EN CARPETA

Hago para la clase estado una asociacion con cada de uno de sus estados (en la maquina de estados) como clases hijas, y agrego las clases afectadas (como MotivoCancelacion y CambioEstado).

Definir el tipo de dato de cada atributo en terminos representativos: String, array, date, integer, date time.
P. ej -> nombre: string

Poner operaciones del contexto en Estado y sus clases hijas. De esta manera existe cancelar() 
en todas las clases Estado pudiendo redefinirse con polimorfismo.

Metodo de enganche: es el metodo que tomamos a partir del cual redefinimos el proceso. En este caso es cancelarTurno().

El pseudocodigo no es contar el diagrama de secuencia.

A partir del metodo de enganche, ponemos todas las signaturas de los metodos en la clase GestorAusenciaProfesional.

CONSIDERACIONES:
Estado es una CLASE ABSTRACTA, ya que no hay instancias de el. NO PONER :Estado en un diagrama de secuencia en un patron STATE.
metodos buscaEstadoCancelado() NO PONER, ya que se va a encargar la clase abstracta de estado.
Se ELIMINA la dependencia del Gestor al Estado, no existe mas. NO PONER.

Los parametros del metodo cancelar(fechaHora: DateTime, motivo: MotivoCancelacion) se ponen como minima en todas las clases que redefinen el metodo.

![[IMG_9785.heic]]

![[IMG_9784.heic]]

En la clase abstracta el metodo puede ser concreto o abstracto.
El metodo concreto cancelar(...) lo voy a solamente redefinir en aquellas clases que puedan pasar al estado Cancelado.


Tips (Pseudocodigo):
- No contar el diagrama de secuencia.
- Explicar el codigo dentro de cada metodo.
- Explicar que hay una clase abstracta, explicar las clases concretas y la forma de implementacion de los metodos.
- Explicar como se ve el polimorfismo.
- Explicar como y donde esta la delegacion. Y a su vez decir que principios de diseño aplica (Solid, etc).


---


### Strategy