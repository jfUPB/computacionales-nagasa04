``` c++
@0
D=A

@1
M=A

(INICIO)
@M
D=M

@6
D=D-A
@SALIR
D;JGE  


@12
D=M 
@M
D=D+A 
@12
M=D    

@M
M=M+1  

@INICIO
0;JMP 

(SALIR)
```
