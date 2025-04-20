```c++
@60
D=A
@9
D=D+A
@6
M=D
@0
0;JMP
```

A continuación, se presenta la tabla que documenta cada ciclo de instrucción:

Tabla: Ciclo Fetch-Decode-Execute

1	0	@60	Carga el valor 60 en el registro A.	El PC se incrementa a 1.	A = 60, D = 0, M = (sin cambios)

2	1	D=A	Asigna el valor del registro A a D.	D = 60. El PC se incrementa a 2.	A = 60, D = 60, M = (sin cambios)

3	2	@9	Carga el valor 9 en el registro A.	El PC se incrementa a 3.	A = 9, D = 60, M = (sin cambios)

4	3	D=D+A	Suma el valor de D (60) y A (9), almacena en D.	D = 69. El PC se incrementa a 4.	A = 9, D = 69, M = (sin cambios)

5	4	@6	Carga la dirección 6 en el registro A.	El PC se incrementa a 5.	A = 6, D = 69, M = (sin cambios)

6	5	M=D	Almacena el valor de D (69) en la dirección de memoria 6.	M[6] = 69. El PC se incrementa a 6.	A = 6, D = 69, M[6] = 69

7	6	@0	Carga la dirección 0 en el registro A.	El PC se incrementa a 7.	A = 0, D = 69, M[6] = 69

8	7	0;JMP	Realiza un salto incondicional a la dirección 0.	El PC se establece en 0.	A = 0, D = 69, M[6] = 69
