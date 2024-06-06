[Duck DNS]: https://www.duckdns.org/

[wg-easy]: https://github.com/wg-easy/wg-easy
[Common Use Cases]: https://github.com/wg-easy/wg-easy#Common-Use-Cases
[wg-easy/docker-compose.yml]: https://github.com/wg-easy/wg-easy/wiki/Using-WireGuard-Easy-with-Pi-Hole

[docker-compose.yml]: docker-compose.yml

[Pihole]: http://ip_raspberry:5353/admin
[WireGuard]: http://ip_raspberry:51821

[Repositorio Duck DNS]: https://github.com/miguel-shadow/docker-duckdns


**Contenidos**
- [1. Pihole y WireGuard](#1-pihole-y-wireguard)
- [2. DNS dinámico](#2-dns-dinámico)
- [3. Instalación](#3-instalación)
- [4. Ejecutar](#4-ejecutar)
- [5. Portales WEB](#5-portales-web)
    - [5.1. Pi-hole](#51-pi-hole)
    - [5.2. WireGuard](#52-wireguard)
- [6. Actualizar DNS Dinámico automáticamente](#6-actualizar-dns-dinámico-automáticamente)


# 1. Pihole y WireGuard
- Permite crear una **VPN WireGuard** y enlazarla con **Pihole** mediante **Docker** en una **Raspberry Pi**


# 2. DNS dinámico
- Mediante [Duck DNS], crear un **dominio** para nuestra IP dinámica


# 3. Instalación
> [!NOTE]
> Esta guía está basada en la **documentación** en Github de [wg-easy]: En la parte inferior, sección [Common Use Cases] aparece cómo enlazar WireGuard con Pihole mediante un `docker-compose.yml` ([wg-easy/docker-compose.yml])

- Modificar las variables (señaladas con `<>`) en el archivo [docker-compose.yml]
    - `<dominio_dns_dinamico>`: Nombre del dominio DNS Dinámico (**\*Creado en Duck DNS anteriormente**)
    - `<password_wg>`: Contraseña del portal WEB de WireGuard
    - `<password_ph>`: Contraseña del portal WEB de Pihole


# 4. Ejecutar
- `docker compose up -d --build`


# 5. Portales WEB
## 5.1. Pi-hole
- **Acceder** mediante un **navegador**: `http://<ip_raspberry>:5353/admin` ([Pihole])


## 5.2. WireGuard
- **Acceder** mediante un **navegador**: `http://<ip_raspberry>:51821` ([WireGuard])


# 6. Actualizar DNS Dinámico automáticamente
Al disponer de una **IP dinámica**, la IP puede cambiar y estropear todo lo anterior, dejando de funcionar la VPN.

En este repositorio explico cómo **actualizar el DNS Dinámico de manera automática**: [Repositorio Duck DNS]
