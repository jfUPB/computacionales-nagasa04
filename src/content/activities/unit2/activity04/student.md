**Código C++:**

```c++
int a = 10;
int* p;
p = &a;
*p = 20;
```

**Traducción a ensamblador:**

```assembly
// int a = 10;
@a // a refers to some memory location.
M=10 // a=10

// int* p;
@p // p refers to some memory location.

// p = &a;
D=A // D=address of a
@p
M=D // p = address of a

// *p = 20;
@p // p refers to some memory location.
A=M // A=address of a
M=20 // *p = 20 
```

**Explicación:**

* **`@a`:** Se define una dirección de memoria para la variable `a`.
* **`M=10`:** Se escribe el valor **10** en la dirección de memoria de `a`.
* **`@p`:** Se define una dirección de memoria para la variable `p`.
* **`D=A`:** Se copia la dirección de memoria de `a` (que está en el registro `A`) al registro `D`.
* **`@p`:** Se carga la dirección de memoria de `p`.
* **`M=D`:** Se escribe la dirección de memoria de `a` (que está en el registro `D`) en la dirección de memoria de `p`. Ahora `p` apunta a `a`.
* **`@p`:** Se carga la dirección de memoria de `p`.
* **`A=M`:** Se copia la dirección de memoria de `a` (que está en el registro `M` porque `p` apunta a `a`) al registro `A`.
* **`M=20`:** Se escribe el valor **20** en la dirección de memoria que está en el registro `A`, que es la dirección de memoria de `a`. Ahora `a` tiene el valor **20**.

