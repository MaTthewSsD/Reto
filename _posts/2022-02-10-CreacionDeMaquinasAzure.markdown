---
layout: post
title:  "Creación de infraestructura en Azure"
date:   2022-01-03 11:32:19 +0100
categories: jekyll update
---
###### Reto Game of Networks
## Creación de la Infraestructura en Microsoft AZURE
#### Entrega de: *Denis Alexander Gutiérrez Salvador*
Cabe aclarar, que hay muchas más funciones de las que mostrare en está parte y opciones más optimas para realizarlas, en mi caso, me he centrado en lo que necesitaba.

#### 1. Empezando con Azure:
Selecci%C3%B3n_106.png
Empezamos logeandonos en nuestra cuenta de azure y nos aparecerá algo parecido a esto:

![Selección_106](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/Selección_106.png)

Para poder ver, mejor los servicios que nesitaremos en azure y asociarlo mejor con nuestros entornos virtuales, vamos a "Todos los servicios" , nos saldrá algo parecido a esto:

![image-20220209165130035](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220209165130035.png)

![image-20220209165256173](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220209165256173.png)



Parece mucho al princio, pero a medida que vayamos avanzando se podrá apreciar de cada uno su función y leendo un poco, os sonará de VirtualBox, VMWare o Hyper-V.

Empezaremos creadonos un grupo de recursos, que vendría siendo como una carpeta, en la cual almacenaremos todos nuestros recursos, <i>Redes Virtuales, Máquinas Virtuales, Discos Duros </i> etc. 

Seleccionamos <b>Grupos de Recursos </b>:

![image-20220209165735357](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220209165735357.png)

Una vez dentro, le pondremos de nombre <i> Proyecto-Reto</i> y en la Regió pondremos "(Europe) France Central":

Lás regiones, son los lugares en los cual se montan los recursos, discos duros, máquinas virtuales etc, es el entorno "Real" de nuestro recursos y <B> TODOS LOS RECURSOS TIENE QUE ESTÁR EN LA MISMA REGIÓN</B> ya que puede conllevar a fallo.

Le damos a siguiente:

![image-20220209165845844](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220209165845844.png)

Si queremos que nuestros recursos estén organizado, podemos ponerle etiquetas, en nuestro caso, ya que nuestros recursos serán pocos y dentro del grupo de recursos se puede agrupar, no lo utilizaremos y simplemente le daremos a "siguiente":

![image-20220209170353238](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220209170353238.png)



En el apartado <b>"Revisar y crear"</b> Podemos apreciar que nos hace un <i>check </i> de las cosas que hemos configurado previamente y nos indica que todo está correcto, en caso de error, nos saldría en color rojo un error.

Le damos a<b> "Crear"</b>.

![image-20220209170522264](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220209170522264.png)

Una vez creado nuestro grupo de recursos, nos saldrá algo parecido a esto:

![image-20220209170635908](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220209170635908.png)

Como podemos apreciar, nos saldrá vacía ya que no hemos creado ningún recurso (de momento).



#### 2. Creación de Recursos:

Pinchamos en la parte superior izquierda en "Micrososft Azure" y al apartado "Todos los servicios" y vamos al apartado "Redes":

![image-20220209171153593](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220209171153593.png)

Nos saldrá algo parecido a esto:

![image-20220209171306147](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220209171306147.png)

le damos a "crear" y empezamos:

Seleccionamos nuestro Grupo de recursos, le ponemos el nombre que quisieramos y la región ponemos "France Central" que es la región en la cual nuestro recursos van a estár:

![image-20220209171409400](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220209171409400.png)

Crearemos las redes en base a nuestra infraestructura de red:

![image-20220209171805804](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220209171805804.png)

Crearemos la red " 172.16.0.0/16" y 3 subredes, nuestro DMZ "172.16.100.0/24", la Red-Inerna"172.16.200.0/24" y la "172.16.0.0/24" con salida a internet:

![image-20220209172015353](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220209172015353.png)

Nos tendría que salír algo parecido:

![image-20220210074138310](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210074138310.png)

Dentro de este, para tener una mejor visualización de nuestra red, tendremos a nuestra disposción, dentro del apartado de "Supervisión" > "Diagrama" para poder mejor nuestra red:

![image-20220210075111705](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210075111705.png)

Una vez creado esto, crearemos nuestras máquinas virtuales.

<h4>3. Creación de Máquinas Virtuales</h4>

Para ello vamos a "Todos los servicios" > "Compute" > "Máquinas Virtuales":

![image-20220209165130035](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220209165130035.png)

Le damos a "Crear" en la parte superior izquierda de esta:

![image-20220210082437479](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210082437479.png)

Una vez dentro de está, pondremos los datos y el tamaño de la máquina que queremos crear:



![image-20220210083248217](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210083248217.png)

Como podemos observar, AZURE nos permite configurar muchas cosas de la máquina virtual, también generar un par de claves SSH para que podamos conectarnos o mediante contraseña.

En este caso, al estár en una cuenta de "AZURE FOR STUDENTS" no nos permite crear más máquinas virtuales de las que tenemos actualmente, en este caso podemos realizar las configuraciones previas y revisar que todo este en orden:

En "Discos" podemos elegir el tipo de discos que prefiramos:

![image-20220210083912112](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210083912112.png)

Le damos a "siguiente" y elegimos nuestra <b>red virtual</b> , también podemos elegir a la subred la cual conectaremos nuestra máquina virtual y si queremos asignarle una "IP Pública" en nuestro caso le asignaremos una, para que nuestros compañeros puedan conectarse a las máquinas y realizar las configuraciones necesarias (más adelante veremos como configurar una VPN para que no necesiten de estás).

Le damos a "siguiente":

![image-20220210084744555](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210084744555.png)

Dejamos la configuración por defecto y le damos a "siguiente":

![image-20220210084955718](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210084955718.png)

En "Opciones Avanzadas" podemos indicarle que si queremos crear nuestra máquina e instalarle una extensión, que ejecute algún script o realizar algún otro cambio, en nuestro caso  no realizaremos nada y le damos a "siguiente":

![image-20220210085148108](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210085148108.png)

Una vez visto eso, solo le dariamos a "Revisar y crear" abajo a la izquierda o a "siguiente" hasta el apartado "Revisar y crear".

El resultado seria algo así:

![image-20220210085534499](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210085534499.png)

Realizamos los mismos pasos para nuestra segunda máquina virtual, cambiando las redes:

![image-20220210090828245](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210090828245.png)

<h4> Disco Duro Virtual</h4>

Para crear nuestra máquina virtual de "Pfsense" lo haremos mediante un disco, ya que "pfsense" en azure no lo cubre nuestra suscripción, para ello, crearemos una cuenta de almacenamiento, "Todos los servicios" > "Almacenamiento" > "Cuentas de almacenamiento":

![image-20220209165256173](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220209165256173.png)

le damos a "crear":

![image-20220210091134674](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210091134674.png)



Le indicamos que la cuenta de almacenamiento estará en nuestro proyecto que se encuentra en la región de "France Central":

![](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210092317074.png)



En "Opciones Avanzadas" dejamos los valores por defecto y le damos a "siguiente":

![image-20220210092417832](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210092417832.png)

Dejamos todo lo demás por defecto y le damos  a "Revisar y crear":

![image-20220210113809656](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210113809656.png)



Una vez creado, tendremos algo parecido a esto:



![image-20220210125321128](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210125321128.png)



le damos a "Blob Service" y a "Contenedor":

![image-20220210125402514](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210125402514.png)



Creamos nuestro contenedor, que contendra nuestro VHD con el software de pfsense:

![image-20220210130010975](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210130010975.png)

Elegimos nuestro disco vhd y en "Tipo de blob" elegimos "blob en páginas" y "cargar":

![image-20220210130122852](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210130122852.png)

Una vez subido nuestro disco VHD tendremos que crear un disco para nuestra máquina a partir de este, para ello vamos al apartado "discos"> "crear":

![image-20220210130912760](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210130912760.png)

Le indicamos el nombre del disco (un nombre cualquiera),  blob de origen, en ella cogemos el vhd que hemos creado previamente, en "Tipo de SO" le indicamos "Linux" y en "Genreación de VM" ponemos 1:

![image-20220210131510576](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210131510576.png)

Para el apartado del "Tamaño" le damos a "cambiar" y seleccionamos en "SKU de disco", "HDD estándar":

![image-20220210131814210](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210131814210.png)

Y ponemos el tamaño del disco que hemos creado (VHD) en mi caso es de 16GB:

![image-20220210131852248](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210131852248.png)

Lo demás lo dejamos por defect y le damos a "Revisar y crear".

![image-20220210132056094](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210132056094.png)

Una vez tengamos nuestro disco creado, podremos crear nuestra máquina a partir del disco duro, en el apartado de "redes" le asignamos una "ip publica" para que tenga acceso con el exterior:

![image-20220210132231730](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210132231730.png)

Una vez creada nuestra máquina de pfsense creamos otras 2 interfaces de red, que estarán conectadas una a la <i>DMZ</i> y otra a la <i>red Interna</i>.

Para ello vamos a "Todos los servicios" > "Redes" > "Interfaces de red" y le damos a "Crear":

![image-20220210134603012](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210134603012.png)

![image-20220210140517903](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210140517903.png)

Le damos a "Revisar y crear" y realizamos lo mismo con la interfaz de red de la "Red-Interna".

![image-20220210141048018](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210141048018.png)



Dentro de la configuración del pfsense, le adjuntaremos otras 2 tarjetas de red, que estarán conectadas a las otras 2 redes:

![image-20220210132935357](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210132935357.png)



Para ello, vamos a "Adjuntar Interfaz de red" y seleccionamos las interfaces de red que hemos creado:

![image-20220210141448498](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/mage-20220210141448498.png)



![image-20220210141556805](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210141556805.png)

Realizamos el mismo proceso para la segunda interfaz de red:

![image-20220210141641852](https://raw.githubusercontent.com/DealG/Reto/main/imagenes/image-20220210141641852.png)












