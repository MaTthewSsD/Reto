---
layout: post
title:  "Reglas de FireWall y NAT"
date:   2022-01-20 11:32:19 +0100
categories: jekyll update
---
###### Reto Game of Networks

## Reglas de FireWall y NAT

#### 1. Empezando con FireWall Rules:

Reglas de Firewall de la WAN hacia la DMZ

![image-20220224111546890](https://github.com/MaTthewSsD/Reto/blob/gh-pages/_posts/Firewall%20y%20NAT//image-20220224111546890.png?raw=true)

Reglas de Firewall de la DMZ, en este caso permitimos todo el tráfico para que podamos realizar las pruebas del dmz:

![image-20220224111609028](https://github.com/MaTthewSsD/Reto/blob/gh-pages/_posts/Firewall%20y%20NAT/image-20220224111609028.png?raw=true)

Reglas de Firewall de la RedInterna:

![image-20220224111627929](https://github.com/MaTthewSsD/Reto/blob/gh-pages/_posts/Firewall%20y%20NAT/image-20220224111627929.png?raw=true)

Y dentro de la OpenVpn permitimos el tráfico total:

![image-20220224013938195](https://github.com/MaTthewSsD/Reto/blob/gh-pages/_posts/Firewall%20y%20NAT/image-20220224013938195.png?raw=true)

Reglas de Nateo para la OpenVPN:

![image-20220224014055514](https://github.com/MaTthewSsD/Reto/blob/gh-pages/_posts/Firewall%20y%20NAT/image-20220224014055514.png?raw=true)

