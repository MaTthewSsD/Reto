SERVIDOR DE CORREO EN OPENSUSE

Instalación del servicio de correo

![image-20220220203450873](image-20220220203450873.png)

Iniciación del sistema y comprobación de funcionamiento

![image-20220220205539501](image-20220220205539501.png)

Instalamos el cliente mailutils

![image-20220220210441866](image-20220220210441866.png)

![image-20220220211134303](image-20220220211134303.png)

## Fichero de configuración Postfix

Hacemos una copia de seguridad y procedemos con la configuración

![image-20220224031115304](image-20220224031115304.png)

Establecemos el nombre de dominio

![image-20220224031309578](image-20220224031309578.png)

Proveerá a los usuarios de la red interna

![image-20220224041414040](image-20220224041414040.png)

El tamaño máximo de envío de mensajes

![image-20220224041508791](image-20220224041508791.png)

El formato del buzón

![image-20220224041632906](image-20220224041632906.png)

Funcionamiento de envíos de manera local

Creamos la usuaria Laura, le enviamos un mail y consultamos el log

![image-20220224134808702](image-20220224134808702.png)

Comprobamos su home para ver el log

![image-20220224132605560](image-20220224132605560.png)

![image-20220224134724052](image-20220224134724052.png)
