# La red de una granja web

## Ejercicio 3.1
**Buscar con qué órdenes de terminal o herramientas gráficas podemos configurar bajo Windows y bajo Linux el enrutamiento del tráfico de un servidor para pasar el tráfico desde una subred a otra.**

* Linux

Usamos en Linux el comando ``` ip route ``` para mostrar la tabla de enrutamiento.  
Una vez escogido la ip que queremos desviar, ponemos ``` ip route add <subred> via <IPdestino> ``` y desviara al tráfico donde a donde queremos.

* Windows

En Windows tenemos la aplicación Routing and Remote Access, en la cual nos mostrara todas IPs y sus rutas, y desde los menús desplegables tendremos la opción de desviar el tráfico.


## Ejercicio 3.2
**Buscar con qué órdenes de terminal o herramientas gráficas podemos configurar bajo Windows y Linux el filtrado y bloqueo de paquetes.**

* Linux

Con el Firewall Iptables de linux, el bloqueo de cualquier paquete entrante o saliente se hace con la siguiente orden:
```
iptables -A INPUT -j DROP
iptables -A OUTPUT -j DROP
```

* Windows

En el Firewall que viene instalado de serie en el servidor, haríamos lo propio desde sus distintos menús.
