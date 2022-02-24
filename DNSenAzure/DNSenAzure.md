## DNS en Azure.

En la máquina Ubuntu de Azure se instalará un servidor DNS primario, que resolverá consultas DNS de forma directa y reversa. Para ello se debe seguir los siguientes pasos:

1. /etc/resolv.conf
2. Instalar bind9.
3. Modificar ficheros de configuración.
4. Crear ficheros de zona de resolución directa e indirecta.
5. Probar la configuración.

## 1. Configurar /etc/resolv.conf.

Debemos configurar antes este fichero para poder realizar las consultas. Sustituimos la dirección 127.0.0.53 que viene por defecto en el Ubuntu y ponemos la dirección de localhost para que el propio servidor haga realice las consultas.![image-20220224001948225](image-20220224001948225.png)

## 2. Instalación del bind9.

Se debe actualizar primero las librerías del sistema y luego instalar servicio con `apt-get install`![image-20220220155436546](image-20220220155436546.png)

Se instala el bind9:![image-20220220155517325](image-20220220155517325.png)

Para comprobar que el servicio ya funciona hay que observar que el bind9 está corriendo.![image-20220220155926044](image-20220220155926044.png)

Y observar que los puertos del DNS estén escuchando.![image-20220220160020319](image-20220220160020319.png)

Ahora que el servicio funciona ya se pueden modificar los ficheros de configuración del servidor.

## 3. Modificar los ficheros de configuración.

El primer fichero a modificar será `/etc/bind/named.conf.local`, antes de realizar una configuración hay que hacer una copia de seguridad. ![image-20220220162627343](image-20220220162627343.png)

En estas líneas de configuración se debe especificar los ficheros de zona. Estos ficheros los usará el servidor para cuando reciba peticiones DNS y este usará estos archivos para resolverlos, de forma directa e inversa.

![image-20220224002154574](image-20220224002154574.png)

Luego haremos mismo con `/etc/bind/named.conf.options`, en él se se especifica que en la línea de forwarders se usen los servidores de Google para respoder a cosultas DNS.![image-20220224002133303](image-20220224002133303.png)

## 4. Crear ficheros de zona de resolución directa e indirecta.

Vamos a crear los siguientes ficheros en los que he especificado en el fichero named.conf.local:

- Crear y configurar el fichero de resolución directa: db.ancs.xyz.

Aquí en el fichero se debe indicar 

![image-20220224003501173](image-20220224003501173.png)

Este será el fichero resultado. Le asignamos aquí al nombre de www.ancs.xyz a la IP pública de nuestro servidor como registro A

- Crear y configurar el fichero de resolución inversa: db.20.47.80.

Para la resolución inversa funciona de forma similar, esta tenemos que asociar la IP con el nombre.![image-20220224004408712](image-20220224004408712.png)

## 5. Probar la configuración.

Para probar la configuración podemos probar con nslookup, host o dig como comandos. De forma local. 

Primero vamos a probar con la resolución directa.

- host.

  ![image-20220224005920656](image-20220224005920656.png)

- nslookup.

  ![image-20220224010026200](image-20220224010026200.png)

  

  Y ahora con la resolución inversa, que resolverá la dirección IP, y nos responderá la consulta con el servidor DNS asociado.

  - host.

  ![image-20220224011426420](image-20220224011426420.png)

  - nslookup.

    ![image-20220224011446027](image-20220224011446027.png)

  

  

  



