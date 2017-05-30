# Balanceo de carga

## Ejercicio 4.1
**Buscar información sobre cuánto costaría en la actualidad un mainframe. Comparar precio y potencia entre esa máquina y una granja web de unas prestaciones similares.**

El IBM Z13 es un mainframe recientemente sacado por IBM, que tiene un precio estimado de $75000, en comparación a una granja web, este tiene la desventaja de que estas tiene un menor coste tanto en la compra como en mantenimiento. Se habla de un ahorro en torno al 50%.


## Ejercicio 4.2
**Buscar información sobre precio y características de balanceadores hardware específicos. Compara las prestaciones que ofrecen unos y otros.**

* ZNA 6508 Hardware Appliance (ZEVENET)  
    - Precio: 2795 euros.  
    - CPU: Intel® CoreTM i5-6500, 3.20 GHz CON 4 cores  
    - Memoria: DDR4 2133 MHz, ECC, 4GB RAM (max. 32 GB)  
    - Almacenamiento: 16GB mSATA.  
    - Conexiones concurrentes: Soporte L2, L3, L4 y L7.  

* LM-3000 Server Load Balancer (KEMP)
    - Precio: 4875 dólares.
    - CPU: Intel Pentium Dual Core G850 @ 2.9GHz
    - Memoria: 4GB
    - Almacenamiento: 32GB SSD
    - Conexiones concurrentes: 8,600,000 (L4), 69,000 (L7, HTTP requests/sec).


## Ejercicio 4.3
**Buscar información sobre los métodos de balanceo que implementan los dispositivos recogidos en el ejercicio 4.2**

* ZNA 6508 Hardware Appliance:
    - Por peso (weight)
    - Round Robin
    - Carga de CPU
    - Memoria
    - Menor número de conexiones (least connections)
    - Menor tiempo de respuesta (least response)

* LM-3000 Server Load Balancer
    - "SDN Adaptive"
    - Round Robin
    - Round Robin con peso (weighted Round Robin)
    - Menor número de conexiones (least connections)
    - Menor número de conexiones con peso (weighted least connections)
    - "Agent‐based Adaptive"
    - "Chained Failover (Fixed Weighting)
    - IP Hash
    - "Layer 7 Content Switching"
    - "Global Server Load Balancing (GSLB)"
    - "AD Group based traffic steering"


## Ejercicio 4.4
**Instala y configura en una máquina virtual el balanceador ZenLoadBalancer.**

una vez instalado el sistema basado en Debian, lo configuramos para acceder desde otra máquina, quedando un resultado casi idéntico al de la práctica 3.


## Ejercicio 4.5
**Probar las diferentes maneras de redirección HTTP. ¿Cuál es adecuada y cuál no lo es para hacer balanceo de carga global? ¿Por qué?**

Para indicar redireccionamiento, se pueden usar varios códigos de estado HTTP: 301, 302, 303, 307 y 308.
- 301 --> La redirección es permanente y se puede guardar en caché.
- 302 --> La redirección es temporal y no se puede guardar en caché por defecto.
- 303 y 307 --> La redirección es temporal. La 303 nunca se puede guardar en caché y la 307 no se guarda por defecto.
- 308 --> La redirección es permanentes y se guarda en caché por defecto.

La 302 la mejor opción si queremos tener varios servidores o páginas para mostrar en función de la localización del cliente.  


## Ejercicio 4.6
**Buscar información sobre los bloques de IP para los distintos países o continentes. Implementar en JavaScript o PHP la detección de la zona desde donde se conecta un usuario**

PHP GeoIPLocation Library es una herramienta que nos permite saber desde que país se realiza la conexión, y aquí esta el código en PHP que nos permite saber la localización.

```
<?php

  include("geoiploc.php"); // Must include this

  // ip must be of the form "192.168.1.100"
  // you may load this from a database
  $ip = $_SERVER["REMOTE_ADDR"];
  echo "Your IP Address is: " . $ip . "<br />";

  echo "Your Country is: ";
  // returns country code by default
  echo getCountryFromIP($ip);
  echo "<br />\n";

  // optionally, you can specify the return type
  // type can be "code" (default), "abbr", "name"

  echo "Your Country Code is: ";
  echo getCountryFromIP($ip, "code");
  echo "<br />\n";

  // print country abbreviation - case insensitive
  echo "Your Country Abbreviation is: ";
  echo getCountryFromIP($ip, "AbBr");
  echo "<br />\n";

  // full name of country - spaces are trimmed
  echo "Your Country Name is: ";
  echo getCountryFromIP($ip, " NamE ");
  echo "<br />\n";

?>
```


## Ejercicio 4.7
**Buscar información sobre métodos y herramientas para implementar GSLB.**

Existe la herramienta NetScaler para implementar GSLB, que se configura sobre su propia línea de comandos de la siguiente forma:

```
set ns config -ipaddress<IPAddress> -netmask<subnetMask>
add ns ip<IPAddress> <subnetMask> -type<type>
add route Network<subnetMask> <gateway>
set system user<userName> <password>
save ns config
reboot
```
