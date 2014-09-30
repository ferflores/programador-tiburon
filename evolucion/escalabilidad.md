# Escalabilidad

Si has escuchado o leido sobre el ciclo de vida del software seguramente se hizo mención de etapas de análisis, diseño, desarrollo, iteraciones, pruebas, documentación, implementación etc. Estas fases varían mucho según el tipo de proyecto y la metodología de desarrollo pero en todos los casos hay una etapa muy importante, ésta es comunmente llamada "mantenimiento" o "soporte" donde el software es supervisado, se hacen cambios constantes de configuración y desde cambios pequeños de código hasta funcionalidades nuevas, todo software necesita cambios con el tiempo por diferentes razones como nuevos requerimientos, errores emergentes, adaptación a nuevos sistemas operativos, integración con otros sistemas etc. Por estas razones prefiero llamar "Evolución" a la etapa de mantenimiento por que si un proyecto de software no crece según lo hace su entorno se va extinguiendo, pueden pasar algunos años y volverse obsoleto hasta el punto de tener que volver a hacer todo.

Suena lógico que un proyecto tenga que evolucionar, si éste se encuentra en producción y tiene usuarios utilizándolo se van a exigir cambios, parece fácil pero es aquí donde realizar una simple modificación puede convertirse en una pesadilla incluso para los mismos programadores presentes desde un inicio, esto es posible que suceda si no se utilizaron buenas prácticas de desarrollo, si no se pensó en el futuro del proyecto, en otras palabras, no se tomó en cuenta la "**Escalabilidad**".

Me sorprendí al no encontrar el significado de la palabra "Escalabilidad" en la RAE (Real Academia de la Lengua Española), así que tomaré lo que encontré en Wikipedia.

*En telecomunicaciones y en ingeniería informática, la escalabilidad es la propiedad deseable de un sistema, una red o un proceso, que indica su habilidad para reaccionar y adaptarse sin perder calidad, o bien manejar el crecimiento continuo de trabajo de manera fluida, o bien para estar preparado para hacerse más grande sin perder calidad en los servicios ofrecidos.*

[Wikipedia: Escalabilidad](http://es.wikipedia.org/wiki/Escalabilidad)

La definición de Wikipedia menciona "propiedad deseable" debido a que practicamente a todo software se le pueden hacer cambios para crecer sin embargo la facilidad y eficiencia con la que se hagan modificaciones dependerá de su "índice de escalabiidad". Aunque puede ser complicado medir o pensar como hacer un desarrollo escalable existen principios a seguir que nos pueden ayudar, algunos de estos principios los veremos en el siguiente tema.

Hacer software escalable no se trata de predecir el futuro, es muy probable que se requieran cambios que no estaban contemplados, hay un principio que debemos tomar en cuenta para delimitar lo que hacemos por escalabilidad, éste es *YAGNI* (You Aren't Gonna Need It), que establece que no debemos escribir lineas de código que no vamos a utilizar. Hay una gran diferencia entre programar pensando en escabilidad y programar de más pensando en funcionalidades que puedan tener uso en un futuro lo cual no es una buena práctica ya que puede ocasionar "código basura".

En los siguientes temas analizaremos los principios ***SOLID*** que nos ayudan como guías, ejemplos y consejos para crear mejor código siguiendo algunas buenas prácticas.
