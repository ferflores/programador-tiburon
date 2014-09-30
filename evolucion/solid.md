# SOLID (S): Single Responsibility Principle
######Principio de única responsabilidad

Antes de comenzar a analizar SOLID debo mencionar que el alcance (scope) que tienen estos principios es por lo general para programación orientada a objetos sin embargo son practicas que pueden tener sus equivalentes en otros paradigmas.

El principio de única responsabilidad (presentado por Robert C. Martin) establece basicamente que toda entidad como clase, función, variable, etc. Debe tener una y solo una responsabilidad y debe desconocer lógica de otras entidades. Veamos un ejemplo.

Teniendo una clase Empleado necesitamos saber cuanto pagarle según sus horas trabajadas, una solución rápida y sencilla sería:

```
class Empleado
{
	public decimal SueldoBase { get; set; }

	public decimal CalcularPago(decimal horasTrabajadas)
	{
		return SueldoBase * horasTrabajadas;
	}
}
```
// SET THIS EXAMPLEFROM CalcularPago to Guardar en base de datos

Con el código anterior podemos crear un empleado, asignarle un sueldo base y llamar a su método CalcularPago() pasando como parámetro las horas trabajadas para obtener la cantidad que se le debe pagar.

Basicamente se resuelve el problema establecido pero no es la mejor manera, debemos de mirar más allá de una rápida solución y no me refiero a pensar en el futuro, me refiero a pensar en el cambio y evolución que nuestro código puede tener. Si analizamos el ejemplo anterior, éste rompe el principio de responsabilidad única por que la clase Empleado no debería de saber como se calcula su sueldo y esto no es por que afecte nuestro código o su desempeño, el problema es que mezclar responsabilidades puede ocasionar mala distribución de código y dificultad de mantenimiento
