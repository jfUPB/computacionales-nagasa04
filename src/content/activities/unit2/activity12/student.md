##### 1. Condicionales

Código en C#:
```
int a = 5;
int b = 10;
if (a < b)
{
    a = b;
}
```

Código en ensamblador:
```
@5              
D=A
@a
M=D            
@10             
D=A
@b
M=D           
@a
D=M          
@b
D=D-M         
@set_a_to_b
D;JLT         
@fin
0;JMP           
@b
D=M            
@a
M=D             
```

##### 2. Ciclos While
   
Código en C#:
```
int i = 0;
while (i < 5)
{
    i++;
}
```

Código en ensamblador:
```
@0
D=A
@i
M=D            
@i
D=M
@5
D=D-A          
@end_while
D;JGE          
@i
M=M+1           
@while_condition
0;JMP           
```

##### 3. Ciclos For

Código en C#:
```
for (int j = 0; j < 5; j++)
{
    j = j + 2;
}
```

Código en ensamblador:
```
@0
D=A
@j
M=D             
@j
D=M
@5
D=D-A        
@end_for
D;JGE           
@j
M=M+2       
@for_condition
0;JMP          
```

##### 4. Escritura de Variables por medio de Punteros

Código en C#:
```
int x = 10;
int* ptr = &x;
*ptr = 20;  
```

Código en ensamblador:
```
@10
D=A
@x
M=D           
@x
D=A
@ptr
M=D            
@20
D=A
@ptr
A=M         
M=D             
```
##### 5. Lectura de Variables por medio de Punteros

Código en C#:
```
int y = 30;
int* p = &y;
int z = *p;  
```

Código en ensamblador:
```
@30
D=A
@y
M=D            
@y
D=A
@p
M=D            
@p
A=M            
D=M           
@z
M=D         
```
##### 6. Manipulación de un Arreglo por medio de Punteros

Código en C#:
```
int[] arr = {1, 2, 3, 4, 5};
int* p = &arr[0];
*p = 10;  
```

Código en ensamblador:
```
@1
D=A
@arr
M=D            
@2
D=A
@arr+1
M=D
@3
D=A
@arr+2
M=D 
@4
D=A
@arr+3
M=D
@5
D=A
@arr+4
M=D            
@arr
D=A
@p
M=D           
@10
D=A
@p
A=M        
M=D         
```
##### 7. Llamado a Funciones con Parámetros

Código en C#:
```
int Sumar(int a, int b)
{
    return a + b;
}

int resultado = Sumar(3, 4);
```

Código en ensamblador:
```
@3
D=A
@a
M=D           
@4
D=A
@b
M=D            
@sumar
0;JMP
@resultado
M=D            
(sumar)
@a
D=M
@b
D=D+M          
@retorno_sumar
0;JMP          
```
##### 8. Llamado a Funciones con Retorno de Parámetros

Código en C#:
```
int Cuadrado(int n)
{
    return n * n;
}

int resultado = Cuadrado(5);
```

Código en ensamblador:
```
@5
D=A
@n
M=D             
@cuadrado
0;JMP
@resultado
M=D           
@n
D=M
D=D*M         
@retorno_cuadrado
0;JMP        
```
