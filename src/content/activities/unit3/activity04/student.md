Experimento 1: Modificar el segmento de texto (código)
¿Qué ocurre?
- El programa intentará modificar la dirección de memoria donde está almacenada la función main(). Sin embargo, en la mayoría de los sistemas modernos, esto provocará un error de segmentación (segmentation fault) y el programa se detendrá abruptamente.

¿Por qué ocurre esto?
- El segmento de código (text segment) es una región de solo lectura en la memoria del programa.
- En sistemas operativos modernos, la memoria donde está almacenado el código ejecutable se protege contra escritura por medidas de seguridad (prevención de modificaciones maliciosas).
- Al intentar escribir en esa región, el sistema operativo detecta una violación de acceso y termina el programa.
_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
Experimento 2: Modificar el segmento de datos (constante global)
¿Qué ocurre?
- El programa intentará modificar el valor almacenado en la constante mensaje_ro, pero probablemente se detenga con un error de segmentación.

¿Por qué ocurre esto?
- La variable mensaje_ro es una constante global (const char* const mensaje_ro = "Hola, memoria de solo lectura";).
- El compilador normalmente almacena las cadenas literales ("Hola, memoria de solo lectura") en un segmento de solo lectura (RODATA).
- Como el sistema detecta que intentas modificar memoria de solo lectura, lanza un error de segmentación.
