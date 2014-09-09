# Resultado / Tiempo

Tomando el código de ejemplo del capítulo anterior, probaremos la rapidez del método **Burbuja**.

En el namespace System.Diagnostics de .NET Framework desde la versión 2.0 podemos encontrar la clase **Stopwatch**, ésta nos puede ayudar para obtener el tiempo que transcurrió entre una linea de código y otra, por ejemplo:

```
var stopwatch = new Stopwatch();

stopwatch.Start();

Console.WriteLine("Hola!");

stopwatch.Stop();

Console.WriteLine(stopwatch.ElapsedMilliseconds);
```

Ese código imprimirá los milisegundos que transcurrieron mientras la consola imprimió "Hola!", en mi caso fue 1 milisegundo, esto puede variar dependiendo de tu procesador.

Ahora que sabemos como medir el tiempo en que se ejecuta un programa podemos medir la eficiencia de nuestro método de ejemplo, vamos a agregar algunas lineas para imprimir los milisegundos transcurridos al ordenar un arreglo de 3 elementos:


```
static void Main(string[] args)
{
	var stopwatch = new Stopwatch();
	stopwatch.Start();

	var arreglo = new int[] { 5, 3, 2};

	Burbuja(arreglo);

	stopwatch.Stop();

	Console.WriteLine(stopwatch.ElapsedMilliseconds);
	Console.ReadLine();
}
```

En mi caso tomó 2 milisegundos, computar un arreglo de 3 elementos es tarea fácil, sería una buena práctica aplicar esta prueba a algún programa que hayas hecho anteriormente, haciendo algunas formulas muy sencillas puedes convertir los milisegundos a segundos, minutos, nanosegundos etc. Aunque nuestro método burbuja parece trabajar muy rápido en el siguiente capítulo lo pondremos bajo pruebas más fuertes.
