# Rendimiento

Cuando se habla de rendimiento (performance) en el mundo de la informática se hace referencia a la velocidad con la que un programa realiza una tarea considerando también el uso de recursos de la computadora o dispositivos externos y de Internet.

Un buen programador debe ser responsable del performance de su código, no basta con escribir 5 o 10 lineas y probar que funcionan localmente en un ordenador o en un ambiente de pruebas por que no es lo mismo que un usuario ejecute un programa una o dos veces a que mil usuarios lo hagan un millón de veces, otro ejemplo es la gran diferencia entre trabajar con un arreglo (array) de 100 elementos a trabajar con uno de 100,000 o hacer una consulta a una tabla de 100 registros y luego hacer la misma consulta cuando la tabla tiene un millón de filas.

Por lo general en lenguajes de programación de alto nivel vienen incluidas clases y funciones para medir tiempos de ejecución pero antes de llegar a ese punto vamos a definir un método al que le realizaremos algunas pruebas.

Tomaremos como ejemplo el ***método de la burbuja*** (bubble sort) que es un algoritmo de ordenamiento que probablemente lo hayas visto en clase de programación, aunque muy conocido no es popular por su eficiencia, al contrario es muy lento cuanto se trata de trabajar con grandes cantidades de datos, este algoritmo recorre una lista *N* veces donde *N* es el tamaño de la lista (o arreglo) y va acomodando cada elemento de menor a mayor hasta dejarlos todos ordenados de forma ascendente (también puede aplicarse de forma descendente).

Un ejemplo muy sencillo en código:

#### Burbuja(arreglo)
```
public static int[] Burbuja(int[] arreglo)
{
	for (var i = 0; i < arreglo.Length; i++)
	{
		for (var j = 0; j < arreglo.Length - 1; j++)
		{
			if (arreglo[j] > arreglo[j + 1])
			{
				var temp = arreglo[j + 1];
				arreglo[j + 1] = arreglo[j];
				arreglo[j] = temp;
			}
		}
	}
	return arreglo;
}

```

El método **Burbuja** recibe un parámetro que es el arreglo a ordenar y devuelve el mismo ya ordenado, el funcionamiento es el siguiente.

Si aplicamos la burbuja a la lista [5,3,2] cada iteración haría los siguientes cambios:

1. [3,2,5]
2. [2,3,5]
3. [2,3,5]

Si observas la iteración 2 y 3 son iguales, este algoritmo puede llegar a hacer muchas iteraciones innecesarias pero este problema lo analizaremos mas adelante, si no has visto antes este algoritmo te pido de favor lo analices con mucha atención hasta entender como funciona y tener bien claro el código para seguir con el resto del capítulo, te comparto el código completo que puedes escribir en una aplicación de consola y lo pruebes por ti mismo.

```
using System;

namespace Pruebas
{
	class Program
	{
		static void Main(string[] args)
		{
			var arreglo = new int[] { 5, 3, 2 };

			Burbuja(arreglo);

			Console.WriteLine(String.Join(",", arreglo));
			Console.ReadLine();
		}

		public static int[] Burbuja(int[] arreglo)
		{
			for (var i = 0; i < arreglo.Length; i++)
			{
				for (var j = 0; j < arreglo.Length - 1; j++)
				{
					if (arreglo[j] > arreglo[j + 1])
					{
						var temp = arreglo[j + 1];
						arreglo[j + 1] = arreglo[j];
						arreglo[j] = temp;
					}
				}
			}
			return arreglo;
		}
	}
}

```

Prueba utilizando arreglos con diferente número de elementos.

###### Nota: String.Join(separador, arreglo) sirve para concatenar los elementos de un arreglo en un string separando cada uno por el separador especificado, en el ejemplo se separan por coma.

Ejecutando el código anterior la consola imprimirá los elementos ordenados de forma ascendente separados por coma (2,3,5).

El algoritmo funciona, nuestro programa parece estar listo, sin embargo hay varias preguntas que debes de comenzar a plantearte si quieres que tus lineas sean consideradas "código para ambiente de producción", te ayudo a pensar en algunas:

¿El método **Burbuja** funciona si el arreglo tiene un millon de elementos?

¿Qué tan rápido funciona nuestro algoritmo?

¿He realizado las suficientes pruebas para considerar que mi código no generará algún error?

¿He investigado sobre alguna mejor solución?

¿Que sucede si el parámetro *arreglo* es nulo?

¿Que debo hacer si se genera algún error en mi método?

Puede haber muchas más preguntas pero no te preocupes, llegando a cierto punto de maduración como programador estas preguntas se procesan más rápido en tu mente logrando prevenir errores o bajo performance automaticamente, en el siguiente capítulo haremos algunas pruebas de nuestro método **Burbuja**.
