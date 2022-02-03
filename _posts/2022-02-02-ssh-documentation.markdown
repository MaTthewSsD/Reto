---
layout: post
title:  "SSH documentation"
date:   2022-02-02 11:32:19 +0100
categories: jekyll update
---
**Conexion remota con SSH**

Compruebo que hay conexión entre la máquina "dmzserver" y "dmzclient":

![image1](../images/image1.png)



Confirmo que hay conexión entre la máquina "dmzclient" y "dmzserver":

![image2](../images/image2.png)



(Si la conexión entre equipos se pierde reiniciar los sistemas).

Para usar el protocolo SSH instalo en la máquina servidora el paquete openssh-server:

![image3](../images/image3.png)

![image3A](../images/image3-16434540278501.png)



Instalo en la máquina cliente el paquete openssh-client:

![image5](../images/image5.png)



Me conecto desde la máquina cliente a la servidora:

![image7](../images/image7.png)



Hago una copia de seguridad de "/etc/ssh/sshd_config" y editamos para mejorar la seguridad:

Cambio el puerto 22 por defecto para establecer la conexión por el 2222.

Bloqueo el acceso root en las conexiones remotas.

![image9](../images/image9.png)



Cambio el tiempo que tenemos para acceder al servidor con contraseña:

![image10](../images/image10.png)



Cambio el máximo de intentos para entrar:

![image12](../images/image12.png)



Reinicio el servicio con "/etc/init.d/sshd restart".



Confirmo que me puedo conectar:

![image13](../images/image13.png)



































