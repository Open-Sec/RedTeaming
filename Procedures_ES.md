# EJECUCIÓN DE PROCEDIMIENTOS

Esta es la etapa de ejecución de acciones de la operación y las variantes son muchas por varios factores que se pueden resumir en dos :

- Por los resultados de las etapas anteriores.
- Por el tipo de escenario a desarrollar.  

De la forma más simple, los escenarios a desarrollar dependen del requerimiento específico de la organización a evaluar o del entendimiento del red team respecto a qué es lo mas adecuado.  Puede ser más complejo sí se consideran servicios recurrente o contínuos y más aún en los permanentes.

Tres escenarios típicos son :

- Compromiso Completo
- Brecha Asumida
- Brecha Personalizada

Aca se puede ver una diferencia con etapas anteriores dado que el **DISEÑO DE VECTORES DE ATAQUE** desprende dos secuencias en paralelo :

- **COMPROMISO INICIAL**
- **INSTALACIÓN**

Más allá de las consideraciones indicadas anteriormente, siempre se considera que habrá un **COMPROMISO INICIAL** que es el punto de partida de todas las acciones del ejercicio en curso así no corresponda a un Compromiso Completo.

El módulo de **INSTALACIÓN** consiste en todas las acciones necesarias para tener un Centro de Comando y Control (C2) de la forma adecuada.
La simplicidad o complejidad del mismo fue definida en la etapa de **VERIFICACIÓN DE TÉCNICAS ADECUADAS**.

Los otros dos módulos, **DESPLAZAMIENTO LATERAL** y **PERMANECER Y EXFILTRAR** se dan como una consecuencia natural, pero, ordenada de los módulos anteriores.  
No resulta inteligente pensar que habiendo conseguido un "pie" (por más que sea altamente privilegiado) dentro de una organización, no se va a considerar ingresar con el "cuerpo" entero y esto es lo que da pie al desplazamiento de forma natural, pero, es una acción que permite obtener la permanencia deseada dentro de la organización para acciones como la exfiltración de información.

## COMPROMISO INICIAL

Sin importar los escenarios a desarrollar, siempre se deben tener varias alternativas de **COMPROMISO INICIAL** y, de ser posible más de una del mismo tipo.
Las razones son diversas, pero, nuevamente se pueden resumir en dos :

- Por mas planeamiento que se haya realizado, algunas condiciones pueden cambiar mientras se ejecutan las acciones de la operación.
- Distracción como cuando se genera un "ataque" usando protocolos inseguros que envian/reciben todo en texto plano y al mismo tiempo se ejecuta un ataque real.

Listar todos los posibles tipos de **COMPROMISO INICIAL** no solamente escapa a este framework si no que sería pretensioso al pretender encasillar la realidad de las organizaciones en una tipología.  Siendo algo filosóficos, acá se aplica perfectamente la dialéctica hegeliana resumida, de forma coloquial, en el hecho que nadie se baña dos veces en un mismo rio.
Sin embargo, podemos ver que los más comúnes son :

- Mediante las aplicaciones web.  Principalmente en el software de base usado en ellas que conduce a RCE o vulnerabilidades en la implementación de funcionalidades que permiten obtener un control total de la información. Como valor agregado, el monitoreo de incidentes que ha evolucionado es el que se da a nivel de infraestructura, el de aplicación está atrasado y de ninguna forma integrado con el resto de la gestión de la seguridad en forma adecuada.
- Mediante servicios en nube que conducen hacia el core de la organización porque aún se encuentra basado en equipos legacy por decisión permanente o porque se encuentran en migración.  Otras condiciones de servicios en nube no son eticamente aprovechables, pero, el mundo de ataques reales si puede hacer uso de ellas como en los casos de SaaS inseguro.
- Escape de las "sandboxes" impuestas por los clientes delgados.
- Accesso remotos via VPN (sobre todo los webvpn).
- Redes inalámbricas que irradían su señal hasta fuera del perímetro físico de las oficinas de la organización evaluada.
- Ataques de Lado Cliente (CSA) que arrancen con acciones como el phishing de manera más común.
- Ingeniería social que incluye intrusión física.

## INSTALACIÓN

Este módulo debe garantizar que la operación disponga de al menos un C2 e infraestructura de ataque confiables y eso determina que se deben realizar instalaciones, configuraciones, implementar alta disponibilidad, detectar acciones de la gestión de amenazas que debe llevar a cabo la organización evaluada.

No hay un C2 que sea adecuado para toda operación, pero, si hay algunas funcionalidades que son requridas como permitir resilencia en los implantes ante la detección/mitigación de los mismos, proveer mecanismos de encubrimiento, permitir que se realice personalización a cualquier nivel incluyendo la modificación/adición de payload/implantes y sus formas de encubrimiento.
Esto último es bien importante porque con frecuencia se espera que los C2 sean una fuente exacta, exitosa e inagotable de payloas y no es su función si no ser un forma de soporte a la operación en curso.

Sin embargo, toda esta infraestructura puede fallar o ser "mitigada" y la necesidad de disponer rapidamente de una nueva, se hace evidente.  Esto es lo que nos lleva a tener que automatizar el proceso de **INSTALACIÓN** mediante IaC o, más propiamente, a emplear la DevOps y OpSec.

En el aspecto de infraestructura complementaria se tienen requerimientos divesos que depende de cada tipo de acción.
Por ejemplo, si el phishing será una opción, se requiere configurar servicios, dominios, generar reputación, etc. con una buena anticipación a la ejecución del envío de mensajes y eso determina infraestructura que debe ser tan confiable que supere los controles de los servicios de correo electrónico modernos.

## DESPLAZAMIENTO LATERAL

Las formas de desplazamiento lateral en función de vulnerabilidades en sistemas MS Windows está ampliamente documentada y controlada al mismo tiempo. Con las fallas en servicios de base como el Active Directory ocurre lo mismo y suelen ser más frecuentes.

Por otro lado, los sistemas basado en Linux o MacOS suelen ser percibidos como menos inseguros en términos de vulnerabilidades del software, pero, igual de proclives a fallas de configuraciones o mantenimientos inadecuados.
En este terreno se van a dar condiciones favorables para el desplazamiento lateral que no dependen de las actualizaciones o configuraciones seguras porque se tiene tecnología embebida que no progresará en el aspecto de seguridad por decisión del fabricante.  Así, los componentes de un sistema de videovigilancia basado en una versión reducida de Linux, ayudan mucho en este módulo.

Las aplicaciones internas también son una fuente de apoyo en el desplazamiento lateral porque suelen ser consideradas como de menos riesgo por su condición de "ubicación" en una red privada, con lo cual, se permite el uso de versiones obsoletas de software de base o se han realizado menos (o ningun) esfuerzo porque sea segura o residen en sistemas legacy.

## PERMANECER Y EXFILTRAR

En esta etapa se ejecutan las acciones que permitan persistir en los equipos donde han colocado los implantes (por ejemplo cuando son reiniciados) y mantener la penetración obtenida (sí un zombie/agente/implante es descubierto y eliminado).
Existen técnicas diversas para permitir que la permanencia sea obtenida y la más conocida es la que implementa un mecanismo de daisy chain.

La exfiltración es un paso "final" en toda esta etapa, es decir, dado que el objetivo de la simulación de adversario es comportarse lo más cercano al atacante real, se debe proveer una forma para extraer la data a la cual se va oteniendo acceso
El conocimiento sobre el uso de protocolos/servicio específicos como el DNS,ICMP, etc. para ejecutar la exfiltración esta bien difundido.  Entonces, lo que se peuden puntualizar son los medios que se emplee.  Por ejemplo,  es muy frecuente que los servidores DNS interno que se usan para el AD, tengan implementado el forwarding de queries hacia Internet.
