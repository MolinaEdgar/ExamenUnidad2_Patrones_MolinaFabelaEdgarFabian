
## SIMULACIÓN DE ATERRIZAJE Y DESPLIEGUE DE VUELOS.
-Autor: MOLINA FABELA EDGAR FABIAN - 22210780

-Proyecto: EXAMEN UNIDAD 2.

-Materia: PATRONES DE DISEÑO

-Docente: MARIBEL GUERRRERO

### DESCRIPCIÓN DE FUNCIONAMIENTO
En un aeropuerto, la torre de control es la responsable de coordinar el flujo de aviones que despegan y aterrizan.
Para optimizar el manejo de recursos y garantizar que solo exista una única torre de control, se utiliza el patrón Singleton.
Los aviones que están bajo control se gestionan mediante un Object Pool lo que permite reutilizar instancias existentes en lugar de crear nuevas, limitando en piscina el número total de aviones activos a cinco para funcion del ejemplo de problema.

### Objetivo
Implementar un sistema que permita lo siguiente:

⚫Mantener una única instancia global de la torre de control mediante Singleton.

⚫Administrar un conjunto limitado de aviones mediante un Object Pool.

⚫Permitir la asignación, liberación y reutilización de los aviones según sus estados.

⚫Simular despegue y aterrizaje bajo control de la torre.

### Funcionamiento del sistema de torre de control con Pool de aviones
**1. Creación de la torre de control (Singleton)**
- Solo existe una instancia de la torre, que controla todos los aviones.
- Cada vez que se necesita registrar un evento (despegue o aterrizaje), se usa la misma torre, evitando duplicados.

**2. Creación del Pool de aviones (Object Pool)**
- Se crea un número limitado de aviones (por ejemplo, 5).
- Todos comienzan con el estado “Listo para despegue”.
- Estos aviones se guardan en la lista disponibles.

**3. Asignar un avión para despegar**
- La torre o el sistema selecciona un avión de la lista disponibles.
- El avión se mueve a la lista "En uso" y su estado cambia a “En despegue”.
- Se muestra en consola el cambio de estado y la torre registra el evento.

**4. Liberar un avión (aterrizaje)**
- Cuando el avión termina su vuelo, se mueve de la lista en uso a disponibles.
- Su estado cambia primero a “Recién aterrizado”, y luego a “Listo para despegue” para poder volver a usarlo.
- La torre registra el evento de aterrizaje.

**5. Mostrar estado**
- En cualquier momento se puede ver cuántos aviones están disponibles y cuántos en uso, y los cambios de estado se muestran claramente en consola.

### Ventajas de usar Singleton y Object Pool

| Patrón        | Ventajas |
|---------------|----------|
| **Singleton** | 1. Garantiza una sola instancia de la torre de control, evitando duplicados.<br>2. Acceso global desde cualquier parte del programa.<br>3. Control centralizado de todos los eventos de despegue y aterrizaje. |
| **Object Pool** | 1. Reutiliza aviones, evitando crear y destruir objetos constantemente.<br>2. Mejora el rendimiento y reduce el uso de memoria.<br>3. Facilita la gestión de recursos limitados, controlando cuáles aviones están disponibles y cuáles en uso. |

### Conclusión general
El sistema de torre de control con los patrones Singleton y Object Pool permite gestionar los aviones de manera eficiente y organizada. La torre de control garantiza un punto único de supervisión, mientras que el pool de aviones asegura que los recursos limitados se reutilicen correctamente, evitando desperdicio y optimizando el rendimiento. En conjunto, estos patrones hacen que el sistema sea fiable, rápido y fácil de mantener, reflejando de forma clara cómo se gestionan los vuelos en un entorno controlado.
