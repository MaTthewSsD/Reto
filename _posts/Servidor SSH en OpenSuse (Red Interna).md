Instalación Servidor SSH en OpenSuse (Red Interna) 

Máquina servidora: OpenSuse. IP 172.16.200.2

Comenzamos ejecutando un sudo zipper update. En OpenSuse el comando zypper sustituye al apt o apt-get.

![img](unknown.png)

Instalo el servidor ssh.

![img](unknown-16434776721584.png)

CONFIGURACIÓN SERVIDOR SSH.

El firewall bloquea las conexiones ssh del puerto 22.

![img](unknown-164347773436918.png)

Abro el puerto 22 del firewall en el servidor

![img](unknown-164347774811320.png)

La conexión funciona desde el cliente.

![img](unknown-164347775369222.png)

Habilito el puerto 22.

![img](unknown-16434776805946.png)

Deniego el acceso por root y lo compruebo.

![img](unknown-16434776901558.png)

![img](unknown-164347951084430.png)

Configuración del tiempo de espera por inactividad (180 segundos) y número máximo de intentos de autentificación (3 intentos)

![img](unknown-164347770169210.png)

Número máximo de conexiones abiertas sin autenticar (1 como máximo).

![image-20220129194615654](image-20220129194615654.png)

![img](unknown-164347982466732.png)

Guardo los cambios y reinicio el servidor con "sudo rcsshd restart"

![img](unknown-164347771804714.png)

Autenticación por clave pública.

Creo el directorio y el fichero que almacenará las claves públicas de los clientes. /.ssh/authorized_keys

![img](unknown-164347772661816.png)

Genero un par de claves en el cliente y copio la clave pública generada al servidor.

![img](unknown-164347776115324.png)

Introducimos la frase de paso y me conecto.

![img](unknown-164347776774226.png)

Revisamos el fichero authorized_keys y vemos las claves públicas de alumno y root (del cliente debian).

![img](unknown-164347777418928.png)

También deshabilito la autenticación por contraseña para obligar que se identifiquen por clave pública.

![image-20220129194346887](image-20220129194346887.png)

**Servicio de conexión SFTP**

Instalo el servidor SFTP.

![img](unknown-164348217370034.png)

Lo habilito para que inicie cuando encienda la máquina.

![img](unknown-164348221369236.png)

Compruebo la conexión.

![img](unknown-164348222956138.png)

Configuración del banner.

![image-20220129201934851](image-20220129201934851.png)

Previamente hay que crear el fichero de bienvenida. El banner funciona correctamente.

![image-20220129202236067](image-20220129202236067.png)