Experimento 5: Variables locales estática vs no estática

¿Qué ocurre?

El programa ejecutará un ciclo de 5 iteraciones llamando a dos funciones:

- funcionSinStatic() que usa una variable local normal.
- funcionConStatic() que usa una variable estática.

![image](https://github.com/user-attachments/assets/95f54b57-5125-4d73-8205-b9d194450de1)

¿Por qué ocurre esto?
- var_no_estatica (sin static):
  - Se crea y destruye en cada llamada de funcionSinStatic().
  - Siempre se inicializa en 100 y nunca cambia su valor fuera de la función.

- var_estatica (con static):
  - Se crea solo una vez y mantiene su valor entre llamadas.
  - Su valor aumenta en cada iteración porque no se reinicia al salir de la función.
 
Experimento 6: Modificar el segmento de Heap

¿Qué ocurre?

Después de liberar la memoria con delete[] arrayHeap;, intentamos acceder a arrayHeap[0]. Esto es un error porque:
- delete[] arrayHeap; libera la memoria asignada.
- arrayHeap ya no apunta a memoria válida.

Posibles salidas:
- Comportamiento inesperado: Algunos sistemas pueden imprimir un valor erróneo porque la memoria ya no está reservada.
- Crash o segmentación fault: En algunos sistemas, acceder a memoria liberada puede hacer que el programa falle inmediatamente.

Consecuencias de no liberar memoria (new sin delete)
- Fugas de memoria: Si nunca liberamos la memoria, el programa consumirá más y más RAM.
- Baja eficiencia: La memoria se desperdicia, lo que ralentiza el sistema.
- Cierre inesperado: En sistemas con poca memoria, el programa podría cerrarse o colapsar.

¿Por qué usar delete[] para arreglos?
- delete solo libera un único objeto, mientras que delete[] libera todos los elementos de un arreglo dinámico.
- No usar delete[] correctamente puede causar comportamiento indefinido.
