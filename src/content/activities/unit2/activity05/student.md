```c++
int a = 10;
int b = 5;
int *p;
p = &a;
b = *p;

//Ensamblador
@10
D=A      
@a
M=D      
@5
D=A   
@b
M=D       
@a
D=A  
@p
M=D       
@p
A=M       
D=M      
@b
M=D     
```
