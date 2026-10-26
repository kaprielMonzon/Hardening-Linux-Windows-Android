# Linux 

Distribuciones basadas en Ubuntu o Debian

Primero debemos tener actualizado nuestro sistema ya sea en apt o flatpak, con el siguiente comando:

```text
sudo apt update -y && sudo apt upgrade -y && flatpak update -y
```

Para asegurarnos de tener un sistema limpio eliminamos paquetes huerfanos

```text
sudo apt --purge autoremove
```

Si queremos que las actualizaciones de seguridad sean automaticas instalamos este paquete:

```text
sudo apt install unattended-upgrades
```

Lo siguiente es configurar un firewall:

```text
sudo apt install ufw
```

Con UFW podemos bloquear todo el tráfico que intenta entrar a la maquina desde afuera.

```text
sudo ufw default deny incoming
```

Con esta otra regla permitimos conectarnos a internet.

```text
sudo ufw default allow outgoing
```
Para dejarlo activo para siempre

```text
sudo ufw enable
```

No todo es instalar, configurar cosas y dejarlas desantendidas sin importancia. Debemos ser conscientes de nuestros movimientos dentro del sistema, podemos tener el mejor antivirus y el sistema mas seguro del planeta, pero si tenemos malas practicas no servira de nada.

Para empezar el navegador que tengamos es muy importante 
