Diseño

Tiene como entrada el modelo de analisis. Transforma un modelo logico (modelo de analisis) en un modelo fisico, teniendo en cuenta las restricciones del negocio.

Es un proceso iterativo.

Modelo de analisis: Enfoque en resolver RF. Modela la solucion en terminos logicos.

Modelo de diseño: Modela la solucion en terminos fisicos.  

El software no es un modelo fisico, es intangible.

Analisis y Diseño en el PUD (Proceso Unificado de Desarrollo)

![](https://docs.google.com/docs-images-rt/ALKuztbat0W7UCyCx_xhUM6vGxun4xysbkfOQjqVp09h6zuBwsP1XyE2DhtwZs_pHIzW-WVsmL1HU9V23YkGdYCp2l0RvWtog-4at4y-b8mzOMzOgVfWkV2CF3epbstqs_LFnPPl-ksLhWMJSZ-7aIVbgXatUdkyhLWFhn-c7ZAEXg=s2048)

Refinamiento: Mas nivel de detalle, menos abstracto.

PREGUNTA EN PARCIAL

Aspectos a diseñarse (todos deben diseñarse):
- Arquitectura (primordial)
    
- Datos
    
- Procesos
    
- Formas de E/S
    
- Interaccion H-M
    
- Procedimientos manuales (no va a ser software necesariamente)

Diseño arquitectonico: Da respuesta a los RF con decisiones globales.

Diseño de datos: Transforma los RF en estructuras de datos para hacer persistente el software. Bases de datos relacional.  

Diseño de los procesos: Profundizar RF, persistencia, concurrencia. Descripcion procedimental de los componentes de software.

Diseño de Interaccion Humano-Maquina: Diseño, evaluacion e implementacion de sistemas computacionales interactivos para uso humano.

NOTA: Usuario cautivo - Cuando el cliente no tiene alternativa de usar otra aplicacion. Por ejemplo la autogestion.

Diseño de Formas de Entrada / Salida: Describe como se ingresa la informacion y como se presentan las salidas del mismo. Un sistema que se entera en el momento lo que está ocurriendo es un Sistema En Linea. En cambio cuando se entera despues, es un Sistema En Lote / Batch.

Diseño de Procedimientos Manuales: Describe como se integra el software al sistema de negocio.

---
# Practico

## Monolitica

### Vista de funcionalidad

Menor cantidad de CU que contemplen los RNF. Justificar.

### Vista de diseño

![[Pasted image 20260923165032.png]]

Componente de presentación para cada tecnología por subsistema.
![[Pasted image 20260923165215.png]]

### Vista de despliegue
La cantidad de servidores para hacer el despliegue será la que esté explicitada, si no está explicitado, entonces se recomiendan las buenas prácticas de separar las capas de software en niveles de hardware diferentes.

Para los nodos que representan servidores externos se espera que se identifiquen los componentes que se deducen explícitamente del enunciado, de lo contrario los servidores externos podrán quedar sin componentes.

Despliegue vinculado al RNF de Base de datos espejada (Mirroring). Si hubiera un RNF vinculado a espejar bases de datos, eso se ve reflejado en la Vista de Despliegue y la base de datos espejo debe estar en otro servidor diferente del que está alojada la base de datos y estar vinculada con el servidor de aplicaciones.

![[Pasted image 20260923172652.png]]

## Micrservicios

Cada unidad funcional es un servicio que se representa como subsitema/componente

Descomposicion por subdominios:
- CORE: Distingue la organizacion de la competencia
- SOPORTE: Contribuyen al core.
- GENERICOS: Comunes a otros negocios, pueden ser externalizados.

### Vista de diseño global
Los servicios provistos por terceros, externos, aparecen en esta vista y luego en la vista de despliegue, en la vista de diseño detallada no aparecen.

![[Pasted image 20260923175436.png]]

- Uso de API y/o API REST: en el glosario de la Cátedra en la UV hay definiciones respeto de estos recursos, la convención acordada en la cátedra es que cuando se necesita explicitar que se trabaja con comunicaciones asincrónicas optamos por API REST. Si no se explicita se puede usar API. Si bien la tendencia actual es hacia el uso de API REST.
- Vamos a trabajar microservicios para el backend con un único front, por ahora, micro front ends lo trabajaremos más adelante.
- Las interfaces de comunicación de los servicios que se comunican con el API Gateway o con el Backend for Frontend será por medio de API Rest. Esto privilegia las comunicaciones asincrónicas.
- Las interfaces de comunicación en los gateways son requeridas y la parte de front y los servicios tanto internos como externos tienen las interfaces provistas.
- Para la comunicación entre servicios internos del producto consideramos que los servicios de dominio genéricos son los que ofrecen, es decir tienen las interfaces provistas y analizamos quienes necesitan y ubicamos las interfaces requeridas.
- Para la comunicación con los servicios externos en la API Gateway Pública se ubican las interfaces requeridas, una por cada servicio externo, por ejemplo Servidor de Correo, Google Maps, MercadoPago, etc.; que en este caso quedarán sin interfaz provista. A su vez cada uno de los servicios que interaccionan con los servicios externos (que por lo general son servicios de domino genérico se integrarán también a la API Gateway Pública.
- Las interfaces salen del servicio, que está encapsulado, no desde los componentes que hay dentro del servicio.
- La comunicación entre servicios de dominios core y dominios de soporte por intercambio de información o actualización de datos en las respectivas bases de datos no los vamos a modelar por ahora, se asume que la comunicación es por la API Rest de cada servicio que se conecta al API Gateway. Esto es una simplificación, de lo contrario deberíamos incorporar otros patrones (SAGA, CQRD, Messaging) y sería muy complejo.
- Respecto a la forma de estructurar cada servicio, recordar que la modularización de los servicios
debe mantener la cohesión lo más alta posible. En ese sentido se recomienda que los componentes
que manejan lógica de conversión o que dependen de sistemas externos no se ubiquen dentro de
los servicios de tipo core.
### Vista de despliegue

### Vista de despliegue



Identificacion de RF (en los CU) y RNF (en listado) significativos para la arquitectura

Criterios:
- CU que resuelva ABMC (+ Representativo -> + Compleja del dominio)
- Tx (Generalmente 1)
- Reportes (Generalmente 1)
- Estadisticas
- Manejo de sesion
- Automaticos
- Masivos

Elegir cuales y JUSTIFICAR en una tabla.

Elegir un framework (Patrones arquitectonicos)
- N - Tier
- Messaging
- Publish - Suscribe
- Broker
- Process Coordinator

