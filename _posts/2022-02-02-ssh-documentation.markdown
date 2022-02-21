---
layout: post
title:  "SSH en red DMZ"
date:   2022-01-28 11:32:19 +0100
categories: jekyll update
---
**Conexion remota con SSH**

Comprobar la conexión entre "dmzserver" y "dmzclient":
image1.png
![image1](https://raw.githubusercontent.com/MaTthewSsD/Reto/gh-pages/images/image1.png)



Confirmar la conexión:

![image2](https://raw.githubusercontent.com/MaTthewSsD/Reto/gh-pages/images/image2.png)



(Si la conexión entre equipos se pierde, reiniciar los sistemas).

Para usar el protocolo SSH hay que instalar el paquete openssh-server:

![image3](https://raw.githubusercontent.com/MaTthewSsD/Reto/gh-pages/images/image3.png)



En la máquina cliente, instalar el paquete openssh-client:

![image5](https://raw.githubusercontent.com/MaTthewSsD/Reto/gh-pages/images/image5.png)



Conexión desde la máquina cliente a la servidora:

![image7](https://raw.githubusercontent.com/MaTthewSsD/Reto/gh-pages/images/image7.png)



Hacer una copia de seguridad de "/etc/ssh/sshd_config" y editar para mejorar la seguridad:

Modificación del puerto 22 por defecto para establecer la conexión por el 2222.

Bloquear el acceso root en las conexiones remotas.

![image9](https://raw.githubusercontent.com/MaTthewSsD/Reto/gh-pages/images/image9.png)



Modificar el tiempo que tenemos para acceder al servidor con contraseña:

![image10](https://raw.githubusercontent.com/MaTthewSsD/Reto/gh-pages/images/image10.png)



Modificar el número máximo de intentos para entrar:

![image12](https://raw.githubusercontent.com/MaTthewSsD/Reto/gh-pages/images/image12.png)



Reiniciar el servicio con "/etc/init.d/sshd restart".



Confirmar que se puede conectar:

![image13](https://raw.githubusercontent.com/MaTthewSsD/Reto/gh-pages/images/image13.png)



































