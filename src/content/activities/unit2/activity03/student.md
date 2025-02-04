**Análisis de los programas:**

**Programa con `while`:**

```c++
//Adds 1+...+100.
 int i=1;
 int sum=0;

 while(i <=100){
    sum+= i;
    i++;
 }
```

* Inicializa las variables `i` y `sum` con los valores **1** y **0** respectivamente.
* El ciclo `while` se ejecuta mientras la condición `i <= 100` sea verdadera.
* Dentro del ciclo, se suma el valor de `i` a `sum` y luego se incrementa `i` en **1**.

**Programa con `for`:**

```c++
//Adds 1+...+100.
int sum=0;
for(int i = 1; i <=100; i++){
   sum+= i;
}
```

* Inicializa la variable `sum` con el valor **0**.
* El ciclo `for` tiene tres partes:
    * **Inicialización:** `int i = 1;`  se inicializa la variable `i` con el valor **1**.
    * **Condición:** `i <= 100;` se evalúa la condición del ciclo. Si es verdadera, se ejecuta el cuerpo del ciclo.
    * **Incremento:** `i++;` se incrementa el valor de `i` en **1** al final de cada iteración del ciclo.
* Dentro del ciclo, se suma el valor de `i` a `sum`.

**Equivalencia de los programas:**

Ambos programas realizan la misma tarea: sumar los números del **1** al **100**. La única diferencia es la forma en que se estructura el ciclo. El ciclo `for` es más compacto y combina la inicialización, la condición y el incremento en una sola línea.

**Traducción a ensamblador del ciclo `for`:**

```assembly
// Adds 1+...+100.
@sum // sum refers to some memory location.
M=0 // sum=0
@i // i refers to some memory location.
M=1 // i=1
(LOOP)
@i
D=M // D=i
@100
D=D-A // D=i-100
@END
D;JGT // If(i-100)>0 gotoEND
@i
D=M // D=i
@sum
M=D+M // sum=sum+i
@i
M=M+1 // i=i+1
@LOOP
0;JMP // GotoLOOP
(END)
@END
0;JMP // Infinite loop
```

**Comparación de las versiones en ensamblador:**

Las versiones en ensamblador del `while` y del `for` son muy similares. La principal diferencia es que la versión del `for` combina la inicialización de `i` con la primera iteración del ciclo, mientras que la versión del `while` realiza la inicialización antes del ciclo.

