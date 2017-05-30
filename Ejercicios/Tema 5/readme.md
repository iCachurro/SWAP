indicándole# Medir prestaciones

## Ejercicio 5.1
**Buscar información sobre cómo calcular el número de conexiones por segundo.**

Con estos comandos se puede ssaber
 ```
 apache2ctl status |grep request  
 netstat -lpan | grep :80 | wc -l
 ```

Pero para tener más información de las conexiones se usa iptstate, indicándole el puerto al que se realizan las peticiones.

```
iptstate -1 -d <ip> -D 80
```


## Ejercicio 5.3
**Buscar información sobre características, disponibilidad para diversos SO, etc de herramientas para monitorizar las prestaciones de un servidor.**

* top --> Nos ayuda a conocer los procesos de ejecución del sistema en tiempo real, el uso de CPU, de memoria, la memoria de intercambio, la caché, tamaño de búfer, PID de proceso, usuario, carga de memoria.

* vmstat --> Nos ofrece estadísticas de uso de la memoria virtual, tales como memoria usada por procesos, paginación, bloques de E/S, etc, así como de la CPU.

* netstat --> Sirve para monitorear el desempeño de la red y solucionar problemas relacionados con la red.
