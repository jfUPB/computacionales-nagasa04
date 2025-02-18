1. Condicionales

Código en C#:
```
int a = 5;
int b = 10;
if (a < b)
{
    a = b;
}
```

Código en ensamblador Hack:
```
@5              // Carga 5 en el registro D
D=A
@a
M=D             // a = 5

@10             // Carga 10 en el registro D
D=A
@b
M=D             // b = 10

@a
D=M             // D = a
@b
D=D-M           // D = a - b

@set_a_to_b
D;JLT           // Si D < 0 (a < b), salta a set_a_to_b

@fin
0;JMP           // Salta al final

(set_a_to_b)
@b
D=M             // D = b
@a
M=D             // a = b

(fin)
```

2. Ciclos While
   
Código en C#:
```
int i = 0;
while (i < 5)
{
    i++;
}
```

Código en ensamblador Hack:
```
@0
D=A
@i
M=D             // i = 0

(while_condition)
@i
D=M
@5
D=D-A           // D = i - 5
@end_while
D;JGE           // Si i >= 5, termina el ciclo

@i
M=M+1           // i++

@while_condition
0;JMP           // Repite el ciclo

(end_while)
```

3. Ciclos For

Código en C#:
```
for (int j = 0; j < 5; j++)
{
    j = j + 2;
}
```

Código en ensamblador Hack:
```
@0
D=A
@j
M=D             // j = 0

(for_condition)
@j
D=M
@5
D=D-A           // D = j - 5
@end_for
D;JGE           // Si j >= 5, termina el ciclo

@j
M=M+2           // j = j + 2

@for_condition
0;JMP           // Repite el ciclo

(end_for)
```

4. Escritura de Variables por medio de Punteros

Código en C#:
```
int x = 10;
int* ptr = &x;
*ptr = 20;  // Escribir por medio del puntero
```

Código en ensamblador Hack:
```
@10
D=A
@x
M=D             // x = 10

@x
D=A
@ptr
M=D             // ptr = &x

@20
D=A
@ptr
A=M             // Accede a la dirección almacenada en ptr
M=D             // *ptr = 20
```
5. Lectura de Variables por medio de Punteros

Código en C#:
```
int y = 30;
int* p = &y;
int z = *p;  // Leer por medio del puntero
```

Código en ensamblador Hack:
```
@30
D=A
@y
M=D             // y = 30

@y
D=A
@p
M=D             // p = &y

@p
A=M             // Accede a la dirección almacenada en p
D=M             // D = *p
@z
M=D             // z = *p
```
6. Manipulación de un Arreglo por medio de Punteros

Código en C#:
```
int[] arr = {1, 2, 3, 4, 5};
int* p = &arr[0];
*p = 10;  // Cambiar el primer elemento del arreglo
```

Código en ensamblador Hack:
```
@1
D=A
@arr
M=D             // arr[0] = 1
@2
D=A
@arr+1
M=D             // arr[1] = 2
@3
D=A
@arr+2
M=D             // arr[2] = 3
@4
D=A
@arr+3
M=D             // arr[3] = 4
@5
D=A
@arr+4
M=D             // arr[4] = 5

@arr
D=A
@p
M=D             // p = &arr[0]

@10
D=A
@p
A=M             // Accede a la dirección almacenada en p
M=D             // *p = 10
```
7. Llamado a Funciones con Parámetros

Código en C#:
```
int Sumar(int a, int b)
{
    return a + b;
}

int resultado = Sumar(3, 4);
```

Código en ensamblador Hack:
```
@3
D=A
@a
M=D             // a = 3

@4
D=A
@b
M=D             // b = 4

@sumar
0;JMP

(retorno_sumar)
@resultado
M=D             // resultado = a + b

(sumar)
@a
D=M
@b
D=D+M           // D = a + b

@retorno_sumar
0;JMP           // Retorna a la llamada
```
8. Llamado a Funciones con Retorno de Parámetros

Código en C#:
```
int Cuadrado(int n)
{
    return n * n;
}

int resultado = Cuadrado(5);
```

Código en ensamblador Hack:
```
@5
D=A
@n
M=D             // n = 5

@cuadrado
0;JMP

(retorno_cuadrado)
@resultado
M=D             // resultado = n * n

(cuadrado)
@n
D=M
D=D*M           // D = n * n

@retorno_cuadrado
0;JMP           // Retorna a la llamada
```
