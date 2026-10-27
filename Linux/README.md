# 🐧 Linux 

En este apartado me enfocare en distribuciones basadas en Ubuntu o Debian, pero muchos o casi todos los paquetes que utilizare tienen sus versiones en sus respectivas distribuciones ya sean basadas en Arch, Fedora, etc.

Ya se conoce la seguridad que brinda Linux al ser flexible y configurable, pero las configuraciones por defecto no son suficientes, debemos hacer una serie de pasos para aprovechar realmente las ventajas que nos brindan las distribuciones de Linux.

<p align="center">
  <img src="images/tux.jpeg" width="50%">
</p>

# ⚠️ Atencion

Con esta guia no busco crear una maquina paranoica con configuraciones que puedan comprometer el uso diario, siempre hay que buscar el equilibrio en usabilidad y seguridad sin romper nada. 

# 🛡️ Actualizaciones 

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

# 🔥 Firewall

Lo siguiente es configurar un firewall, en este caso utilizaremos UFW, un frontend del firewall del nucleo de linux, nftables o, iptables en sistemas mas antiguos. Traduce cosas como bloquear una ip, que sin UFW, se nos complicaria ya que es tedioso de configurar por si solo, este lo hace de manera sencilla para que el kernel lo entienda.

Lo instalaremos con:

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

Si tenemos un puerto ssh configurado debemos permitir la entrada, pero limitarlo para evitar ataques de fuerza bruta.

```text
sudo ufw allow 22/tcp
```
```text
sudo ufw limit ssh
```

Para dejarlo activo para siempre

```text
sudo ufw enable
```


