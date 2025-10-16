# MOLINA FABELA EDGAR FABIAN - 22210780
## SIMULACIÓN DE ATERRIZAJE Y DESPLIEGUE DE VUELOS.

### DESCRIPCIÓN DE FUNCIONAMIENTO
En un aeropuerto, la torre de control es la responsable de coordinar el flujo de aviones que despegan y aterrizan.
Para optimizar el manejo de recursos y garantizar que solo exista una única torre de control, se utiliza el patrón Singleton.
Los aviones que están bajo control se gestionan mediante un Object Pool lo que permite reutilizar instancias existentes en lugar de crear nuevas, limitando en piscina el número total de aviones activos a cinco para funcion del ejemplo de problema.
Cada avión puede encontrarse en uno de los tres estados operativos:
🟢 Listo para despegue (esperando a despegar)
🟡 En despegue (en vuelo)
🔵 Recién aterrizado (vuelo terminado)

### Objetivo
Implementar un sistema que permita lo siguiente:
⚫Mantener una única instancia global de la torre de control mediante Singleton.
⚫Administrar un conjunto limitado de aviones mediante un Object Pool.
⚫Permitir la asignación, liberación y reutilización de los aviones según sus estados.
⚫Simular despegue y aterrizaje bajo control de la torre.
