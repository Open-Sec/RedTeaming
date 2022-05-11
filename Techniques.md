# DEFINITION OF TECHNIQUES

Esta etapa consiste en la planificación netamente técnica de la ejecución de la operación y se deben obtener definiciones exactas sobre como se procederá durante la **EJECUCIÓN DE PROCEDIMIENTOS**.
Aunque esto parezca netamente metodológico, no lo es, solamente se trata de acciones que deben ser conducidas debido a que no se puede experimentar cuando se ejecutan las acciones de la operación en curso.  Cualquier acción que genere una alerta puede determinar el fracaso parcial o total de la operación y es bien importante nunca subestimar al adversario (que para el red team viene siendo el blue team o quienes defienden a la organización evaluada).

Con la información trabajada en la etapa anterior de **VERFIICACIÓN DE TÁCTICAS ADECUADAS**, se procederá a **IDENTIFICAR VULNERABILIDADES** que permitan iniciar los ataques de la operación o, porlo menos, determinar cuáles son los posibles vectores de ataque.
Esto demanda analizar detalles que incluso pueden requerir empezar a realizar acciones que generen tráfico hacia los recursos de la organización evaluada, pero, teniendo en cuenta que no se trata de un pentest y los escaneos de cualquier tipo no deben ser considerados (al menos no en la forma indiscriminada que se usan durante un pentest).

El **DISEÑO DE VECTORES DE ATAQUE** determina cómo, con qué, cuándo se realizarán acciones de explotación de vulberabilidades o secuencias de pasos que permitan obtener el objetivo en curso (por ejemplo, el compromiso inicial) y los red teamers requeridos para cada escenario.

La **REVISIÓN DE TÉCNICAS** es la validacíon y confirmación final que permita dar el pase a la **EJECUCIÓN DE PROCEDIMIENTOS** y puede determinar cuestionamientos a las vulnerabilidades identificadas y los vectores diseñados que demanden una optimización, añadir nuevas vulnerabilidades/vectores o descartar algunos.

## IDENTIFY VULNERABILITIES (IDENTIFICAR VULNERABILIDADES)

La identificación de vulnerabilidades como tal es compleja en este punto porque puede determinar la ejecución de acciones que generen tráfico (así sea leve) y que podría ser detectado, identificado y mitigado.
Esto resulta tan complicado que, por ejemplo, en el caso de una operación de Compromiso Total, puede hacer que una de las opciones de Compromiso Inicial (llamado Accesso Inicial también), termine siendo inutilizada y más aún cuando se conduce en escenarios monitoreadas frecuentemente como aquellos que involucran servicios en servidores (sean contenedores o máquinas virtuales o servidores físicos) o máquinas de usuarios (así sean usuarios de áreas de TI, locales o remotos) o controles de acceso de seguridad física.

Por otro lado, se pueden tener situaciones donde ciertos controles ya no requieren ser identificados, pero, la información sobre los targets a utilizar no es facilmente obtenible.  En el caso de un escenario de Brecha Asumida, los controles de acceso a una red privada se asumen vulnerados, pero, al mismo tiempo se puede requerir analizar elementos para los cuales no se ha podido obtener información en el módulo de **RECON** debido a que es altamente confidencial (pero no invulnerable) o, sencillamente, porque se considera algo tan "sin valor" que se maneja de forma "interna" y resulta que ese elemento se convierte en un trampolin perfecto para continuar con el ataque.

La mejor postura en este módulo corresponde a "
- Realizar procesos de handshake naturales con los servicios expuestos.
- Considerar fallas en funcionalidades como secuencias de escape de ambientes tipo sandbox (como los usados en los servicios de clientes delgados).
- Emplear credenciales divulgadas para comprobar que aún son válidas (no empezar a tratar de listar todo porque cada acción puede estar siendo auditada, incluso la misma autenticación realizada con las credenciales divulgadas).
- Determinar sí las aplicaciones encontradas pueden o deben conducir hacia alguna interacción con otros recursos y servicios que permitan obtener el objetivo planteado (esto se puede hacer de forma sencilla cuando se trata de aplicaciones comúnes/horizontales, con las no comúnes/verticales se tendrá que basar en lo obtenido durante la etapa anterior y si no hay información al respecto, será poco probable que se use salvo que se identifiquen el uso de componentes con vulnerabilidades, pero, eso ya no es usar aplicaciones como un medio si no explotar vulnerabilidades en software de base).
- Analizar los controles respecto a los servicios de colaboración.
- Analizar los controles en acceso físico a las instalaciones y oficinas.
- Analizar los controles de acceso a redes inalámbricas.

## DESIGN ATTACK VECTORS (DISEÑO DE VECTORES DE ATAQUE)

Siempre tomar la acción del Compromiso Inicial resulta más sencilla como ejemplo para este módulo :

- Sí el vector de ataque será una aplicación web, puede que se trate de un sencillo CMS o de una aplicación desarrollada específicamente para la organización.  Puede que tenga una opción de auto registro automático o se tenga que pasar por un proceso de registro manual (como cuando se trata de una aplicación bancaria). Esto es necesario en el sentido que la vulnerabilidad que permita el compromiso inicial puede requerir haber pasado por un proceso de autenticación y tiene implicancias de ingeniería social.
- Sí el vector de ataque es una aplicación web de uso interno y no se perciben oportunidades de éxito con la ingeniería social, se pueden haber definido opciones en base a controles de acceso fallidos en componentes relacionados como pueden ser código fuente expuesto, configuraciones de nube mal hechas, credenciales divulgadas, instancias de desarrollo y/o QA expuestas con vulnerabilidades o fallas en control de acceso, interfaces de autenticación/recuperación de acceso sometibles a ataques de diccionario, etc.
- Sí el vector de ataque será realizado mediante servicios expuestos mediante servidores, se deben considerar no solamente identficar vulnerabilidades explotables si no usos no adecuados de funcionalidades.
- Sí el vector de ataque serán los equipos de usuarios, las formas de entregar el malware de forma exitosa serña las que requirirán mayor esfuerzo porque van desde la determinación de las condiciones requeridas para la distribución (phishing, fisica, etc.) hasta como evadir las protecciones del tipo EDR que vengan incluídas en el sistema operativo base y las adicionadas como complemento y/o reemplazo total/parcial.

La determinacion de las formas de evasión de protecciones que se vayan a emplear resultan vitales y se deben considerar situaciones donde existen varias y se encuentran encadenadas y monitoreadas de forma correcta.
Por eso, esta etapa debe definir de forma exacta qué se usará para explotar las vulnerabilidades identificadas (herramientas, exploits, scripts, etc.) o qué técnicas se emplearán y las adecuaciones requeridas o sí debe crearse algo (si, aca si hay tiempo y el esfuerzo es recompensando para la creación de exploits o scripts o herramientas).
Como se puede inferir, esta etapa incluye pruebas de laboratorio desarrollando los escenarios que se pondrán en ejecución y **EJERCITARLOS**.

También, se puede inferir que se requieren tantas habilidades y experiencias que se requiere aplicar a la parte **TEAM** de Red Team si o si y es el mejor momento de incorporar a los red teamers necesarios.  Su participación puede ser parcial (durante una etapa y/o módulo específico o durante toda la operación).
Esto no implica que antes o después no hayan o sean consultados, pero, si incorporación formal le añade la responsabilidad de entregar resultados.

El aspecto de resilencia (termino más popular desde la pandemia) es importante porque no sería inteligente, por ejemplo, haber definido un solo vector para un Compromiso Inicial y que sí es detectado/mitigado se determine el fracaso de la operación.
Sin embargo, esto lleva a otro aspecto que pocas veces es ejercitado en una simulación de adversarios, pero, si empleado en ataques reales : el atacar otras organizaciones relacionadas a la organización evaluada como un medio de obtener ataques exitosos.  En el mundo del red teaming, esto se puede dar en corporaciones o grupos empresariales, pero, no es tan común salvo un nivel de madurez excelente en la gestión de la seguridad a nivel corporativo o del grupo completo.

## REVIEW TECHNIQUES (REVISIÓN DE TÉCNICAS)

Esta parte de esta es la validación final y la mejor recomendación es que sea conducida por el Líder del Red Team asignado con el apoyo de algún red teamer que no haya participado de las etapas anteriores.
Así se podra tener un mejor feedback que lleve hacia replantear o continuar a la siguiente etapa.
