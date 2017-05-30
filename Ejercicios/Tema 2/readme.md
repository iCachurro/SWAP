# Alta disponibilidad

## Ejercicio 2.1
**Calcular la disponibilidad del sistema si tenemos dos réplicas de cada elemento (en total 3 elementos en cada subsistema).**

Fórmula: As = Ac1 + ( (1 – Ac1) * Ac2 )

Web --> 97.75% + (1 - 97.75%) * 85% = 99.6625%  
Application --> 99% + (1 - 99%) * 90% = 99.9%  
Database --> 99.9999% + (1-99.9999%) * 99.9% = 99.9999999%  
DNS --> 99.96% + (1 - 99.96%) * 98% = 99.9992%  
Firewall --> 97.75% + (1 - 97.75%) * 85% = 99.6625%  
Switch --> 99.99% + (1 - 99.99%) * 99% = 99.9999%
Data Center --> 99.99% + (1 - 99.99%) * 99.99% = 99.999999%  
ISP --> 99.75% + (1 - 99.75%) * 95% = 99.9875%  

Disponibilidad Total --> 99.6625% * 99.9% * 99.9999999% * 99.9992% * 99.6625% * 99.9999% * 99.999999% * 99.9875% = 99,2034961%   

| Componente | Sin réplica | Con 1 réplica  | Con 2 réplica |
| - | - | - | - |
| Web | 85% | 97.75% | 99.6625% |
| Application | 90% | 99% | 99.9% |
| Database | 99.9% | 99.9999% | 99.9999999% |
| DNS | 98% | 99.96% | 99.9992% |
| Firewall | 85% | 97.75% | 99.6625% |
| Switch | 99% | 99.99% | 99.9999% |
| Data Center | 99.99% | 99.99% | 99.999999% |
| ISP | 95% | 99.75% | 99.9875% |


## Ejercicio 2.2
**Buscar frameworks y librerías para diferentes lenguajes que permitan hacer aplicaciones altamente disponibles con relativa facilidad.**

- Process Manager 2 --> Es un gestor de procesos para aplicaciones Node.js con un balanceador de carga integrado.
- Symfony --> Es un frameWork PHP para acelerar la creación y el mantenimiento de aplicaciones web.
- Heartbeat --> es un programa para la administración de clústeres.


## Ejercicio 2.3
**¿Cómo analizar el nivel de carga de cada uno de los subsistemas en el servidor? Buscar herramientas y aprender a usarlas.**

- Top --> Muestra todos los procesos activos del sistema con su información.
- GTmetrix --> Se usa para evaluar la carga de una web unificando Google Page Speed y Yahoo! YSlow.
- Vmstat --> Nos da la información sobre las estadísticas de la memoria virtual.


## Ejercicio 2.4
**Buscar ejemplos de balanceadores software y hardware (productos comerciales).**
- Software
    - Nginx
    - Haproxy
    - Pound
- Hardware
    - Router Cisco
    - LoadMaster

**Buscar productos comerciales para servidores de aplicaciones.**
- WebLogic de Oracle.
- WebSphere de IBM.

**Buscar productos comerciales para servidores de almacenamiento.**  
Los sistemas NAS de las principales marcas Synology y QNAQ.
