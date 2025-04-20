##### Respuestas a las preguntas
1. ¿Por qué la versión de swapPorValor no logra intercambiar los valores de x e y en main()?
- *swapPorValor:* recibe los valores de x e y como copias, por lo que cualquier cambio dentro de la función no afecta las variables originales. Solo se modifican las copias locales de a y b.

2. ¿Cómo y por qué logran las otras dos funciones (por referencia y por puntero) modificar las variables originales?
- *swapPorReferencia:* usa referencias, que actúan como alias de las variables originales. Cualquier cambio dentro de la función se refleja en las variables originales.
- *swapPorPuntero:* recibe direcciones de memoria de las variables originales y las modifica usando el operador de indirección *, lo que también afecta directamente las variables originales.

3. ¿Cuáles son las ventajas y consideraciones de usar referencias versus punteros en este caso?
- *Referencias:* Son más seguras y más fáciles de usar, ya que no requieren desreferenciación (*). Sin embargo, deben estar inicializadas al declararse.
- *Punteros:* Son más flexibles porque pueden apuntar a nullptr o cambiar la dirección a la que apuntan. Sin embargo, requieren mayor manejo de memoria y pueden introducir errores si no se usan correctamente.
