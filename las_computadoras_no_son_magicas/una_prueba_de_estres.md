# Prueba de estrés

Existen diferentes tipos de pruebas que se pueden aplicar al software, en el capítulo anterior realizamos una prueba de rendimiento muy sencilla que solo nos muestra el tiempo de ejecución de un método, ahora nuestro objetivo será hacer que nuestro método no funcione correctamente, romperlo si es posible llevando al tope su capacidad de trabajo, a ésto se le conoce como *prueba de estrés*.

Con las pruebas anteriores observamos que nuestro método **Burbuja** ordena muy rápido un arreglo de 3 elementos pero ¿Cuánto tardará en ordenarlo si el tamaño del arreglo es de 10,000?

En vez de crear un arreglo de 10,000 elementos manualmente crearemos un método que lo hace por nosotros:

#### GenerarArregloNumerico (cantidad, minimo, maximo)

```
public static int[] GenerarArregloNumerico(int cantidad)
{
	int[] arreglo = new int[cantidad];
	var random = new Random();

	for (var x = 0; x < cantidad; x++)
	{
		var numeroAleatorio = random.Next(0, cantidad);
		arreglo[x] = numeroAleatorio;
	}

	return arreglo;
}

```

Ejemplo de uso:

```
var arreglo = GenerarArregloNumerico (1000);
```
El código anterior generaría un arreglo con 1000 números aleatorios enteros entre 0 y 1000.

Ahora podemos probar nuestro método ordenando 10,000 elementos.

```

var stopwatch = new Stopwatch();
stopwatch.Start();

var arreglo = GenerarArregloNumerico(10000);

Burbuja(arreglo);

stopwatch.Stop();

Console.WriteLine(stopwatch.ElapsedMilliseconds);
Console.ReadLine();

```

En mi caso tomó 2178 milisegundos que equivalen a 2.178 segundos lo cual sigue siendo algo aceptable pero si pruebas con 20,000 elementos superará los 10 segundos y arriba de 50,000 serían minutos, cuidado si pruebas con cantidades muy grandes puedes dejar colgado un rato tu compilador. No queremos que nuestro usuario tenga que esperar minutos cada vez que pasa por alguna parte de nuestro sistema que usa este método por lo que una mejor solución es sin duda necesaria. En un escenario real por el simple hecho de tener que ordenar 50,000 elementos podemos estar casi seguros que algo estamos haciendo mal, eso no debería de suceder, cuando se necesita procesar grandes cantidades de datos es recomendable hacerse por partes (batches) aunque si hay casos donde se ocupa trabajar con grandes datos como al momento de generar reportes o proyectos científicos.

Como pudimos ver el método de la burbuja no es muy bueno, además hay otros factores que debemos tomar en cuenta como el número de iteraciones. Si el método *Burbuja* recorre todo un arreglo *N* veces donde *N* es el tamaño de éste, significa que el número de iteraciones crecerá exponencialmente conforme el arreglo sea más grande por lo que al realizar un ordenamiento entre mil elementos se harán un millón de comparaciones y esto no es algo bueno, en un escenario real puede existir el requerimiento de que por cada comparación se necesita hacer una consulta (query) a una base de datos o una petición (request) a una página de Internet o un Web Service, ese tipo de tareas pueden ser más "pesadas" que trabajar con un arreglo númerico por lo que 100,000 o un millón iteraciones no son aceptables.



