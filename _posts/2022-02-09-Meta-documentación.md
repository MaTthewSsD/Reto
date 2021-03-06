---
layout: post
title:  "Metadocumentación"
date:   2022-01-31 1:32:19 +0100
categories: jekyll update
---
# Meta-documentación

## Preparación de la MV donde hacemos los testeos en local

Preparamos una máquina Linux Pop-OS para hacer los testeos Jekyll en local.

![](https://github.com/MaTthewSsD/Fotos/blob/main/Screenshot_10.png?raw=true)

Ahora en esta máquina descargaremos los prerrequisitos necesarios para instalar Jekyll.

> Se pueden consultar en la página https://jekyllrb.com/docs/

`apt update`

![](https://github.com/MaTthewSsD/Fotos/blob/main/Screenshot_1.png?raw=true)

`apt-get install ruby-full`

![](https://github.com/MaTthewSsD/Fotos/blob/main/2.png?raw=true)

El resto de prerrequisitos ya los teníamos instalados por defecto en la máquina.

instalamos Jekyll

`gem install jekyll blunder`

![](https://github.com/MaTthewSsD/Fotos/blob/main/3.png?raw=true)

Ya tenemos Jekyll instalado en nuestra máquina.

Ahora para testear en local creamos una página estática genérica con el siguiente comando.

`jekyll new blog`

![](https://github.com/MaTthewSsD/Fotos/blob/main/4.png?raw=true)

Ahora lanzamos en local nuestra página estática.

`bundle exec jekyll serve`

![](https://github.com/MaTthewSsD/Fotos/blob/main/5.png?raw=true)

Ahora solo queda ver por local la página.

![](https://github.com/MaTthewSsD/Fotos/blob/main/6.png?raw=true)
## Trasladar página a Github Pages

Primero tenemos que crear un repositorio para guardar los ficheros.

![](https://github.com/MaTthewSsD/Fotos/blob/main/7.png?raw=true)

Una vez creado el repositorio copiamos los archivos generados por el comando `jekyll new blog` y los subo a el repositorio.

Ahora mostraremos un ejemplo del resultado:

![](https://github.com/MaTthewSsD/Fotos/blob/main/8.png?raw=true)

Ahora mostraremos un ejemplo de una página subida mediante este método.

![](https://github.com/MaTthewSsD/Fotos/blob/main/9.png?raw=true)
