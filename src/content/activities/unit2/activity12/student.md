## Ejemplos de Conceptos de Programación en Alto Nivel y Ensamblador:

**1. Condicionales:**

**Alto Nivel (C):**

```c
#include <stdio.h>

int main() {
  int numero = 10;

  if (numero > 5) {
    printf("El número es mayor que 5\n");
  } else {
    printf("El número es menor o igual que 5\n");
  }

  return 0;
}
```

**Ensamblador:**

```assembly
(inicio)
@numero
D=M
@5
D=D-A
@mayor
D;JGT
@menor
0;JMP

(mayor)
@mensaje_mayor
D=A
@imprimir
0;JMP

(menor)
@mensaje_menor
D=A
@imprimir
0;JMP

(mensaje_mayor)
A=100 // Dirección del mensaje "El número es mayor que 5\n"
0;JMP

(mensaje_menor)
A=108 // Dirección del mensaje "El número es menor o igual que 5\n"
0;JMP

(imprimir)
// Código para imprimir el mensaje
.
.
.

@fin
0;JMP

(numero)
A=10
0;JMP

(fin)
0;JMP
```

**2. Ciclos While:**

**Alto Nivel (C):**

```c
#include <stdio.h>

int main() {
  int i = 0;

  while (i < 10) {
    printf("%d ", i);
    i++;
  }

  return 0;
}
```

**Ensamblador:**

```assembly
(inicio)
@i
D=M
@10
D=D-A
@bucle
D;JLT
@fin
0;JMP

(bucle)
@i
D=M
@imprimir
0;JMP

(imprimir)
// Código para imprimir el valor de i
.
.
.

@i
M=M+1
@inicio
0;JMP

(i)
A=0
0;JMP

(fin)
0;JMP
```

**3. Ciclos For:**

**Alto Nivel (C):**

```c
#include <stdio.h>

int main() {
  for (int i = 0; i < 5; i++) {
    printf("%d ", i);
  }

  return 0;
}
```

**Ensamblador:**

```assembly
(inicio)
@i
M=0
@bucle
0;JMP

(bucle)
@i
D=M
@5
D=D-A
@fin
D;JGE
@imprimir
0;JMP

(imprimir)
// Código para imprimir el valor de i
.
.
.

@i
M=M+1
@bucle
0;JMP

(i)
A=0
0;JMP

(fin)
0;JMP
```

**4. Escritura de Variables por medio de Punteros:**

**Alto Nivel (C):**

```c
#include <stdio.h>

int main() {
  int numero = 10;
  int *ptr = &numero;

  *ptr = 20;

  printf("El valor de numero es: %d\n", numero);

  return 0;
}
```

**Ensamblador:**

```assembly
(inicio)
@numero
D=A
@ptr
M=D
@20
D=A
@ptr
A=M
M=D
@numero
D=M
@imprimir
0;JMP

(imprimir)
// Código para imprimir el valor de numero
.
.
.

@fin
0;JMP

(numero)
A=10
0;JMP

(ptr)
A=0
0;JMP

(fin)
0;JMP
```

**5. Lectura de Variables por medio de Punteros:**

**Alto Nivel (C):**

```c
#include <stdio.h>

int main() {
  int numero = 10;
  int *ptr = &numero;

  printf("El valor de numero es: %d\n", *ptr);

  return 0;
}
```

**Ensamblador:**

```assembly
(inicio)
@numero
D=A
@ptr
M=D
@ptr
A=M
D=M
@imprimir
0;JMP

(imprimir)
// Código para imprimir el valor de *ptr
.
.
.

@fin
0;JMP

(numero)
A=10
0;JMP

(ptr)
A=0
0;JMP

(fin)
0;JMP
```

**6. Manipulación de un Arreglo por medio de Punteros:**

**Alto Nivel (C):**

```c
#include <stdio.h>

int main() {
  int arreglo[5] = {1, 2, 3, 4, 5};
  int *ptr = arreglo;

  for (int i = 0; i < 5; i++) {
    printf("%d ", *ptr);
    ptr++;
  }

  return 0;
}
```

**Ensamblador:**

```assembly
(inicio)
@arreglo
D=A
@ptr
M=D
@i
M=0
@bucle
0;JMP

(bucle)
@i
D=M
@5
D=D-A
@fin
D;JGE
@imprimir
0;JMP

(imprimir)
@ptr
A=M
D=M
// Código para imprimir el valor de *ptr
.
.
.

@ptr
M=M+1
@i
M=M+1
@bucle
0;JMP

(i)
A=0
0;JMP

(fin)
0;JMP

(arreglo)
A=100 // Dirección del inicio del arreglo
0;JMP

(ptr)
A=0
0;JMP
```

**7. Llamado a Funciones con Parámetros:**

**Alto Nivel (C):**

```c
#include <stdio.h>

void sumar(int a, int b) {
  printf("La suma de %d y %d es: %d\n", a, b, a + b);
}

int main() {
  sumar(5, 10);

  return 0;
}
```

**Ensamblador:**

```assembly
(inicio)
@5
D=A
@R0
M=D
@10
D=A
@R1
M=D
@sumar
0;JMP

(sumar)
@R0
D=M
@R1
D=D+M
@imprimir
0;JMP

(imprimir)
// Código para imprimir la suma
.
.
.

@fin
0;JMP

(fin)
0;JMP
```

**8. Llamado a Funciones con Retorno de Parámetros:**

**Alto Nivel (C):**

```c
#include <stdio.h>

int multiplicar(int a, int b) {
  return a * b;
}

int main() {
  int resultado = multiplicar(5, 10);
  printf("El resultado de la multiplicación es: %d\n", resultado);

  return 0;
}
```

**Ensamblador:**

```assembly
(inicio)
@5
D=A
@R0
M=D
@10
D=A
@R1
M=D
@multiplicar
0;JMP

(multiplicar)
@R0
D=M
@R1
D=D*M
@R2
M=D
@fin_multiplicar
0;JMP

(fin_multiplicar)
@R2
D=M
@resultado
M=D
@imprimir
0;JMP

(imprimir)
// Código para imprimir el resultado
.
.
.

@fin
0;JMP

(resultado)
A=0
0;JMP

(fin)
0;JMP
```
