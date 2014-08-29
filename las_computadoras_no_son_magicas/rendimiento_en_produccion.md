# Ambientes de desarrollo

Existe un término que probablemente ya hayas escuchado, y si no es el caso, lo escucharás en tu primer empleo, estoy hablando de "Producción" o "Ambiente de producción" que hace referencia al entorno en el que no solo se encuentra un programa realizando una sola función si no un conjunto de una o más aplicaciones de software, una o más computadoras funcionando como servidor, una o más bases de datos entre muchos otros componentes que pueden formar parte de la arquitectura de lo que es ya todo un sistema de información operando con información real y probablemente generando ganancias para una empresa.

Para explicarlo más claramente por lo general existen tres ambientes para una aplicación de software:

* Desarrollo (Development)
* Pruebas (Testing)
* Producción (Production)

El ambiente de desarrollo es donde se encuentra el código fuente y pueden hacerse cambios sin mucho riesgo, este ambiente (environment) puede instalarse en una o varias computadoras donde los programadores harán su trabajo, codificarán y harán cambios a lo largo de la vida del proyecto.

En el ambiente de pruebas se colocan archivos, ejectutables (en caso de haberlos) del software que se está desarrollando o partes de éste, además de una base de datos de prueba, este environment por lo general está en un solo lugar (servidor/server) donde personas involucradas en el proyecto principalmente Testers (personas que realizan diferentes tipos de pruebas) validan el correcto funcionamiento del software, reportan errores entre otras actividades para mejorar la calidad constantemente.

En producción se coloca el resultado de los ambientes anteriores, software ya con un cierto nivel de calidad que garantiza la poca probabilidad de que ocurra algún error, sería ideal que en este ambiente no hubiera problemas, que se pudieran hacer pruebas exhaustivas y que todo funcionara perfectamente, lamentablemente eso no existe, siempre hay errores tarde o temprano.

Cabe mencionar que cada entorno que estoy mencionando puede variar mucho dependiendo del proyecto, estándares de las empresas, metodologías de desarrollo, etc.

Hacer cambios directamente en producción sin probarse antes puede poner en riesgo la integridad entre componentes del sistema, pérdida o corrupción definitiva de información que puede ocasionar desde usuarios insatisfechos hasta afectar monetariamente o legalmente a una empresa.

Las computadoras no son mágicas, no son tan inteligentes (al menos no hasta el día de hoy), no es fácil tenerlas listas para cualquier escenario, necesitan de nuestro ingenio para hacer un mejor trabajo.


*Nota: al proceso de mover partes o cambios de software de un ambiente a otro se le llama "Deployment"*

