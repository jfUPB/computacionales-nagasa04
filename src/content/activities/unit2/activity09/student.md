``` c#
using System;

class Program
{
    // Constantes para la pantalla y el teclado
    const int SCREEN_SIZE = 8192;  // Pantalla de 512x256 píxeles, con cada posición representando 16 píxeles
    static int[] SCREEN = new int[SCREEN_SIZE];  // Arreglo que representa la pantalla
    static int KBD;  // Variable que simula la entrada del teclado

    // Variables del programa
    static int[] memory = new int[100];  // Espacio de memoria simulado
    static int D;  // Registro D

    static void Main(string[] args)
    {
        // Simulación del programa en ensamblador

        // @16
        D = memory[16];  // D = M[16]

        // @16
        D = D - memory[16];  // D = D - M[16]

        // @96
        D = memory[96];  // D = M[96]

        // @19
        D = D - memory[19];  // D = D - M[19]

        // @16
        D = memory[16];  // D = M[16]

        // @16
        memory[16] = memory[16] + 1;  // M[16] = M[16] + 1

        // @4
        D = memory[4];  // D = M[4]

        // @16
        D = memory[16];  // D = M[16]

        // Fin del programa
        Console.WriteLine($"Final del programa. Registro D = {D}");
    }
}
```
