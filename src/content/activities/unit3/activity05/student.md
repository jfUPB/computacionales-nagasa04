Experimento 3: Modificar el segmento de datos (variables globales)
¿Qué ocurre?
El programa imprimirá los valores iniciales de las variables globales y luego modificará sus valores correctamente
![image](https://github.com/user-attachments/assets/f4152f3b-5ad9-4f0e-bf7f-f2e5d528aab1)

¿Por qué ocurre esto?
- Las variables globales se almacenan en la sección de datos del programa, la cual sí permite modificaciones.
- global_inicializada = 42; está en la sección de datos inicializada.
- global_no_inicializada; está en la sección BSS (Block Started by Symbol), que almacena variables no inicializadas (y el sistema las inicializa en 0 automáticamente).
- Como esta memoria es de lectura y escritura (R/W), se pueden modificar sin problema.


Experimento 4: Modificar la variable local estática fuera de la función
¿Qué ocurre?
El código no compila
¿Por qué ocurre esto?
- var_estatica es una variable estática dentro de funcionConStatic(), lo que significa que su alcance es local a esa función.
- Solo puede ser accedida dentro de funcionConStatic().
- En main(), el compilador no la reconoce porque su alcance es limitado.
