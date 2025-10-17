```
using System;

namespace ExamenUnidad2
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("=== TORRE DE CONTROL Y POOL DE AVIONES ===\n");
            TorreDeControl torre = TorreDeControl.ObtenerInstancia();
            PoolAviones pool = new PoolAviones(5);
            pool.MostrarEstado();
            pool.AsignarAvion("AV-001");
            pool.MostrarEstado();
            Console.WriteLine("=== FIN DE LA DEMOSTRACIÓN ===");
        }
    }
}
```
