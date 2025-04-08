
## Explicación de la Copia de Objetos en C++ y C#

### Copia en C++
En C++, cuando se copia un objeto utilizando `=` (asignación por valor), se crea una copia independiente de los datos del objeto original. Es decir:
- `copia = original;` genera un nuevo objeto `copia` con los mismos valores que `original`.
- Modificar `copia` **no afecta** a `original`, ya que cada uno tiene su propia ubicación en memoria.
- Si `original` es modificado a través de un puntero (`p = &original`), los cambios afectarán a `original` y, por ende, se reflejarán en cualquier uso del puntero.

### Copia en C#
En C#, la copia de objetos depende del tipo de objeto:
- **Tipos por valor (structs):** se copian igual que en C++, generando una copia independiente.
- **Tipos por referencia (clases):** la copia no genera un nuevo objeto, sino que `copia` y `original` apuntan al mismo espacio en memoria.
- En el código de ejemplo, `copia = original;` hace que ambos apunten al mismo objeto, por lo que modificar `copia` **también modifica** `original`.

## Diferencias Encontradas
| Característica | C++ (Copia por valor) | C# (Copia por referencia en clases) |
|--------------|---------------------|----------------------------------|
| Copia independiente | Sí | No (a menos que se implemente una copia profunda) |
| Cambios en la copia afectan al original | No | Sí |
| Ubicación en memoria | `copia` y `original` ocupan direcciones distintas | `copia` y `original` comparten la misma dirección |
