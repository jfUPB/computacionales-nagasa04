1. Reflexión sobre la lista enlazada con 3 y 4 nodos
  Si dibujamos una lista enlazada con 3 nodos, tendríamos algo así:
```
[Head] -> [Nodo 1] -> [Nodo 2] -> [Nodo 3] -> nullptr
```
- Head apunta al primer nodo.
- Cada nodo tiene una posición y un puntero next que apunta al siguiente nodo.
- Tail apunta al último nodo (Nodo 3).
- size = 3.
  
Si agregamos un nodo más:

```
[Head] -> [Nodo 1] -> [Nodo 2] -> [Nodo 3] -> [Nodo 4] -> nullptr
```
- Tail ahora apunta a Nodo 4.
- size = 4.

Cada nodo adicional extiende la lista, pero la estructura sigue siendo la misma.

2️. Reflexión sobre los punteros head y tail en LinkedList
- ¿Dónde apuntan head y tail en una lista con 3 nodos?
  - head apunta al primer nodo (Nodo 1).
  - tail apunta al último nodo (Nodo 3).
  - size = 3.

- ¿Qué pasaría si LinkedList no tuviera el puntero head?
  - No podríamos recorrer la lista desde el inicio.
  - Si solo tuviéramos tail, no podríamos acceder a los nodos previos.

- ¿Qué pasaría si no tuviera el puntero tail?
  - Para agregar un nuevo nodo, tendríamos que recorrer toda la lista para encontrar el último nodo, lo que haría la operación push_back más lenta.

- ¿Qué pasaría si no tuviera el entero size?
  - No podríamos saber cuántos nodos tiene la lista sin recorrerla completamente.

3️. Reflexión sobre el destructor
- ¿Por qué es necesario liberar la memoria manualmente en C++?
  - En C++, la memoria dinámica asignada con new no se libera automáticamente.
  - Si no liberamos la memoria de los nodos al destruir la lista, se generarán fugas de memoria (memory leaks).
  - Con el método clear(), evitamos que la memoria quede ocupada después de que la lista ya no se use.

4️. Reflexión sobre el método push_back
  Antes y después de agregar nodos:

Caso size = 0 (lista vacía):
```
head = nullptr, tail = nullptr, size = 0
```

Después de agregar un nodo:
```
head -> [Nodo 1] -> nullptr
tail -> [Nodo 1]
size = 1
```
Caso size = 1:
```
head -> [Nodo 1] -> nullptr
tail -> [Nodo 1]
size = 1
```
Después de agregar Nodo 2:
```
head -> [Nodo 1] -> [Nodo 2] -> nullptr
tail -> [Nodo 2]
size = 2
```
Caso size = 2:
```
head -> [Nodo 1] -> [Nodo 2] -> nullptr
tail -> [Nodo 2]
size = 2
```
Después de agregar Nodo 3:
```
head -> [Nodo 1] -> [Nodo 2] -> [Nodo 3] -> nullptr
tail -> [Nodo 3]
size = 3
```
5. Reflexión sobre el método pop_back
Antes y después de eliminar nodos:

Caso size = 2:
```
head -> [Nodo 1] -> [Nodo 2] -> nullptr
tail -> [Nodo 2]
size = 2
```
Después de eliminar Nodo 2:
```
head -> [Nodo 1] -> nullptr
tail -> [Nodo 1]
size = 1
```
Caso size = 1:
```
head -> [Nodo 1] -> nullptr
tail -> [Nodo 1]
size = 1
```
Después de eliminar Nodo 1:
```
head = nullptr
tail = nullptr
size = 0
```

6️. Reflexión sobre el método clear
- clear() recorre todos los nodos y los elimina uno por uno.
- Cuando se ejecuta en una lista con 3 nodos:
```
[Head] -> [Nodo 1] -> [Nodo 2] -> [Nodo 3] -> nullptr
```
Después de clear():
```
head = nullptr
tail = nullptr
size = 0
```
Sin clear(), los nodos seguirían ocupando memoria.

7️. Reflexión sobre el código de ofApp
- setup(): Inicializa la lista con 20 nodos en el centro de la pantalla.
- update(): Mueve los nodos de la serpiente interpolando entre su posición actual y el mouse.
- draw(): Dibuja la serpiente usando ofMesh.
- keyPressed():

c: Limpia la lista.

a: Agrega un nodo en una posición aleatoria.

r: Elimina el último nodo.

s: Guarda una captura de pantalla.

8️. Reflexión sobre glm::mix
- glm::mix(a, b, factor) interpola entre a y b, donde factor es la proporción de mezcla:
- Si factor = 0.2, el nodo se mueve un 20% hacia la posición del mouse en cada actualización.
- Así se logra el efecto de movimiento suave.
