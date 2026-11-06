## Principios SOLID

Principios y buenas practicas en el diseño y la programacion O.O. Permite la creacion de software de calidad, legible, reusable, escalable.

SRP: Single Responsaibility. Responsabilidad unica. Enfocado a que una clase nunca debe tener mas de una razon para cambiar. Evitar clases que hagan cosas que deberian hacer otras.
OCP: Open/Close. Abierto/cerrado. Las entidades de software deberian mantenerse abiertas a la extension y cerradas a la modificacion. Preparar el codigo para modificarlo mediante: Herencia, Polimorfismo, Composicion. Logica extensible en nuevas clases. 
LSP: Likov Substitution. Sustitucion de Liskov. Las funciones que usen referencias a clases base deben ser capaces de usar objetos de clases derivadas de estas sin saberlo. Imaginar una clase con herencia a varias subclases con un metodo redefinido en cada una de ellas.
I
D

## Patrones de diseño
Son descripciones de clases y objetos relacionados que están particularizados para resolver un problema de diseño general en un determinado contexto.

Nomina, abstrae e identifica aspectos clave de una estructura de diseño. Sean clases, instancias participantes, roles, colaboraciones y responsabilidades.

Aborda un problema en concreto, describiendo cuando aplicarlo, consecuencias, ventajas e inconvenientes.

Elementos esenciales:
- Nombre
- Problema
- Solución
- Consecuencias

Plantilla de definicion:
- Nombre
	- Propósito
	- Sinónimos
- Problema
	- Motivación
	- Aplicabilidad
- Solución
	- Estructura
	- Participantes
	- Colaboraciones
	- Implementación
- Consecuencias
	- Ventajas
	- Inconvenientes
- Ejemplo de Código
- Usos conocidos
- Patrones relacionados

Patrones de diseño que resuelven:
- Encontrar los objetos apropiados: Implica descomponer sistema de objetos, Clases de analisis vs. Clases de diseño (clave para sistema mas flexible).
  
- Determinar granularidad: Los objetos varian en tamaño y numero. 
  
- Especificar interfaces: Los objetos SOLO se conocen a traves de su interfaz. Recordar que la interfaz es el CONJUNTO de todas las signaturas definidas por las operaciones de un objeto.
  
  _nombreOp (par1 : tipoPar1; par2:tipoPar2):tipoValorRetorno_ -> No dice nada de su implementacion, entonces, cualquier objeto puede tener la misma firma pero distinta implementación.
  
  Se debe identificar los parámetros los tipos de datos, el acceso a ellos, ya sea público o protegido.
  
- Especificar implementacion de clases: la implementación de los objetos que han definido por sus clases, y a su vez, los patrones nos ayudan a definir estas clases participantes.
  
  Cabe destacar que se vea diferenciar entre la herencia de clases y la herencia de interfaces. 
  
- Un principio del diseño orientado a objetos reutilizable dice: programar para una interfaz, no para una implementación.
  
  Los clientes deben interactuar y referenciar objetos a través de sus interfaces o clases abstractas en lugar de sus clases concretas, evitando así que necesiten conocer la implementación específica de cada objeto.
  
- Favorecen la reutilizacion:
	- Reutilizacion de caja blanca (herencia - ES UN): Interior de clases padres visibles a subclases.
		- Definición estática
		- Sencilla de usar
		- Es fácil modificar la implementación estáticamente no en tiempo de ejecución
		- Rompe el encapsulamiento
		  
	- Reutilizacion de caja negra (composicion - TIENE UN): Detalles internos de objetos no son visibles.
		- Definición dinámica
		- Uso más complicado
		- Es posible cambiar la implementación en tiempo de ejecución
		- Requiere que se satisfaga cierta interfaz
		- No rompe el encapsulamiento
	
	![[Pasted image 20261104020700.png]]
	
	Favorecer la composición de objetos frente a la herencia de clases.
	
	Delegacion: Un objeto receptor delega operaciones en su delegado. se obtiene software más flexible (dinámico y altamente parametrizado) pero más difícil de entender.
	
	![[Pasted image 20261104021512.png]]
	
	Interfaz: El cliente usa una interfaz como "puente" sin saber que objetos estan por detras implementados.
	
	![[Pasted image 20261104022721.png]]
	
	Finalmente: Delegacion + Interfaz
	
	![[Pasted image 20261104023317.png]]
	
- Diseñar para el cambio: Anticiparse a nuevos requisitos y cambios para una correcta evolucion. Cada patron permite que ciertos aspectos puedan cambiar independientemente de otros aspectos.

Causas comunes para rediseño:
* **Crear un objeto indicando la clase**: *Abstract Factory*, *Factory Method*, *Prototype*
* **Dependencia de operaciones concretas**: *Chain of Responsibility*, *Command*
* **Dependencia de plataformas hardware o software**: *Abstract Factory*, *Bridge*
* **Dependencia sobre representación de objetos**: *Abstract Factory*, *Bridge*, *Memento*, *Proxy*
* **Dependencias de algoritmos**: *Builder*, *Iterator*, *Strategy*, *Template Method*, *Visitor*
* **Acoplamiento fuerte entre clases**: *Abstract Factory*, *Bridge*, *Chain of Responsibility*, *Command*, *Facade*, *Mediator*, *Observer*
* **Añadir funcionalidad mediante la herencia**: *Bridge*, *Chain of Responsibility*, *Composite*, *Decorator*, *Observer*, *Strategy*
* **Incapacidad de cambiar clases convenientemente**: *Adapter*, *Decorator*, *Visitor*

Criterios:
- Proposito: Creacion (de objetos), Estructural (composicion de clases u objetos), Comportamiento (interaccion y reparto de responsabilidad entre clases y objetos).
- Ambito: Clase (relaciones de herencia, estaticas), Objeto (relaciones entre objetos, dinamicas).

![[Pasted image 20261104143847.png]]

Patrones de creacion:
Abstraen el proceso de creacion de objetos. Si es de clases, usa herencia. Si es de objetos, delega la instanciacion a otro objeto. Flexible en qué, quién, cómo y cuando lo crea. Se encapsula que clases concretas usa el sistema y como se crean las instancias a esas clases.
- Abstract Factory: Proporciona un contrato para la creación de familias de objetos relacionados o dependientes sin tener que especificar su clase concreta.
- Builder: Armar objetos complejos paso a paso, separando las partes del armado del resultado final para poder crear distintas versiones del objeto usando el mismo proceso.
- Factory Method: 

Enlace dinamico: asociación en tiempo de ejecución entre una petición a un objeto y una de sus operaciones.

Polimorfismo: Permite sustituir objetos en tiempo de ejecución por otro con la misma interfaz.

Interfaz: Es una colección de operaciones con un nombre, que se usa para especificar un servicio de una clase o de un componente. Sumatoria de todas las firmas de las operaciones.

La idea clave es separar la especificación de funcionalidad (la interfaz) de su implementación por un clasificador (como una clase o subsistema).

## Diseño de experiencia de usuario


## Diseño de persistencia

