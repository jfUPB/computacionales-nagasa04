## Captura de Pantalla
![image](https://github.com/user-attachments/assets/ce8b0c82-501c-4d2e-ac1d-1db0863b40d2)

## Explicación de la Diferencia entre Objetos en el Stack y en el Heap

En C++, los objetos pueden crearse en dos lugares distintos de la memoria:

1. **Stack (Pila):**
   - Se utiliza para almacenar variables locales y tiene un acceso más rápido.
   - La memoria es administrada automáticamente: cuando una función termina, las variables locales son eliminadas.
   - En nuestro programa, `pStack` es un objeto almacenado en el stack.

2. **Heap (Montículo):**
   - Se utiliza para almacenar datos dinámicos con `new`.
   - La memoria debe ser gestionada manualmente por el programador usando `delete`.
   - En nuestro programa, `pHeap` es un puntero que apunta a un objeto almacenado en el heap.

## Análisis de `pStack` y `pHeap`

1. **`pStack`** es un objeto directamente alojado en el stack.
   - Es decir, `pStack` es una instancia de `Punto` con una dirección de memoria propia dentro del stack.

2. **`pHeap`** es un puntero a un objeto en el heap.
   - `pHeap` contiene la dirección del objeto creado dinámicamente.
   - En otras palabras, `pHeap` no es un objeto, sino una referencia a un objeto en el heap.

## Observaciones en Memory1

Al ingresar la dirección de `&pHeap` en la ventana Memory1 y comparar con la pestaña de Locals, se observa:
- `&pHeap` almacena la dirección del objeto en el heap.
- En Locals, `pHeap` muestra la dirección del objeto y sus valores (`x=50, y=60`).
