# VERIFICATION OF PROPER TACTICS (VERIFICACIÓN DE TÁCTICAS ADECUADAS)

Puesto que la estrategia ya debe estar definida a este punto y que la misma depende del alcance acordado para el ejercicio de red teaming, el framework de Open-Sec se enfoca en ordenar las acciones concretas operativas.
Aunque no necesariamente se pueden aplicar todos estos módulos porque dependerán del tipo de ejercicio y escenario a desarrollar, son comúnes y útiles todos ellos.

Por esas razones, el realizar un **RECON** adecuado es lo más importante en toda operación de forma que las Tácticas tradicionales sean modificadas para que puedan ser aplicadas de forma exitosa o utilizar aquellas Tácticas que no son explotadas comunmente e, incluso, puede llevar a proponer Tácticas completamente nuevas.
Por ejemplo, aún los ejercicios de red teaming se relacionan mucho a quebrar la seguridad a nivel de infraestructura y no de aplicaciones.  Conseguir un "compromiso inicial" a través de las aplicaciones tiene la ventaja que casi todas requieren acceso al core de la data y aplicaciones de integración y que, además, su protección y monitoreo son menos maduros que los empleados con respecto a la infraestructura.

La **ENUMERACION** es una tarea de ordenamiento y preparación para uso posterior de la información acopiada y analizada. 
También, puede incluir acciones que no vayan en contra del caracter pasivo de esta etapa o de hacerlo, sean generadoras de registros comúnes (que por su abundancia son ignorados) o registros poco convencionales (que sean ignorados por desconocimiento de los mismos).

Finalmente, la **REVISIÓN DE TÁCTICAS** permitirá conocer sí se requiere obtener más información o información diferente o de fuente diferente.  Por ejemplo, el análisis de documentación encontrada en Internet puede confrimar que una buena opción para el compromiso inicial puede ser la red Wi-Fi de la organización o el colocar una red Wi-Fi falsa a la cual se conecten los usuarios.  Esto determina que se requiere un conocimiento de la seguridad física establecida en la organización y una visita del perímtero físico serán requeridos.
También, es válido que se adicionen Tácticas, que se descarten las definidas o que se modifiquen.

## RECON (RECOINNASSENCE - RECONOCIMIENTO)

Este módulo desarrolla las mismas acciones que un Pentest con diferencias que resultan importantes :

- En un Pentest, se puede realizar un acopio amplio de información respecto a una organización, pero, dado que los alcances son sumamente acotados, puede terminar siendo una perdida de tiempo ya que dicha información no será empleada.
- Una de las grandes diferencias en el **RECON** durante un ejercicio de red teaming es que se hará búsqueda de documentos no solo para extraer metadata si no, también, para revisar el contenido de los documentos respecto a información úitl para el ejercicio o que represente una divulgación de datos importantes.
- Otra de las grandes diferencias es que se le otorga un mayor tiempo porque constituye las bases del ejercicio y el conocimiento que se requiere sobre la organización.  Es importante recordar que una operación real de red teaming es acerca de datos y los procesos que los manejan, no solo de tecnología.  De hecho, el tiempo asignado puede alcanzar el 30% o más de todo el ejercicio.
- La información divulgada como resultado de la explotación de brechas de seguridad explotadas no es solamente reportada a la organización evaluda si no tomada como insumo importante en el resto de acciones de la operación. Esto incluye código fuente de aplicaciones y documentos que no sean unicamente de uso interno.

Por ello, este módulo implica que no solamente se realiza un acopio de información si no que la misma debe ser analizada de acuerdo a los objetivos del ejercicio luego de una cuidadosa revisión y ponderación.

## ENUMERATION (ENUMERACIÓN)

La cantidad de informacion que se puede obtener determina la necesidad de compilarla en una forma adecuada para el desarrollo de las otras etapas del ejercicio y ello implica disponer de formas en las que esta información sea de fácil acceso y pueda ser sometida a búsquedas diversas de forma rapida y simple.
Existen muchas aplicaciones que pueden ser utilizadas para estos fines, sin embargo, cualquier forma práctica es válida.  Por ejemplo, disponer de una base de datos SQLite con campos BLOB (para almacenar imágenes) ayudará a realizar búsquedas con un lenguaje tan popular como el SQL y acceder a los detalles de cada información obtenida más allá del lo básico (un nombre de archivo, un URL, un nombre de usuario, un email, contraseñas divulgadas, etc.) incluyendo otros elementos no básicos (comentarios hechos por quien obtuvo la información, screenshots, categoría, etc.)

Este módulo es el filtro final antes de continuar con la **REVISIÓN DE TÁCTICAS** y es donde se pueden realizar algunas acciones que no sean pasivas, pero, que tampoco despierten alertas tempranas.
Por ejemplo, la obtención de screenshots de servidores web expuestos es una acción que debe ser parte del módulo de **RECON**, pero, el determinar si la calidad es la adecuada o no, si se deben incluir screenshots adicionales del mismo URL base (como aquellos generados por mensajes de error) o incluir el fuente de la página, entre otros, corresponden a esta etapa.
Otra acción puede corresponder con el concepto tradicional de enumeración (como se lleva a cabo en un pentest cuando se enumeran usuarios, grupos, roles,etc.), pero, se debe analizar muy bien el hecho que estas actividades dejan registros sin importar de que se trata.  Es decir, una enumeración de usuarios de un sistema operativo o de un servicio de nube, debe dejar registros auditables.
El motivador para querer realizar una enumeración de este tipo es que el feedback para las Tácticas propuestas será importantísimo. Por ejemplo, cuando se han obtenido credenciales de un servicio de nube durante el **RECON** y se puede intentar hacer enumeración de identidades y recursos.

## REVIEW TACTICS (REVISIÓN DE TÁCTICAS)

Idealmente, los módulos anteriores han servido para confirmar las Tácticas propuestas, pero, en el mundo real este módulo sirve para mejoralas, corregirlas, descartarlas o crear nuevas.

Si bien es cierto que no hay una secuencia estricta en la aplicacion de cada etapa (se puede subir y bajar según se requiera), este módulo deberá servir para continuar de manera firme con el resto de etapas.  
Incluso, es el que, finalmente, determinará el tipo de red teamers que serán asignados, su cantidad, durante cuánto tiempo, en qué etapa o módulo y qué acciones específicas ejecutarán (la parte **teaming** del ejercicio).

Las Tácticas deben permitir hacer un cambio rapido ante situaciones esperadas (cuando se sabe que se realizará alguna acción activa que generará ruido) o inesperadas como el comportamiento de elementos de protección bien establecidos/configurados.

Finalmente, el resultado de esta etapa es un conjunto documento de Tácticas a emplear en los módulos posteriores y en acciones comúnes como el Compromiso Inicial, la Instalación (incluyendo las Tácticas de OpSec que deben ser empleadas), el Desplazamiento Lateral, la Persistencia y Permanencia, la Exfiltración.
