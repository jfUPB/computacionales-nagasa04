Ejecucion:
![image](https://github.com/user-attachments/assets/fe383b1e-7b93-40b5-859b-70a055930fed)
Mapa de memoria:
``` c++
+-------------------------------+
| Segmento de código (Text)       |
| Dirección de main():            |
| Dirección de suma():            |
| Dirección de funcionConStatic():|
+-------------------------------+
| Variables globales y estáticas      |
| Dirección de global_inicializada:   |
| Dirección de global_no_inicializada:|
| Dirección de var_estatica (static): |
+-------------------------------+
| Memoria de solo lectura (RO)  |
| Dirección de mensaje_ro:      |
+-------------------------------+
| Heap (memoria dinámica)       |
| Dirección del arrayHeap[0]:   |
| Dirección del arrayHeap[9]:   |
+-------------------------------+
| Stack (variables locales)     |
| Dirección de 'c' en suma():   |
| Dirección de 'b' en main():   |
| Dirección de 'a' en main():   |
+-------------------------------+
```
