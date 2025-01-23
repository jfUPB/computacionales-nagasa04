#### Mi programa

``` asm
@1 
D=A 
@2 
D=D+A 
@16 
M=D 
@6 
0;JMP
```

**Explicación** 
##### Explicación del Programa Original

1. `@1`: Carga el valor **1** en el registro **A**.
2. `D=A`: Mueve el valor de **A** (1) al registro **D**.
3. `@2`: Carga el valor **2** en el registro **A**.
4. `D=D+A`: Suma el valor en **D** (1) con el valor en **A** (2), resultando en **3**.
5. `@16`: Carga el valor **16** en el registro **A**.
6. `M=D`: Almacena el valor de **D** (3) en la posición de memoria **16**.
7. `@6`: Carga el valor **6** en el registro **A**.
8. `0;JMP`: Salta a la dirección **0**, creando un bucle infinito.

##### Modificaciones para Sumar 60 y 9

Para realizar la suma de **60** y **9** y almacenar el resultado en la posición de memoria **6**, haremos los siguientes cambios:

1. Cargar **60** en un registro.
2. Cargar **9** y sumarlos.
3. Almacenar el resultado en la posición de memoria **6**.
4. Hacer un salto a la posición **0**.

``` asm
@60
D=A
@9
D=D+A
@6
M=D
@0
0;JMP   
``` 
