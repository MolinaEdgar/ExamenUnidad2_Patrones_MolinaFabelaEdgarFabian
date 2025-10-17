```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;


namespace ExamenUnidad2
{
    public class Avion
    {
        public string Codigo { get; set; }
        public string Estado { get; private set; } //eS el estatus del avion
        public Avion(string codigo)
        {
            Codigo = codigo;
            Estado = "Listo para despegue";
        }
        public void Despegar()
        {
            Estado = "En despegue";
            Console.WriteLine($"\nEl avión {Codigo} ha iniciado su despegue.");
        }
        public void Aterrizar()
        {
            Estado = "Recién aterrizado";
            Console.WriteLine($"\nEl avión {Codigo} ha aterrizado.");
        }
        public void PrepararParaDespegue()
        {
            Estado = "Listo para despegue";
            Console.WriteLine($"\nEl avión {Codigo} está listo para un nuevo despegue.");
        }
        public override string ToString()
        {
            return $"[{Codigo}] - Estado: {Estado}";
        }
    }
}

```
