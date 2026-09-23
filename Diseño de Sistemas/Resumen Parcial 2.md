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
- SOPORTE: 
- GENERICOS: 

### Vista de funcionalidad



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

