# Bloque 1 — Orientación en el sistema y la terminal

## 1.1 — Filesystem Hierarchy Standard (FHS)

### Concepto

El sistema no está dividido por unidades como en Windows, todo cuelga del mismo árbol "/", desde el cual se montan los discos, particiones, etc. A partir de ahí, hay distintos directorios para cada función.

### Tabla de directorios de primer nivel
| Directorio        | Para qué sirve                                                                          |
|-------------------|-----------------------------------------------------------------------------------------|
| /etc              | Ficheros de configuración del sistema                                                   |
| /var              | Datos variables, como colas de correo, caché... que crece con el uso                    |
| /home             | Directorios personales de los usuarios                                                  |
| /root             | Directorio personal de root                                                             |
| /usr              | Programas y datos de usuarios instalados: binarios (/usr/bin), librerías, documentación |
| /bin, /sbin, /lib | Enlaces simbólicos dentro de /usr, binarios esenciales                                  |
| /tmp              | Ficheros temporales                                                                     |
| /boot             | El kernel y ficheros de arranque                                                        |
| /dev              | Discos representados como ficheros, ej: /dev/sda                                        |
| /proc, /sys       | Pseudo-sistemas de ficheros sobre el kernel y hardware del sistema                      |
| /opt, /srv, /mnt  | Software opcional, datos de servicios, puntos de montaje. También /media                |

### Comandos practicados
| Comando                     | Para qué sirve                                                                          |
|-----------------------------|-----------------------------------------------------------------------------------------|
| ls /                        | Muestra el directorio / con  sus carpetas como /bin, /home, etc.                        |
| ls -la /etc | head -30      | Lista 30 archivos de la carpeta /etc con                                                |
| cat /etc/os-release         | Lee el archivo que muestra la información del sistema                                   |
| ls /var/log                 | Lista los logs del sistemas (carpeta de logs)                                           |
| df -h                       | Muestra el espacio en disco                                                             |
| lsblk                       | Muestra las particiones de /dev/sda                                                     |
| cat /proc/cpuinfo           | Muestra la CPU asignada                                                                 |
| cat /proc/meminfo           | Muestra el uso de la memoria en el sistema                                              |

### Errores / cosas que me confundieron

### Dudas abiertas