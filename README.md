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
Si tenemos un puerto ssh configurado debemos permitir la entrada, pero limitarlo para evitar ataque de fuerza bruta.

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

# Para Windows y Linux

No todo es instalar, configurar cosas y dejarlas desantendidas sin importancia. Debemos ser conscientes de nuestros movimientos dentro del sistema, podemos tener el mejor antivirus y el sistema mas seguro del planeta, pero si tenemos malas practicas no servira de nada.

Para empezar el navegador es uno de los principales vectores de ataque, es muy importante tenerlo actualizado y configurado. Siempre voy a ser partidario del uso de Brave y Firefox, por un lado Brave es un navegador basado en chromium con un monton de protecciones por defecto, como un anti-huella digital para que los sitios no armen un perfil nuestro equipo, un bloqueador de rastreadores y anuncios. Firefox tiene la caracteristica de no estar basado en el motor de Google, cosa que los mas entusiastas valoran por encima de Brave, esto se debe a que la empresa Google buena parte de sus ingresos provienen de la publicidad y de los datos de los usuarios.

Una de las mejores herramientas para estar seguros en Firefox que no lleva bloqueador de anuncios como Brave, es usar uBlock Origin, es el mejor bloqueador del planeta, tiene opciones muy variadas de filtros y la posibilidad de agregar listas personalizadas de sitios que queramos bloquear.

A continuacion voy a dejar una captura de tierlist de como califico a los siguientes navegadores para uso diario, OJO con esto no quiero decir que navegador es bueno y cual es malo, solo veo las implicancias que tiene cada uno, como por ejemplo ritmo de actualizaciones, configuraciones por defecto y modelo de negocio.
