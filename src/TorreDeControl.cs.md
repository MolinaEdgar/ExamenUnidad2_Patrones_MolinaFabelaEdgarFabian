```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ExamenUnidad2
{
    public class TorreDeControl
    {
        private static TorreDeControl? instancia;
        private static readonly object bloqueo = new object();
        public static TorreDeControl ObtenerInstancia()
        {
            if (instancia == null)
            {
                lock (bloqueo)
                {
                    if (instancia == null)
                        instancia = new TorreDeControl();
                }
            }
            return instancia;
        }
        public void RegistrarEvento(string mensaje)
        {
            Console.WriteLine($"[TORRE DE CONTROL]: {mensaje}");
        }
    }
}
```
