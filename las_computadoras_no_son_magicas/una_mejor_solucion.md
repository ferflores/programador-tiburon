# Una mejor solución

Es muy motivante cuando la solución a un problema llega a tu mente, quieres implementarla, exponerla o hasta presumirla y es reconfortante ver que funciona correctamente pero es muy importante siempre cuestionarse si fue la mejor opción, un ingeniero de software debe ser crítico y analista, es muy común en estos días encontrar una solución al problema que se presenta después de hacer una búsqueda en Internet y eso es bueno, puedes encontrar soluciones que ya han sido probadas por otras personas e incluso por comunidades, esto no significa que harás un "copy/paste", para cada escenario puede haber diferentes implementaciones pero siempre es bueno hacer investigación antes de *reinventar la rueda*.

Si haces una busqueda sobre los mejores métodos de ordenamiento, comprobarás que la *burbuja* no es muy eficiente con grandes cantidades de números como lo vimos en el tema anterior y observarás que hay algoritmos más eficientes como el *Quicksort*, veamos un ejemplo.

#### Quicksort(arreglo)
```
public static void Quicksort(int[] arrreglo, int izquierda, int derecha)
{
	var i = izquierda;
	var j = derecha;
	var pivote = arrreglo[(izquierda + derecha) / 2];

	while (i <= j)
	{
		while (arrreglo[i].CompareTo(pivote) < 0)
		{
			i++;
		}

		while (arrreglo[j].CompareTo(pivote) > 0)
		{
			j--;
		}

		if (i <= j)
		{
			var temp = arrreglo[i];
			arrreglo[i] = arrreglo[j];
			arrreglo[j] = temp;

			i++;
			j--;
		}
	}

	if (izquierda < j)
	{
		Quicksort(arrreglo, izquierda, j);
	}

	if (i < derecha)
	{
		Quicksort(arrreglo, i, derecha);
	}
}
```



El algoritmo trabaja de la siguiente forma:

1.
Elegir un elemento de la lista de elementos a ordenar, al que llamaremos pivote.

2.
Resituar los demás elementos de la lista a cada lado del pivote, de manera que a un lado queden todos los menores que él, y al otro los mayores. Los elementos iguales al pivote pueden ser colocados tanto a su derecha como a su izquierda, dependiendo de la implementación deseada. En este momento, el pivote ocupa exactamente el lugar que le corresponderá en la lista ordenada.

3.
La lista queda separada en dos sublistas, una formada por los elementos a la izquierda del pivote, y otra por los elementos a su derecha.

4.
Repetir este proceso de forma recursiva para cada sublista mientras éstas contengan más de un elemento. Una vez terminado este proceso todos los elementos estarán ordenados.

[Explicación extraida de Wikipedia](http://es.wikipedia.org/wiki/Quicksort)

Analiza bien el código, trata de entenderlo y ver las diferencias que tiene con el método de la burbuja, la razón principal que lo hace mejor es por que divide el ordenamiento por partes haciendo una menor cantidad de iteraciones, esta técnica se conoce como "divide y vencerás" que hace referencia a trabajarcon grandes cantidades de datos de una manera más distribuida e inteligente por lo tanto más eficiente.

Si sometemos *quicksort* a la misma prueba que sometimos a la *burbuja* veremos una gran diferencia.

```
var stopwatch = new Stopwatch();
stopwatch.Start();

var arreglo = GenerarArregloNumerico(10000);

Quicksort(arreglo, 0, arreglo.Length - 1);

stopwatch.Stop();

Console.WriteLine(stopwatch.ElapsedMilliseconds);
Console.ReadLine();
```

La prueba con 10mil elementos tomó solamente 2 milisegundos a diferencia de la burbuja que necesitó 2000 milisegundos para terminar el ordenamiento. Con la burbuja hubieran transcurrido minutos para ordenar 50,000 elementos, con quicksort podemos ordenar un millón de elementos en 200 milisegundos.

Es muy notable la diferencia entre las dos soluciones, un código o algoritmo siempre se puede mejorar para realizar menos iteraciones y tomar menos tiempo, eso lo puedes ver siempre como un reto ya que constantemente se hacen investigaciones y avances tecnológicos, probablemente en unos años el método quicksort y otros que hayas visto sean considerados lentos y reemplazados por nuevas tecnologías o ideas, es importante mantenerte a la vanguardia como programador así que no te quedes atrás y busca siempre una mejor solución.

