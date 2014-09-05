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
