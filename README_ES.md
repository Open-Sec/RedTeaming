# Marco de Referencia para Operaciones tipo Red Team por Open-Sec

Teniendo claramente establecida la diferencia entre Emulación de Amenazas y Simulación de Adversarios, este framework fue desarrollado por el team de Open-Sec como una forma de estandarizar las acciones realizadas durante las operaciones de red teaming que realizamos y contar con un medio de comunicación e integración de los red teamers y sus labores.

También, es importante considerar cuáles son los objetivos principales de un ejercicio de red teaming que son medir el :
- TTD (Time To Detect) : Tiempo para Detectar
- TTM (Time To Mitigate) : Tiempo para Mitigar

Es importante reconocer que Mitre ha popularizado la terminología de TTP (Tactic, Techniques, Procedures) mediante su framework ATT&CK (https://attack.mitre.org/).

Al mismo tiempo, es importante tener claros algunos aspectos del ambito del red teaming :
- Un atacante no utilizará las TTPs documentadas y que un Blue Team tomará como referencia, al menos no las usará como se han documentado de forma exacta.  Seria absurdo que los atacantes hagan lo que esperan los defensores.
- Un atacante puede tomar como referencia las TTPs, pero, nunca seguirlas de forma estricta y sobre todo debido a que no toda organización es igual y que sus niveles de madurez en la gestión de la seguridad tampoco lo son.
- Un framework como ATT&CK es muy adecuado para realizar ejercicios de Emulación de Amenazas que puede iniciar en la forma de "table top exercises" y concluir con operaciones reales para escenarios y casos específicos como ejercicios que acompañen durante la maduración de la gestión de la seguridad.
- Existen varios frameworks para red teaming, unos más desarrollados que otros y algunos basados en sectores específicos.  Todos ellos apuntan a establecer pasos claros y específicos en la gestión de los ejercicios de red teaming y sus resultados.

En un principio se aplicó unicamente el gráfico que se observa abajo y se han desarrollado documentos (en formato markdown) independientes que se comparten entre los red teamers.

Adicionalmente, se ha empleado este framework en los entrenamientos provistos por Open-Sec para, de forma implícita, orientar los ejercicios de red teaming adecuadamente entre los participantes.
Este repositorio es un primer esfuerzo en compartir ésta documentación, pero, de una forma organizada.

*No pretende ser de una guía completa o un libro o una metodología o un framework que incluya todo lo existente y lo que está por existir, solamente es un conjunto de información a la cual acudir por un ordenamiento secuencial de pasos y algunas ideas que se van modificando en el tiempo (sea por obsolescencia o por mejoras).*

1. Verification of Proper Tactics. (https://github.com/Open-Sec/RedTeaming/blob/main/Tactics.md)
2. Definition of Techniques. (https://github.com/Open-Sec/RedTeaming/blob/main/Techniques.md)
3. Execute Procedures. (https://github.com/Open-Sec/RedTeaming/blob/main/Procedures.md)
4. Real Goal. (https://github.com/Open-Sec/RedTeaming/blob/main/Goal.md)

![Red Teaming Framework by Open-Sec](https://github.com/Open-Sec/RedTeaming/blob/main/redteaming-framework-2.png)
