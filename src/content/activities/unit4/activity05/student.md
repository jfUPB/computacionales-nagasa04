1. **¿Qué aspectos de la implementación de la cola te resultaron más fáciles? ¿Por qué?**  
Uno de los aspectos que me resultó más fácil fue la comprensión de la estructura básica de la cola y su funcionamiento general. Como la cola sigue un orden FIFO (First In, First Out), me fue sencillo entender la importancia de los punteros *front* y *rear* para manejar la entrada y salida de datos. Además, el concepto de agregar elementos al final y eliminarlos del principio me pareció intuitivo al relacionarlo con situaciones cotidianas, como una fila de espera.

2. **¿Qué parte te pareció más difícil o te tomó más tiempo? ¿Cómo la resolviste?**  
La parte más difícil fue gestionar correctamente la memoria y evitar fugas. Como la estructura usa asignación dinámica de memoria con *new* y *delete*, tuve problemas asegurando que cada nodo eliminado se liberara correctamente. Al principio, olvidé actualizar el puntero *rear* cuando la cola quedaba vacía, lo que causaba errores. Para resolverlo, revisé ejemplos adicionales, depuré el código paso a paso y agregué comprobaciones para asegurarme de que la memoria se gestionara correctamente.

3. **Si pudieras repetir esta actividad, ¿Qué harías diferente para mejorar tu desempeño?**  
Si tuviera que repetir esta actividad, dedicaría más tiempo a planificar la implementación antes de escribir el código. También me gustaría probar diferentes enfoques, como utilizar *std::queue* en lugar de una implementación manual, para comparar las ventajas y desventajas de cada método. Además, practicaría con ejemplos más simples antes de integrar la cola en una aplicación gráfica con openFrameworks.

4. **¿Cómo se relaciona lo que aprendiste en esta unidad con otras áreas de la programación o de tu carrera?**  
El concepto de colas es fundamental en muchas áreas de la programación, como estructuras de datos, sistemas operativos y desarrollo de videojuegos. En sistemas en tiempo real, las colas se usan para manejar eventos, tareas o buffers. También es una estructura clave en algoritmos de inteligencia artificial y redes. Aprender a implementarlas desde cero me ayuda a comprender mejor su funcionamiento y a optimizar su uso en otras aplicaciones.

5. **¿Qué aprendizajes de esta unidad te servirán en futuros proyectos?**  
Aprender a manejar estructuras de datos dinámicas como la cola me será útil en cualquier proyecto que requiera organizar y procesar datos de manera eficiente. También reforzó mi comprensión del uso de punteros, memoria dinámica y buenas prácticas en C++. Esto me preparará para desarrollar programas más eficientes y escalables, ya sea en aplicaciones interactivas, desarrollo de videojuegos o cualquier otro proyecto que requiera manejo de estructuras de datos complejas.
