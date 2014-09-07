# Rendimiento

Cuando se habla de rendimiento (performance) en el mundo de la informática se hace referencia a la velocidad con la que un programa realiza una tarea considerando también el uso de recursos de la computadora o dispositivos externos y de Internet.

Un buen programador debe ser responsable del performance de su código, no basta con escribir 5 o 10 lineas y probar que funcionan localmente en un ordenador o en un ambiente de pruebas por que no es lo mismo que un usuario ejecute un programa una o dos veces a que mil usuarios lo hagan un millón de veces, otro ejemplo es la gran diferencia entre trabajar con un arreglo (array) de 100 elementos a trabajar con uno de 100,000 o hacer una consulta a una tabla de 100 registros y luego hacer la misma consulta cuando la tabla tiene un millón de filas.

Por lo general en lenguajes de programación de alto nivel vienen incluidas clases y funciones para medir tiempos de ejecución como mostraré en un ejemplo que explico a continuación.

Tomaremos como ejemplo la *búsqueda secuencial* que es un algoritmo muy conocido pero no es popular por su eficiencia, al contrario es muy lento cuanto se trata de trabajar con grandes cantidades de datos, este algoritmo recorre una lista buscando un elemento con cierto criterio hasta encontrarlo o recorrer toda la lista.

Un ejemplo en código es muy sencillo:

#### ObtenerPosicion(arreglo, valorBuscado)
```
public int ObtenerPosicion(int[] arreglo, int valorBuscado){

        for(int x=0; x < arreglo.Length; x++){
            if(arreglo[x] == valorBuscado){
                return x;
            }
        }

        return -1;
    }

```

El método **ObtenerPosicion** recibe dos parámetros; el arreglo en el que se realizará la busqueda y el elemento a buscar, en este caso lo que queremos saber es la posición del elemento, si éste se encuentra devolvemos el indice, en caso contrario -1.

Si agregamos el método a una clase y hacemos pruebas sencillas podemos ver que funciona:

```
var arreglo = new int[]{ 2, 5, 7 };
var pos = ObtenerPosicion(arreglo, 5);
Console.WriteLine(pos);

```
Ejecutando el código anterior la consola imprimirá 1 ya que es la posición del número 5, si en vez de 5 el segundo parámetro fuera 2, el resultado sería 0 y si el elemento a buscar no se encuentra en el arreglo la consola imprimirá -1.

Nuestro algoritmo funciona, nuestro programa parece estar listo, sin embargo hay varias preguntas que debes de comenzar a plantearte si quieres que tus lineas sean consideradas "código para ambiente de producción", te ayudo a pensar en algunas:

¿El método **ObtenerPosicion** funciona si el arreglo tiene un millon de elementos?

¿Qué tan rápido funciona nuestro algoritmo?

¿He realizado las suficientes pruebas para considerar que mi código no generará algún error?

¿He investigado sobre alguna mejor solución?

¿Que sucede si el parámetro *arreglo* es nulo?

¿Que debo hacer si se genera algún error en mi método?

Puede haber muchas más preguntas pero no te preocupes, llegando a cierto punto de maduración como programador estas preguntas se procesan más rápido en tu mente logrando prevenir errores o bajo performance automaticamente, en el siguiente capítulo haremos algunas pruebas de nuestro método **ObtenerPosicion**, si no te ha quedado claro el código te recomiendo leerlo y tratar de entenderlo para continuar con los ejemplos.
