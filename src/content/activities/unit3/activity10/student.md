![image](https://github.com/user-attachments/assets/579ef9b0-5817-48e3-a436-36a7e0561d40)

## Comportamiento al Llamar a `cambiarNombre`

Después de llamar a la función `cambiarNombre(original, "cambiado")`, se observa lo siguiente:
- Se crea una **copia** del objeto `original`, llamada `p`, dentro de la función.
- `p.name` se modifica a "cambiado".
- Al salir de la función, el destructor de `p` se ejecuta, eliminando esta copia.
- `original` permanece sin cambios porque `p` fue una copia independiente.

Por eso, aparece el mensaje:
```
Destructor: Punto cambiado(70, 80) destruido.
```
Esto indica que la copia de `original` (`p`) fue destruida, pero el objeto `original` sigue existiendo.

## Ubicación en Memoria de `original` y `p`
- `original` está en el **stack** (pila) de la función `main`.
- `p` está en el **stack** de la función `cambiarNombre` y se destruye al salir de la función.
- Son objetos **distintos** con diferentes direcciones de memoria.

## Modificación de `cambiarNombre` para Usar Referencias
### Código Modificado:
```cpp
void cambiarNombre(Punto& p, string nuevoNombre) {
  p.name = nuevoNombre;
}
```
### Comportamiento Observado:
- Ahora `p` es una **referencia** a `original`, por lo que no se crea una copia.
- Se cambia directamente `original.name` a "cambiado".
- No hay mensaje de destructor porque no se creó ni eliminó ningún objeto nuevo.
- `original` sí cambia su nombre de forma permanente.

## Modificación de `cambiarNombre` para Usar Punteros
### Código Modificado:
```cpp
void cambiarNombre(Punto* p, string nuevoNombre) {
  p->name = nuevoNombre;
}

int main() {
    Punto original("original",70, 80);
    original.imprimir();

    cambiarNombre(&original, "cambiado");
    original.imprimir();
    return 0;
}
```
### Comportamiento Observado:
- Se pasa la **dirección** de `original` a la función.
- Dentro de `cambiarNombre`, `p` es un puntero que apunta a `original`.
- Se accede y modifica `original` usando `p->name`.
- `original` cambia su nombre correctamente sin crear copias.

## Diferencia entre Pasar un Objeto por Valor, Referencia y Puntero
| Método | Comportamiento |
|--------|---------------|
| **Por valor** (`Punto p`) | Se crea una copia independiente. Modificaciones no afectan al original. |
| **Por referencia** (`Punto& p`) | Se modifica el objeto original directamente. No hay copias. |
| **Por puntero** (`Punto* p`) | Similar a referencia, pero se usa `->` para acceder a los miembros. |
