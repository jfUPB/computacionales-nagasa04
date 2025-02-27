- ¿En qué direcciones de memoria se implementan las variables i, sum?

No se puede determinar la dirección de memoria exacta de i y sum a partir del código ensamblador. Esto depende de cómo se haya configurado el simulador y la memoria disponible.
Sin embargo, lo importante es que el ensamblador asigna direcciones de memoria únicas a cada variable.

- ¿Cuál es la diferencia entre la dirección de una variable y su contenido?

La dirección de una variable es la ubicación física en la memoria donde se almacena el valor de la variable.
El contenido de una variable es el valor real que se almacena en esa ubicación de memoria.
Explica cómo se implementa la condición i <= 100

- La condición i <= 100 se implementa mediante la instrucción D;JGT.

Primero, se calcula la diferencia entre i y 100 y se guarda en el registro D.
La instrucción JGT (Jump if Greater Than) salta a la etiqueta END si el valor de D es mayor que 0.
En otras palabras, si i es mayor que 100, se salta a END, lo que significa que la condición i <= 100 no se cumple.
