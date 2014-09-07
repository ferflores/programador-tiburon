# Tiempo / Resultado

Tomando el código de ejemplo del capítulo anterior, probaremos la rapidez del método **ObtenerPosicion**.

En el namespace System.Diagnostics de .NET Framework desde la versión 2.0 podemos encontrar la clase **Stopwatch**, ésta nos puede ayudar para obtener el tiempo que transcurrió entre una linea de código y otra, por ejemplo:

```
var stopwatch = new Stopwatch();

stopwatch.Start();

Console.WriteLine("Hola!");

stopwatch.Stop();

Console.WriteLine(stopwatch.ElapsedMilliseconds);
```

Ese código imprimirá los milisegundos que transcurrieron mientras la consola imprimió "Hola!", en mi caso fueron 15 milisegundos, esto puede variar dependiendo del ordenador.

Ahora que sabemos como medir el tiempo en que se ejecuta un programa podemos medir la eficiencia del método **ObtenerPosicion**, ejemplo:


```
var arreglo = new int[]{ 2, 5, 7 };

var stopwatch = new Stopwatch ();
stopwatch.Start ();

var pos = ObtenerPosicion(arreglo, 5);

stopwatch.Stop ();
Console.WriteLine ("Milisegundos: " + stopwatch.ElapsedMilliseconds);
```

En mi caso tomó 20 milisegundos, sigue siendo una prueba muy sencilla, a continuación el código completo con nuestro método en una clase para que puedas probar por si has tenido algún problema.

```
using System;
using System.Diagnostics;

namespace Pruebas
{
	class MainClass
	{
		public static void Main (string[] args)
		{
			var arreglo = new int[]{ 2, 5, 7};

			var stopwatch = new Stopwatch ();
			stopwatch.Start ();

			var pos = ObtenerPosicion(arreglo, 5);

			Console.WriteLine(pos);

			stopwatch.Stop ();
			Console.WriteLine ("Milisegundos: " + stopwatch.ElapsedMilliseconds);
		}

		public static int ObtenerPosicion(int[] arreglo, int valorBuscado){

			for(int x=0; x < arreglo.Length; x++){
				if(arreglo[x] == valorBuscado){
					return x;
				}
			}

			return -1;
		}
	}
}

```

Toma el tiempo necesario para entender el código, agrega mas elementos al arreglo para ver que tanto varían los milisegundos transcurridos trabajando con más números.
