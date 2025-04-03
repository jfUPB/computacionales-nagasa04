**Análisis de la Programación Orientada a Objetos en C++**

**1. Análisis de la clase `ofApp` en memoria**
- **Hipótesis:** Se espera ver la instancia de `ofApp` con una lista de punteros a `Particle*` en memoria.
- **Observaciones:** La instancia de `ofApp` existe en memoria solo en tiempo de ejecución, con referencias a los objetos `Particle*`.

**2. Análisis de `CircularExplosion` en memoria**
- **Observaciones:** `CircularExplosion` almacena primero los datos de `ExplosionParticle` y `Particle`.

**3. Análisis de la `_vtable` y los métodos virtuales**
- **Observaciones:** Cada clase tiene su propia `_vtable` con referencias a los métodos virtuales correspondientes.
- **Comparación con `StarExplosion`:** Cada objeto tiene una `_vtable` diferente según los métodos sobrescritos.

**4. Encapsulamiento**
- **Observaciones del primer experimento:** Solo `publicVar` es accesible desde `main()`, los demás generan errores de compilación.
- **Segundo experimento:** `privateVar` no puede accederse directamente, pero sí a través de un método público.
- **Tercer experimento:** Se puede acceder a atributos privados usando `reinterpret_cast`.

**5. Herencia en memoria**
- **Observaciones:** En `CircularExplosion`, los atributos de `Particle` aparecen primero, seguidos por `ExplosionParticle` y `CircularExplosion`.
- **Herencia múltiple:** Se pueden combinar varias clases base en un solo objeto.

**6. Polimorfismo y el método `update()`**
- **Observaciones:** `update()` se ejecuta de manera diferente según el tipo real del objeto.

**7. Relación entre métodos virtuales y polimorfismo**
- **Observaciones:** La `_vtable` almacena las direcciones de los métodos virtuales.

**8. Importancia de la tabla de funciones virtuales**
- **Uso:** Permite la resolución dinámica de métodos en tiempo de ejecución.

