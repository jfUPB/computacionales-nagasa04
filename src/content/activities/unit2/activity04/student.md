**Código C++:**

```c++
int a = 10;
int* p;
p = &a;
*p = 20;
```

**Traducción a ensamblador:**

```assembly
@a
M=10
@p 
D=A
@p
M=D
@p
A=M
M=20
```
