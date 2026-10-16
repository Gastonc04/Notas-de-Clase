## Diseño de un Framework de Persistencia
En el diagrama de secuencia se cuenta el proceso de persistencia de objetos, no lo habiamos incluido hasta ahora.

### Problema de impedancia
Surgen problemas de incompatibilidad entre ambos dominios (relacional y orientada a objetos).

Algunas diferencias:
- En BDR se almacenan datos en tablas
- Son tipos primitivos, no almacenan comportamiento
- Se debe transformar el Modelo de objetos a estructura de tablas
- Fuerte acoplamiento entre el sistema y el DBMS.
- 
### Mapeo del modelo OO a relacional
Mapeamos las clases de entidad (seran las persistentes).

Represetacion de Objetos como Tablas (VER PPTs):
- Si una clase tiene solo tipos de datos primitivos: Relacion 1:1.
- Si un atributo tiene multiples valores: Relacion a mas de una tabla, llevara a una clave compuesta. VER NUEVA RELACION.

Patron identificador de objeto (OID): Asignar un identificador de objeto a cada registro.

Mapeo de relaciones de asociacion: Patron Representacion de las relaciones de los objetos en tablas.
- Asociaciones 1..*
Mapeo de herencia a un modelo relacional:
No existe la herencia.

### Esquema de Persistencia

Persistencia del Modelo de Objetos (VA AL FINAL)
Soluciones posibles:
- Super objeto persistente: Todas las clases heredan de ese super objeto persistente ObjetoPersistente, heredando la implementacion de la persistencia.
- Servicio de persistencia: Subsistema de persistencia, se crea una capa que mapea las tablas y objetos.

Super objeto persistente: ObjetoPersistente tiene metodos genericos que luego se redefinen.

Servicio de persistencia: Almacenar (Desmaterializar) y recuperar (Materializar) los objetos. Confirmar y deshacer (commit y rollback).

Pasos para desarrollar un framework de persistencia:
- Correspondencia
- Identidada 