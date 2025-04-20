1. ¿Cómo se crea la lista enlazada?
En el archivo ofApp.h, la lista se declara como un atributo de la clase ofApp:
```
std::list<glm::vec2> snake;
```
Esta lista se inicializa automáticamente cuando se crea una instancia de ofApp.

2. ¿Cómo se añaden los primeros nodos a la lista?
En el método setup(), se añaden 20 nodos en la posición central de la pantalla:
```
for (int i = 0; i < 20; i++) {
    snake.emplace_back(ofGetWidth() / 2, ofGetHeight() / 2);
}
```
Se usa emplace_back() para insertar nuevos nodos al final de la lista.

3. ¿Cómo se añaden nodos adicionales a la lista?
En el método keyPressed(), cuando se presiona la tecla 'a', se agrega un nuevo nodo en una posición aleatoria:
```
else if (key == 'a') {
    snake.emplace_back(ofRandomWidth(), ofRandomHeight());
}
```

4. ¿Cómo se eliminan nodos de la lista?
En keyPressed(), cuando se presiona la tecla 'r', se elimina el último nodo de la lista con pop_back():
```
else if (key == 'r') {
    if (!snake.empty()) {
        snake.pop_back();
    }
}
```

5. ¿Cómo se limpia la lista?
En keyPressed(), cuando se presiona la tecla 'c', la lista se vacía completamente con clear():
```
if (key == 'c') {
    snake.clear();
}
```
6. ¿Cómo se verifica si la lista está vacía?
Antes de eliminar un nodo en la función keyPressed(), se usa:
```
if (!snake.empty()) { 
    snake.pop_back();
}
```
La función empty() devuelve true si la lista no tiene elementos.
