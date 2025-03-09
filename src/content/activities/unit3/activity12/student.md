**1. Explicación del ciclo de vida de un objeto en el stack versus uno en el heap**

- **Objeto en el stack:**
  - Se crea cuando se entra en el bloque donde está declarado.
  - Se destruye automáticamente al salir del bloque, llamando al destructor.
  - Se gestiona automáticamente por el compilador, sin necesidad de `delete`.
  - Se almacena en la memoria **stack**, que es más rápida y eficiente en términos de acceso y gestión.

- **Objeto en el heap:**
  - Se crea con `new`, lo que reserva memoria dinámicamente.
  - Persiste en memoria hasta que se llama explícitamente a `delete`.
  - Su dirección de memoria se almacena en un puntero.
  - Se encuentra en la memoria **heap**, que permite mayor flexibilidad pero requiere gestión manual para evitar fugas de memoria.

**2. Análisis de la modificación y errores de compilación**

Al ejecutar la segunda versión del código con:
```cpp
{
    cout << "Inicio del bloque 2" << endl;
    Punto* pBloque2 = new Punto(500, 600);
    pBloque2->imprimir();
}
pBloque2->imprimir();
delete pBloque2;
```
Se produce un **error de compilación**, ya que `pBloque2` está declarado dentro del bloque `{}` y deja de existir al salir del bloque. Al intentar acceder a `pBloque2` fuera de ese bloque, el compilador detecta que la variable ya no es válida.

**3. Modificación con `pBloque2` declarado fuera del bloque**

Código corregido:
```cpp
Punto* pBloque2 = nullptr;
{
    cout << "Inicio del bloque 2" << endl;
    pBloque2 = new Punto(500, 600);
    pBloque2->imprimir();
}
pBloque2->imprimir();
delete pBloque2;
```

**Explicación:**
- `pBloque2` ahora se declara antes del bloque, por lo que su puntero sigue existiendo después del bloque.
- El objeto al que apunta `pBloque2` sigue existiendo en el heap, ya que fue creado con `new`.
- No se produce error de compilación, y el objeto se puede usar hasta que se llame a `delete`.

**4. Análisis de por qué `pBloque` se destruye automáticamente, pero `pBloque2` no**

- `pBloque` es un objeto en el stack, por lo que se destruye automáticamente al salir del bloque que lo contiene. El destructor se ejecuta inmediatamente.
- `pBloque2` es un puntero almacenado en el stack, pero el objeto al que apunta está en el heap.
- Aunque el puntero `pBloque2` sigue existiendo después del bloque, el objeto en memoria dinámica solo se libera cuando se llama a `delete pBloque2`.

**5. Ubicación en memoria:**
- **`pBloque`** (instancia en stack) -> Se almacena en el **stack** y se destruye al salir del bloque.
- **`pBloque2`** (puntero en stack) -> Se almacena en el **stack**, pero su objeto está en el **heap** y persiste hasta que se libera manualmente con `delete`.
