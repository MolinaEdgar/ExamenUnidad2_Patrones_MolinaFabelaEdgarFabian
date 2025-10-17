```
using System;
using System.Collections.Generic;
using System.Linq;

namespace ExamenUnidad2
{
    public class PoolAviones
    {
        private List<Avion> disponibles;
        private List<Avion> enUso;
        private int limite;

        public PoolAviones(int cantidad)
        {
            limite = cantidad;
            disponibles = new List<Avion>();
            enUso = new List<Avion>();

            for (int i = 1; i <= limite; i++)
            {
                disponibles.Add(new Avion($"AV-{i:000}"));
            }

            Console.WriteLine($"Pool creado con {limite} aviones.\n");
            MostrarTodosLosAviones();
        }

        public void MostrarTodosLosAviones()
        {
            Console.WriteLine("=== ESTADO INICIAL DE AVIONES ===");
            foreach (var avion in disponibles)
            {
                Console.WriteLine($"{avion.Codigo} - {avion.Estado}");
            }
            Console.WriteLine();
        }

        public void MostrarEstado()
        {
            Console.WriteLine($"Disponibles: {disponibles.Count} | En uso: {enUso.Count}\n");
        }

        public void AsignarAvion(string codigo)
        {
            Avion avion = disponibles.FirstOrDefault(a => a.Codigo == codigo);

            if (avion != null)
            {
                disponibles.Remove(avion);
                enUso.Add(avion);

                avion.Despegar();
                Console.WriteLine($"{avion.Codigo} ahora está '{avion.Estado}'");

                TorreDeControl.ObtenerInstancia().RegistrarEvento($"El avión {codigo} fue asignado para despegar.");
            }
            else
            {
                Console.WriteLine($"El avión {codigo} no está disponible.");
            }
        }
    }
}

```
