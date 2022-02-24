###### Reto Game of Networks

## Creación de Proxy en PFSENSE

#### Entrega de: *Denis Alexander Gutiérrez Salvador*

#### 1. Empezando con PFSENSE:

Instalamos "Squid":

Vamos a "Gerente de Empaquetación" y buscamos "squid":

![image-20220223232731491](F:\2 ASIR\Servicios\RETO\proxy\image-20220223232731491.png)

Luego de instalarlo, vamos a "Services" y buscamos "Squid Proxy Server":

![image-20220223232912216](F:\2 ASIR\Servicios\RETO\proxy\image-20220223232912216.png)

![image-20220223232936025](F:\2 ASIR\Servicios\RETO\proxy\image-20220223232936025.png)

![image-20220223233202221](F:\2 ASIR\Servicios\RETO\proxy\image-20220223233202221.png)

Le damos a "Check to enable the Squid proxy" y seleccionamos la interfaz donde va a actuar, en nuestro caso es "DMZ":

![image-20220223233424947](F:\2 ASIR\Servicios\RETO\proxy\image-20220223233424947.png)

Habilitamos el log:

![image-20220223233525989](F:\2 ASIR\Servicios\RETO\proxy\image-20220223233525989.png)

Primero vamos a acceder a "www.taapas.es" para luego bloquearlo:

![image-20220223233940378](F:\2 ASIR\Servicios\RETO\proxy\image-20220223233940378.png)

Vamos a probarlo, bloqueando el acceso a "www.taapas.es", para ello vamos a "Blacklist":

![image-20220224004013425](F:\2 ASIR\Servicios\RETO\proxy\image-20220224004013425.png)

Y le damos a "guardar":

![image-20220223234016512](F:\2 ASIR\Servicios\RETO\proxy\image-20220223234016512.png)

Vamos a "Internet Properties" y ponemos nuestro proxy y el puerto:

![image-20220224004847274](proxy/image-20220224004847274.png)







