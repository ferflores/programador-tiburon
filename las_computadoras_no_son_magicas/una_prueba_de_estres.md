# Prueba de estrés

Existen diferentes tipos de pruebas que se pueden aplicar al software, en el capítulo anterior realizamos una prueba de rendimiento muy sencilla que solo nos muestra el tiempo de ejecución de un método, ahora nuestro objetivo será hacer que nuestro método no funcione correctamente, romperlo si es posible llevando al tope su capacidad de trabajo, a ésto se le conoce como *prueba de estrés*.

Con las pruebas anteriore observamos que nuestro método **ObtenerPosicion** tarda entre 15 y 30 milisegundos para encontrar la posición de un número en un arreglo de 3 elementos pero ¿Cuánto tardará en encontrarlo si el tamaño del arreglo es de 100,000?

En vez de crear un arreglo de 100,000 elementos manualmente crearemos un método que lo hace por nosotros:

#### GenerarArregloNumerico (cantidad, minimo, maximo)

```
public static int[] GenerarArregloNumerico(int cantidad, int minimo, int maximo){
	int[] arreglo = new int[cantidad];
	var random = new Random ();

	for (var x = 0; x < cantidad; x++) {
		var numeroAleatorio = random.Next(minimo, maximo);
		arreglo [x] = numeroAleatorio;
	}

	return arreglo;
}

```

Ejemplo de uso:

```
var arreglo = GenerarArregloNumerico (1000, 0,500);
```
El código anterior generaría un arreglo con 1000 números enteros entre 0 y 499.

Ahora podemos probar nuestro método buscando un número entre 100,000 elementos.

```

var arreglo = GenerarArregloNumerico (100000, 0,10);

var stopwatch = new Stopwatch ();
stopwatch.Start ();

var pos = ObtenerPosicion(arreglo, 5);

stopwatch.Stop ();
Console.WriteLine ("Milisegundos: " + stopwatch.ElapsedMilliseconds);

```

Probablemente esperabas que tomara minutos, horas o que tu computadora se congelara pero si realizaste esta prueba (y tienes un procesador de capacidad considerable) notarás que no hay mucha diferencia en el tiempo de ejecución incluso si el valor buscado (5) no es encontrado o si aumentas el tamaño del arreglo a 1,000,000, cuidado si intentas crear arreglos más grandes de 100 millones puedes ocasionar que tu compilador se quede colgado un buen rato. La razón por la que no hay mucha diferencia en los tiempos es por lo básico que es nuestro algoritmo de busqueda, la comparación es muy simple y no realizamos ninguna operación compleja.

La poca diferencia entre tiempos no significa que nuestro código sea perfecto, hay otros factores que debemos tomar en cuenta como el número de iteraciones. Si el método **ObtenerPosicion** recorre todo un arreglo en busca de un elemento y no lo encuentra esto significa que el número de iteraciones es igual al tamaño del arreglo por lo que al realizar una busqueda entre un millón de elementos, se harán un millón de comparaciones y esto no es algo bueno, en un escenario real puede existir el requerimiento de que por cada comparación se necesita hacer una consulta (query) a una base de datos o una petición (request) a una página de Internet o un Web Service, ese tipo de tareas son más "pesadas" que trabajar con un simple arreglo númerico por lo que 100,000 o un millón iteraciones no son aceptables.



