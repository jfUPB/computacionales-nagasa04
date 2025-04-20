Funciones de Cada Tipo de Instrucción

A-instructions:
Función: Las A-instructions se utilizan para establecer el valor de la dirección del registro A o para cargar un valor inmediato en el registro A. Permiten acceder a direcciones de memoria o valores constantes.

C-instructions:
Función: Las C-instructions realizan operaciones aritméticas o lógicas y pueden mover datos entre registros, así como modificar el flujo de ejecución del programa mediante saltos. Son las instrucciones más versátiles y complejas del lenguaje ensamblador Hack.

2. Representación en Binario

A-instructions:

Formato: Se representan con un código de 16 bits, donde el primer bit es 0. Los siguientes 15 bits representan la dirección o el valor inmediato.
Ejemplo de formato: 0xxxxxxxxxxxxxxx (donde x son los bits que representan el valor).

C-instructions:

Formato: Se representan con un código de 16 bits, donde el primer bit es 1. La instrucción se divide en varios campos:
Bits 15-13: Código de operación (comp).
Bits 12-10: Destino (dest).
Bits 9-7: Salto (jump).
Ejemplo de formato: 111accccccddddjjj (donde a, c, d, y j son los bits que representan los diferentes campos).

3. Ejemplos de Instrucciones

A-instructions:
Instrucción	Representación Binaria	Descripción

@5	0000000000000101	Carga el valor 5 en el registro A.

@16	0000000000010000	Carga el valor 16 en el registro A.

@200	0000000011001000	Carga el valor 200 en el registro A.

C-instructions:
Instrucción	Representación Binaria	Descripción

D=A	1110001100000000	Asigna el valor del registro A al registro D.

D=D+1	1110111110001000	Incrementa el valor del registro D en 1.

0;JMP	1110101010000111	Realiza un salto incondicional a la dirección especificada en el registro A.
