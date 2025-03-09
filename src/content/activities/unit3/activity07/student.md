1. **¿Cuál es la diferencia entre un constructor y un destructor en C++?**
   - Un **constructor** es una función especial que se ejecuta automáticamente cuando un objeto de la clase es creado. Se usa para inicializar variables y asignar memoria.
   - Un **destructor** se ejecuta automáticamente cuando un objeto sale del ámbito o es eliminado. Se usa para liberar recursos y evitar fugas de memoria.

2. **¿Cuál es la diferencia entre un objeto y una clase en C++?**
   - Una **clase** es una plantilla o un modelo que define atributos y métodos.
   - Un **objeto** es una instancia de una clase, creada en memoria con valores específicos.

3. **¿Qué diferencia notas entre el objeto `Punto` en C++ y C#?**
   - En **C++**, el objeto `Punto` se almacena en el **stack** si se declara sin punteros, mientras que en **C#** siempre es una referencia en el **heap**.
   - En **C++**, los constructores y destructores se ejecutan automáticamente, pero en **C#** el recolector de basura controla la destrucción del objeto.

4. **¿Qué es `p` en C++ y qué es `p` en C#?**
   - En **C++**, `p` es un **objeto** almacenado directamente en el stack.
   - En **C#**, `p` es una **referencia** a un objeto almacenado en el heap.

5. **¿En qué parte de memoria se almacena `p` en C++ y en C#?**
   - En **C++**, si se declara como `Punto p(10,20);`, se almacena en el **stack**.
   - En **C#**, `Punto p = new Punto(10,20);` almacena el objeto en el **heap**, mientras que `p` es una referencia en el stack.

6. **Captura de pantalla del depurador mostrando la variable `p` y su dirección de memoria.**
   - (Incluir captura de pantalla donde se ve la dirección de `p` y los valores de `x` y `y` en la memoria.)

7. **¿Qué observaste con el depurador acerca de `p`?**  
   - `p` tiene una dirección de memoria en el stack.
   - Los valores de `x` e `y` se almacenan en posiciones consecutivas de la memoria.
   - La asignación en memoria sigue el orden **little-endian**.

8. **Según lo que observaste, ¿qué es un objeto en C++?**
   - Un objeto en **C++** es una entidad en memoria que ocupa un bloque específico en el stack (o en el heap si se usa `new`).
   - Su existencia depende de su ámbito: si se declara en una función, se destruye al salir de ella.
   - La memoria ocupada por un objeto en el stack se libera automáticamente, mientras que en el heap requiere `delete` para ser liberada manualmente.
