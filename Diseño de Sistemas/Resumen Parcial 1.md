Repaso POO

Objeto: elemento/unidad/entidad individual e identificable con un papel bien definido en el dominio. Puede ser real (Alumno) o abstracto (Inscripción).

Naturaleza de los objetos:

- Estado: Situación o condición en la que esta un objeto a lo largo de su ciclo de vida. Representados por los valores actuales de sus atributos.
    
- Comportamiento: Selectores (Solo muestran datos), Modificadores (Realizan una acción sobre las propiedades). 
    
- Identidad: No esta dada por los valores de los atributos, sino que esta dada por la posición de memoria a la hora de crear el objeto.
    

  

Clase: Definición de un conjunto de objetos que comparten atributos y comportamiento.

  

- Vista externa: Lo que todo los objetos de esa clase pueden hacer (comportamientos). Otra forma de verlo seria los servicios que puede ofrecer esos objetos a objetos de otra clase. Lo que esta publico.

  

- Vista interna: Todo aquello que permanece oculto: Implementación del comportamiento. Atributos.

  

Elementos esenciales:

- Abstracción: Características esenciales que lo distinguen de los demás. Fronteras conceptuales nítidamente definidas.
    
- Encapsulamiento: Ocultamiento de la información. Atributos y la implementación de los comportamientos.
    
- Modularidad: Propiedad que tiene un sistema que ha sido descompuesto en partes modulares altamente cohesivas y débilmente acopladas. Lo mas pequeño es una clase.
    
- Jerarquia: Ordenacion de las abstracciones. De clases (herencia), De partes (Agregacion/composicion).
    

  

Nota: Altamente cohesivo significa que los modelos están fuertemente relacionados. Bajo acoplamiento significa que haya la menor dependencia posible entre módulos.

  

Relaciones entre clases:

- Jerárquicas
    

- Herencia: Existe polimorfismo, un hijo puede redefinir el comportamiento adoptado de un padre.
    
- Agregacion/Composicion: Define un todo/parte. En el caso de composición, si se elimina una de las 2 deja de existir el otro. En el caso de agregación, puede existir una sin la otra.
    

- No jerárquicas
    

- Asociación: Especifica que los objetos de una clase están relacionados con los objetos de otra clase.
    

  

Nota: Polimorfismo, poli (múltiples) y morfismo (formas), quiere decir múltiples formas de realizar determinada operación.

Navegabilidad es hacia que clase se relaciona los objetos de una clase.

Multiplicidad es la cantidad de instancias de relación puede haber. EJEMPLO: ¿Cuantas inscripciones puede tener un alumno? -> 1.

  
  
  

Unidad 1

  

Flujo de análisis de trabajo - Diagrama de maquina de estados

  

El flujo de análisis estudia los requisitos capturados en la etapa anterior y los refina y estructura.

  

Lenguaje basado en un modelo de objetos conceptual denominado “Modelo de análisis”, que nos permite refinar los requisitos y razonar sobre aspectos internos del sistema.

  

Estructura del sistema obtenida:

- Basada en clases y paquetes.
    
- Vista interna del sistema.
    

  

Nota: La vista interna la vemos como colaboración entre objetos (implementación). 

  

Roles o trabajadores:

- Arquitecto (1)
    
- Ingeniero de casos de uso (2)
    
- Ingeniero de componentes (3)
    

  
  

Artefactos de analisis:

- Descripción de la arquitectura (1): Vista de modelo de analisis que muestra los artefactos mas significativos para la arquitectura.
    

- Realizacion de casos de uso (2): Colaboración que describe como se lleva a cabo y se ejecuta un CU mediante la interacción entre objetos.
    
- Clases de análisis (3): Organizado en paquetes de analisis.
    
- Paquetes de analisis (3).
    

3.Clases de análisis: Comportamiento definido mediante responsabilidades. Trata requisitos funcionales. Siempre entra en uno de estos 3 estereotipos:

3.Paquetes de analisis: Mecanismo lógico de agrupación de artefactos del modelo de análisis en piezas mas manejables. Puede contener: Clases de analisis, RCU, más paquetes de analisis.

  
  

Cada artefacto se realiza con esos diagramas UML. Los pintados de naranja son diagramas de vista estática, es decir estructurales (Diagramas de clases), y los mas claritos son de vista dinámica, porque modelan comportamiento (Diagrama Maq. De Estados). 

  

Maquina de Estados

  

Es un diagrama de comportamiento (o sea vista dinámica).

  

Definición: Especificación de una secuencia de estados por los que transita un objeto a lo largo de su vida en respuesta a eventos y su respuesta a dichos eventos.

  

Toda clase tiene una UNICA Maquina de estados.

  

Estado

Condicion en la vida de un objeto durante la cual satisface una condición, realiza una actividad, o espera un evento.

  

Recordar que el estado de un objeto se representa por los atributos + valores actuales de los mismos.

  

Permanece en un estado por tiempo finito.

  

Notación camelCase.

  

Estado inicial/final son pseudoestados. 

  

Pueden haber subastados.

Transición

Relación que une 2 estados que indica que un objeto esta en un estado y realiza una acción para posteriormente pasar al otro estado al suceder un evento especificado que satisfaga una condición.

Tiene:

- Estado origen
    
- Evento de disparo
    
- Condiciones de guarda
    
- Efecto o acción
    
- Estado destino 
    

  

Sintaxis:

nombreEvento (lista de parametros opcional) [condiciones de guarda opcional] / lista de acciones opcional

  
  

Evento

Estimulo que hace que un objeto transite de un estado a otro.

  

Tipos:

- Eventos de llamada <-
    
- Eventos de señal
    
- Eventos de cambio
    
- Eventos de tiempo
    

  

Eventos de llamada: Peticion u operación que debe estar definida en la clase. Recibir un evento de llamada es un activador para que se ejecute una operación.

  

Nota: Cuando quiero guardar los estados por los que transitó un objeto (fechas), hago un objeto CambioEstado[NombreClase].

  

——————

  

Estados compuestos. Se componen de subastados, los cuales pueden ser concurrentes o secuenciales <-. Los secuenciales como su nombre lo indica se hace en secuencia, los concurrentes se hacen en paralelo (no lo trabajamos).

  

Si un estado apunta a un sub estado, va hacia el.

Si un estado apunta al estado compuesto, va al primer sub estado.

Si un estado compuesto apunta a otro estado, todos sus sub estados pueden transitar a el.

  

Estado de historia (H). Recuerda el ultimo subastado en el que estaba antes de abandonar el estado compuesto.

H *: Historia profunda. Es decir que si un sub estado a su vez también era estado compuesto, recuerda en que sub estado del mismo estaba parado.

  

Los eventos de la maquina de estados DEBEN estar en el diagrama de clases como métodos.

DEBE haber un atributo Estado en la clase correspondiente.

DEBE haber al menos un caso de uso que se relacione con los métodos que provocan cambio de estado.

  

UML 2.0

  

Para que modelar?

Ayudan a visualizar como es o queremos que sea un sistema.

Permiten especificar la estructura y comportamiento de un sistema

Proporcionan plantillas para la construcción de un programa.

Documentan las decisiones tomadas.

  

UML es un lenguaje unificado de modelado estandarizado para escribir planos de software.

  
  
  

UML permite:

- Visualizar: Provee una serie de modelos.
    
- Especificar: Detrás de cada elemento hay una especificación o detalle
    
- Documentar
    
- Construir: Mediante la interpretación de modelos, podemos escribir código.
    

  

Se dice unificado porque permite modelar cualquier dominio o sistema de información.

  

Soporta cualquier lenguaje de programación, muchos procesos de desarrollo.

  

Autores de UML (La suma de ellos dieron lugar a UML):

- Grady Booch
    
- Ivar Jacobson
    
- James Rumbaugh
    

  

 La diferencia con la 1.0 es que hay mucha mas sintaxis, es mas extensible, captura mas comportamiento.

  

MDA - Model Driven Arquitecture: Vision de como llegar al software a través de los modelos.

  

Estructura de UML:

- 1. Bloques de construcción
    
- 2. Mecanismos comunes
    
- 3. Reglas
    

  

1. Bloques de construcción
    

  

Elementos:

- Estructurales:
    

- Clase
    
- Interfaz
    
- Colaboración
    
- Casos de uso
    
- Clase activa
    
- Componente
    
- Artefacto
    
- Nodo
    

- De comportamiento:
    

- Interacción
    
- Maquina de estado
    
- Actividad
    

- De agrupación:
    

- Paquete
    

- De anotación:
    

- Nota (se utiliza en casos de que UML no contemple en sus elementos algo que requiera modelarse)
    

Elementos estructurales

  
  
  
  
  
  
  

Elementos de comportamiento

En cada uno se pone énfasis en cosas distintas.

  

En el de interacción se pone en el conjunto de objetos que interactúan.

En la M.E se pone en el ciclo de vida de un objeto.

En la actividad, se pone en los flujos entre los pasos de un proceso, acción, etc sin mirar el objeto.

  
  
  

Relaciones

  

Asociacion, agregacion, composicion y generalizacion ya hemos usado en diagramas de clases.

Dependencia, asociacion y generalizacion las hemos usado en diagramas de CU.

Ahora sumaremos dependencia y realizacion a diagramas de clases (clases que implementan un metodo definidos en una interfaz). Al hacer realizacion de CU.

  

Diagramas

  

Representacion grafica de un conjunto de elementos que permiten visualizar un sistema desde diferentes perspectivas.

  

  

2. Mecanismos comunes
    

  

Especificaciones: Detras de cada notacion grafica hay una especificacion con una explicacion textual de la sintaxis y semantica de ese bloque en construccion.

  

Adornos: Todos los elementos en la notacion comienzan con un simbolo basico al cual pueden añadirse una variedad de adornos especificos a ese simbolo.

Divisiones comunes: 

- Clasificador/instancia (ej: Clase/objeto)
    
- Interfaz/implementacion (ej: CU/Colaboracion, Operacion/Metodo)
    

  

Mecanismos de extensibilidad: Es posible extender el lenguaje de manera controlada mediante los mecanismos de extension:

- Estereotipos (ej: interfaz, control, entidad)
    
- Valores etiquetados
    
- Restricciones
    

  

3. Reglas
    

  

Semanticas para:

- Nombres: Como llamar a los elementos, relaciones, diagramas.
    
- Alcance: Contexto que le da significado al nombre.
    
- Visibilidad: Como se pueden ver y utilizar esos nombres (publicos, privados, etc).
    
- Integridad: Como se relacionan apropiada y consistentemente unos elementos con otros.
    
- Ejecucion: Que es ejecutar un modelo dinamico.
    

  

—---------

  

Arquitectura del sistema:

  

1. La organización de un sistema de software: Es la forma en que divides todo el sistema en piezas más pequeñas.

  

2. La selección de elementos estructurales y sus interfaces: Aquí decides qué componentes usarás (por ejemplo, una base de datos SQL, un motor de búsqueda, una API externa) y cómo se van a conectar con el resto del sistema.

Interfaces: Son las "puertas" de entrada y salida. Definen cómo una parte del sistema puede hablar con otra sin necesidad de conocer cómo funciona la otra por dentro.

  

3. Su comportamiento (colaboraciones entre elementos): No basta con que los elementos existan; deben trabajar juntos. Esto describe el flujo de información. Por ejemplo: cuando el usuario presiona "Comprar", ¿qué mensaje envía el Carrito a la pieza de Pagos? ¿Cómo responden?.

  

4. La composición en subsistemas cada vez más grandes: El software se construye por capas o niveles (jerarquía).

- Pequeños componentes se agrupan para formar módulos.
    
- Varios módulos se agrupan para formar subsistemas.
    
- Varios subsistemas forman el sistema completo.
    

Esto ayuda a manejar la complejidad: si tratas de entender todo el sistema a la vez, es imposible; si lo ves nivel por nivel, es mucho más sencillo.

  

5. El estilo arquitectónico que guía esta organización: Es la "filosofía" o el patrón que elegiste para que todo sea coherente. Algunos ejemplos famosos son:

- Cliente-Servidor: El modelo clásico donde uno pide y el otro responde.
    
- Microservicios: Dividir todo en servicios pequeñitos e independientes.
    
- Capas (Layered): Separar la interfaz de usuario de la lógica de negocio y de los datos.
    

El estilo actúa como una guía para que, cuando necesites añadir algo nuevo, sepas dónde y cómo encajarlo sin romper la lógica del sistema.

  
  

Vistas en UML:

  

  

Es una forma de organizar la documentación de un sistema complejo mirando el mismo problema desde 5 perspectivas diferentes para que todos (desarrolladores, clientes, usuarios) entiendan lo mismo.

  

Imagina que estás diseñando un edificio: necesitas planos de arquitectura, planos eléctricos, de cañerías, etc. Aquí es igual.

  

Las 5 Vistas

1. Vista de Casos de Uso (La central - El "Qué"): Es el corazón de todo. Describe qué hace el sistema desde el punto de vista del usuario. Si esto no está claro, el resto no sirve.
    

  

2. Vista de Diseño (El "Cómo lógico"): Aquí definimos la estructura interna: clases, objetos y cómo se organizan. Es el plano de la lógica del software.
    

  

3. Vista de Procesos (El "Cómo dinámico"): Se enfoca en el movimiento: cómo fluye la información, hilos (threads), concurrencia y sincronización. Es ver cómo el software "se mueve" mientras se ejecuta.
    

  

4. Vista de Implementación (El "Cómo se construye"): Es el mapa de los archivos físicos: librerías, módulos, componentes. Es cómo empaquetamos el código para que sea funcional.
    

  

5. Vista de Despliegue (El "Dónde se instala"): Es el plano del hardware. ¿En qué servidores, computadoras o dispositivos va a vivir y ejecutarse todo esto?
    

  

Flujo de análisis de trabajo - Diagrama de comunicación y Diagrama de clases de analisis

  

Analizar un caso de uso

- Identificar clases de analisis participantes: Diagrama de clases de analisis (Las clases que intervienen en la realizacion del CU).
    
- Describir interacciones entre objetos de analisis: Diagramas de interaccion.
    

  

Clases de analisis participantes

Nota: si hay un sistema experto (o sistema externo) como generar factura con AFIP, me tengo que comunicar a traves de una interfaz, asi que se modelará otra interfaz. Pueden ser impresora o generador de pdf tambien.

*por ahora solo utilizaremos una ventana.

  

Interacciones entre objetos de analisis.

A traves de diagramas de interaccion, sea diagrama de comunicacion y/o diagrama de secuencia.

  

Los 2 tienen en comun que muestran la interacción entre OBJETOS. Las clases estan en tiempo de diseño.

  

Sintaxis de la instancia de un objeto:

por ejemplo:

  

el mensaje es una flecha que va hacia el objeto que recibe dicho mensaje. Es el comportamiento que puede ejecutar el que recibe.

  

  

Por ej: solicitarDocumentoContribuyente() lo ejecuta VentanaNuevoContribuyente, no ControladorNuevoContribuyente.

ConfirmacionIngresada() lo ejecuta ControladorNuevoContribuyente.

  

TODOS los mensajes que recibe un objeto DEBEN estar definidos con el MISMO nombre en la clase de analisis correspondiente.

  

Ejemplo de descripcion de CU

  

Nota: Dividir por momentos la descripcion ayuda a la legibilidad. Por ej: ingresar a la opcion, solicitar datos de algo, solicitar confirmacion, fin de CU.

  
  
  
  
  
  
  
  

Primeramente, la interfaz debe tener un habilitar() para disponer los elementos visuales habilitados en primera instancia en forma de ciclo.

  

1RA SECCION DE LA DESCRIPCION DEL CU

Como se ve ahí en el 2. está habilitando los elementos visuales en primera instancia (por ej: “guardar” no estará habilitado hasta mas adelante).

El controlador lleva un ordenamiento de la logica del CU, luego colaborará con otros objetos.

Cuando se envia un mensaje a muchos objetos, como en el 8. se coloca un *.

  

2DA SECCION DE LA DESCRIPCION DEL CU

Ingresando los datos 11. se necesita buscar las provincias, sigue siendo una logica del CU 12.buscarProvASelecc() mediante un metodo 13.*mostrasNombre() a objetos provincias.

Luego la interfaz pide seleccionar una 14.pedirSeleccionProvincias(), el actor selecciona una 15.seleccionarProv() y se pasa al controlador la provincia seleccionada 16.provSeleccionada().

  

Aca hay que buscar localidades de la provincia que se seleccionó 17 (va a haber un objeto NUEVO llamado seleccionada:Provincia ya que ya no hablo con todas los objetos provincia sino que solo con uno), se muestran localidades 18, se muestran los nombres al objeto localidad 19.*.

Luego de la misma forma que la provincia, se pide seleccionar una 20, se selecciona 21, y se pasa la localidad seleccionada al controlador 22.

  

3RA SECCION DE LA DESCRIPCION DEL CU.

Ahora se pide la confirmacion del registro 23, se confirma 24, se pasa al controlador 25, y el controlador registra el contribuyente y va a un nuevo objeto “nuevo:Contribuyente” a través del mensaje 27.crear().

  

A su vez, existe una responsabilidad conocer a “Domicilio” en el diagrama de clases de analisis, quiere decir que se debe crear tambien el objeto domicilio del contribuyente.

  

por lo tanto el mismo objeto nuevo:Contribuyente va a crear el domicilio 28.crearDomicilio() a traves del mensaje 29.crear() al objeto “Domicilio”.

  

por ultimo, el controlador ejecuta el fin del CU a traves de 30.finCU().

  

finalmente todos los métodos incluidos en el diagrama de clases de analisis para este CU quedaria asi.

  

Las relaciones de <<control>> y <<boundary>> son dependencias porque ambos objetos existen en tiempo de ejecucion del CU, si fueran de asociacion peristirian.

  

Los atributos de <<control>> son las listas, atributos (datos) que van pasando de los objetos al controlador y los ingresados por el actor que a son pasados por la interfaz.

  

Consideraciones!!!

NUNCA un objeto <<entidad>> le manda un mensaje a <<control>>.

  

Un <<boundary>> puede mandar mensaje al actor SOLAMENTE cuando el actor es un sistema o dispositivo hardware.

Un objeto NO BUSCA objetos de la misma clase, a menos que haya una asociación reflexiva.

  

Al llamar a otro CU, se modela como un SELF en el objeto <<control>>.

  
  
  
  
  

Cuando hay una relacion de agregacion, el controlador accede al TODO y este a su PARTE.

  

Flujo de análisis de trabajo - Diagrama de secuencia

  

El diagrama de secuencia nos muestra las interacciones entre lineas de vida como una secuencia de eventos ordenada en el tiempo.

  

La linea de vida es la existencia de un rol en un tiempo particular.

El nombre es opcional, solo es necesario cuando se quiere colaborar con un subconjunto u objeto en particular (seleccionado por ejemplo).

  
  

Signatura de mensajes.

  
  
  

Tipos de mensaje:

  

sincrono: espera una respuesta.

  

asincrono: en tiempo real, no espera.

  
  
  
  
  
  
  
  

Foco de control es el periodo de tiempo durante el cual un objeto ejecuta determinada acción.

  
  

Fragmentos combinados: Agrupación de comportamiento, se presenta como región anidada dentro del diagrama de secuencia.

Tienen:

- Operador: como se ejecutan los operandos.
    
- Uno o + operandos
    
- Cero o mas condiciones de protección
    

  

Hay 13 operadores. Veremos los mas comunes:

- loop: bucle, min max [condicion]
    
- opt: opcion, se ejecuta un solo operando si la condicion es verdadera. Equivalente a if.
    
- alt: alternativa, se ejecuta que tenga la condicion verdadera. Permite tener varios operandos y si se quiere, un else si no cumple ningun operando verdadero. Equivalente a if-else o switch-case.
    

  

Tipos de loop

  
  
  
  
  

Llamada de un CU

  
  

Patrones GRASP

  

Patrones de Software para Asignacion de Responsabilidades Generales.

A la hora de asignar responsabilidades a los objetos en el diagrama de interaccion.

  

RECORDAR: Una responsabilidad es un contrato u obligacion del clasificador.

Hacer algo el mismo objeto: Ejecuta una lógica interna propia. Ej: mostrarNombre(), calcularAlgo().

Iniciar una accion en otros objetos: Envía un mensaje a otro objeto para que este trabaje. Ej: mostrarDomicilio().

Coordinar y controlar actividades en otros objetos: Actúa como "director" de orquesta, decidiendo el flujo entre varios objetos. Ej: controladorPagos, gestorRegistro. Puede ser otro tambien.

  

Conocer datos privados: Son sus propios atributos básicos. Ej: getNombre(), mostrarTelefono().

Conocer los objetos relacionados: Tiene referencias o punteros a otros objetos con los que colabora. Ej: setDomicilio().

Conocer las cosas que puede derivar o calcular: No guarda estos datos, pero sabe cómo obtenerlos basándose en lo que ya conoce. Ej: calcularSaldo().

  

Experto en informacion

  

Asignar la responsabilidad a la clase que cuenta con la informacion necesaria para cumplir con la responsabilidad.

  

  

Creador

  

Quien deberia ser responsable de crear una nueva instancia de una clase?

Asignarle a la clase B la responsabilidad de crear una instancia de la clase A cuando:

  

Si no estuviese asignarDomicilio() NO FUNCIONA.

  

No respeta patrones GRASP. Genera dependencia entre el controlador y domicilio, y además el controlador necesitaria saber como se guardan los datos del domicilio en el contribuyente (lo cual deberia ser responsabilidad de contribuyente).

  

  
  
  

Controlador

  

Quien se deberia encargar de atender un evento del sistema o caso de uso? Un manejador artificial.

  

El simple hecho de que exista un controlador en el diagrama, ya cumple con el patron.

Si no hubiese un manejador habria acoplamiento entre la capa de presentacion y la capa de la logica de negocio.

Bajo acoplamiento

  

Como dar soporte a una dependencia escasa y a un aumento de reutilizacion?

Asignar una responsabilidad para mantener bajo acoplamiento.

  

  

  
  

No cumple con bajo acoplamiento… por lo tanto genera dependencias entre el gestor/controlador con otras clases de entidad.

  

Se podria evitar aprovechando cada clase que conoce a otra con la que esta relacionada.

  
  
  
  

Asi sí

Alta cohesion

  

Como mantengo una complejidad manejable?

Para evitar que sean:

- Dificiles de entender
    
- Dificiles de reutilizar
    
- Dificiles de conservar
    
- Sensibles a cambios
    

  

Debo asignar una responsabilidad para garantizar la alta cohesion.

Es decir que una clase debe presentar un número relativamente pequeño de métodos, con funcionalidades altamente relacionadas. Se busca que la clase cumpla únicamente su función.

  

Este si cumple. Hay que fijarse una vez terminado el diagrama de clases de analisis. Si hubiese una clase que tiene un metodo que no deberia estar ahi o no tiene mucho sentido, seguramente este generando baja cohesion a los otros metodos de la misma clase.

  

EJEMPLO DE APLICACION DE PATRONES GRASP

Rosa - Controlador

Violeta - Bajo acoplamiento

Verde - Creador

Naranja - Experto en informacion

Hay alta cohesion porque se aplican los anteriores.

  

Anotaciones práctico

  

En una relacion todo/parte, la parte tambien puede conocer atributos del todo.

  

En el ejemplo, si corte vacuno quiere saber la fecha de ingreso, puede conocerla.

  
  
  
  

Todos los eventos de cambio de estado TIENEN que estar en la clase correspondiente en el modelo de dominio para que este de soporte a la maquina de estado.

  

En el modelado de dominio, las clases con la que una esta relacionada no se modelan como atributos por “Convenciones de modelado”, sino que se coloca sobre la relacion el nombre.

  

Ademas los metodos new(), delete(), getAtributo(), setAtributo(), getClaseAsociada(), setClaseAsociada() se colocan en una clase y aclarando en una nota, se generaliza para todas las demas clases.

  
  
  
  
  
  
  

Cuando se manda un mensaje a un conjunto de objetos y es solo un mensaje, podemos utilizar el *. Pero en caso de que sea mas de un mensaje se hace un fragmento loop.

  
  
  
  
  
  
  
  
  
  
  
  
  
  
  

**Me quedo en video 4. Realizar modelo dominio museo pictorico.

  

Generalmente en la descripción del CU, cuando dice el sistema hace tal cosa, es una accion del manejador.