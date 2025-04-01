#### ¿Qué es una cola y cómo funciona el principio FIFO?
Una **cola** es una estructura de datos en la que los elementos se organizan de manera lineal y se siguen el principio **FIFO (First In, First Out)**, que significa "el primero en entrar es el primero en salir".

Imagina una fila en un supermercado: la primera persona en llegar es la primera en ser atendida, y las personas que llegan después deben esperar su turno.

### **Implementación de enqueue() y dequeue() en una cola**
Una cola puede implementarse con arreglos o con listas enlazadas. En este caso, la implementaremos con una lista enlazada en C++.

#### **Definición de la estructura de la cola**
```cpp
struct Nodo {
    int dato;
    Nodo* siguiente;
};

class Cola {
private:
    Nodo* frente;
    Nodo* final;
public:
    Cola() {
        frente = nullptr;
        final = nullptr;
    }

    void enqueue(int valor) {
        Nodo* nuevoNodo = new Nodo();
        nuevoNodo->dato = valor;
        nuevoNodo->siguiente = nullptr;
        
        if (final == nullptr) {
            frente = final = nuevoNodo;
        } else {
            final->siguiente = nuevoNodo;
            final = nuevoNodo;
        }
    }

    int dequeue() {
        if (frente == nullptr) {
            throw std::runtime_error("La cola está vacía");
        }
        
        int valor = frente->dato;
        Nodo* temp = frente;
        frente = frente->siguiente;
        delete temp;

        if (frente == nullptr) {
            final = nullptr;
        }
        
        return valor;
    }
};
```

### **Explicación de enqueue() y dequeue()**
- **enqueue(int valor)**: Agrega un nuevo nodo al final de la cola. Si la cola está vacía, tanto `frente` como `final` apuntan al nuevo nodo. Si no está vacía, el nuevo nodo se agrega al final y `final` se actualiza.
- **dequeue()**: Elimina el nodo del frente de la cola y devuelve su valor. Si la cola queda vacía, `final` también se actualiza a `nullptr`.

### **Un error común y cómo evitarlo**
Un error común es no manejar correctamente el caso en que la cola está vacía. Si intentamos hacer `dequeue()` cuando `frente` es `nullptr`, el programa puede fallar. Para evitar esto, verificamos si `frente == nullptr` antes de intentar eliminar un nodo y lanzamos una excepción si la cola está vacía.

Con esta explicación y el código de ejemplo, un estudiante podrá entender cómo funciona una cola y cómo implementarla manualmente. ¡Espero que te haya sido útil!

