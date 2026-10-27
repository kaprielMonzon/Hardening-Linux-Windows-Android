# 🐧 Linux 

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

# 📱💻 Para todos los dispositivos

No todo es instalar, configurar cosas y dejarlas desantendidas sin importancia. Debemos ser conscientes de nuestros movimientos dentro del sistema, podemos tener el mejor antivirus y el sistema mas seguro del planeta, pero si tenemos malas practicas no servira de nada. Aca entran todos los dispositivos que usamos diariamente con, Android, iOS, MacOS, Windows y Linux.

# 🖥️ Navegadores

Para empezar el navegador es uno de los principales vectores de ataque, es muy importante tenerlo actualizado y configurado. Siempre voy a ser partidario del uso de Brave y Firefox, por un lado Brave es un navegador basado en chromium con un monton de protecciones por defecto, como un anti-huella digital para que los sitios no armen un perfil nuestro equipo, un bloqueador de rastreadores y anuncios, con un ritmo rapido de actualizaciones detras de su fork original, Chromium. Firefox tiene la caracteristica de no estar basado en el motor de Google, cosa que los mas entusiastas valoran por encima de Brave, esto se debe a que la empresa Google buena parte de sus ingresos provienen de la publicidad y de los datos de los usuarios.

Una de las mejores herramientas para estar seguros en Firefox que no lleva bloqueador de anuncios como Brave, es usar uBlock Origin, es el mejor bloqueador del planeta, tiene opciones muy variadas de filtros y la posibilidad de agregar listas personalizadas de sitios que queramos bloquear.

A continuacion voy a dejar una captura de tierlist de como califico a los siguientes navegadores para un uso diario, OJO con esto no quiero decir que navegador es bueno y cual es malo, solo veo las implicancias que tiene cada uno, como por ejemplo ritmo de actualizaciones, configuraciones por defecto y modelo de negocio. Aclaro que probe todos y cada uno de los navegadores que estan en esta tier

<p align="center">
  <img src="images/tier.png" alt="Tierlist de Navegadores" width="60%">
</p>

- 🟢 Firefox y Brave a mi parecer son los mas seguros, tienen muchos años de desarrollo, aunque Brave tiene varias funciones que nadie usa, como el sistema de recompensas, pero ya existe una alternativa limpia como Brave Origin. LibreWolf, es una excelente alternativa a Firefox, pueden haber algunos problemas con algunos sitios por la configuracion reforzada que tiene, pero muy usable para el dia a dia, eso si, al ser un Fork de Firefox tiene un pequeño retraso en el ritmo de actualizaciones pero es de 1 a 3 dias, no es fatal para el uso diario, a menos que hablemos de vulnerabilidades de dia 0, pero no ocurre solo con proyectos comunitarios, las Zero-Day afectan a las grandes corporaciones y cada vez con mas frecuencia gracias al avance de la IA.

- 🔵 Mullvad y Tor son los mas grandes proyectos de privacidad si hablamos de navegadores, tienen configuraciones por defecto muy agresivas contra rastreadores, anuncios, incluso contra JavaScript que es el principal culpable del robo de datos. Cada uno tiene su objetivo, para una busqueda normal sin dejar cookies ni sesiones abiertas, Mullvad es el mejor, tiene un boton que borra todo y crea una identidad, Tor es la entrada a las redes onion, donde se alojan sitios web que solo se pueden acceder mediante a este navegador, muy usado para busquedas en paises con mucha censura, aunque es bastante mas lento que los convencionales. El pero que tienen estos dos es por la comodidad, para una persona que le gusta tener todas las sesiones abiertas sin tener que poner credenciales de 0 es inviable y por las restricciones a nivel de configuracion que hacen a estos dos navegadores seguros, pueden romper sitios y hacernos resolver CAPTCHAS uno atras del otro, esto se hace para ver si no somos un bot, recomendados para hacer busquedas delicadas, no para el uso mucho mas frecuente a sitios del dia a dia. 

- 🟡 La precacion por aca va dividida, por un lado Chromium, Chrome y Edge, por su modelo de negocio, estos navegadores son recavadores de datos y sobre todo carecen de un buen bloqueador de rastreadores ni anuncios, Google lanzo el Manifest V3 que restringe de manera bruta el funcionamiento de los bloqueadores como uBlock Origin, teniendo que ceder a alternativas mucho menos potentes como uBlock Origin Lite que se adaptan a estas nuevas reglas impuestas. Por otro lado forks de Chromium con un equipo mas reducido, como Chromite y Helium que si bien son buenas alternativas a Brave, no tienen el mismo nivel de auditoria de seguridad que este ultimo, las actualizaciones suelen llegar varios dias despues y no siempre tienen el mismo apoyo que los grandes navegadores, no quiere decir que sean malas opciones, con estos a falta del Widevine no conviene usarlos para ver servicios de streaming como Spotify y Netflix. Como dato a favor de Helium este tiene uBlock Origin instalado por defecto, es de los pocos navegadores a parte de Brave basados en Chromium que permiten instalarlo.       

- 🔴 Aca navegadores como Internet Explorer, estan directamente tachados para usar a dia de hoy, ya se le conocen problemas de la epoca de Windows XP, daria para otro articulo nombrar los problemas de este navegador para un uso en estas epocas. El navegador de Samsung y Opera, estan muy por debajo de navegadores como Chrome y Edge en terminos de seguridad. A Opera se le conocen practicas sucias como sugerencias de enlaces de afiliados con objetivos publicitarios que el usuario no pidio y ni hablar del poco control del bloqueo de anuncios y rastreadores que este tiene. En cuanto al de Samsung es de codigo cerrado como varios de los navegadores con empresas por detras, no se sabe que hace y la cantidad excesiva de permisos que se le dan en el momento de uso. En este tier podria haber puesto a Helium y Cromite pero en este caso pongo a Ungoogled Chromium del que usa como base Helium, para mi es mucho menos practico que los dos anteriores, no es recomendable para hacer compras ni cosas delicadas en el ya que, como muchos proyectos que dependen de comunidades, van muy por detras de las ultimas actualizaciones de seguridad, pero mas alla de eso, no tiene actualizaciones automaticas en Windows, en Linux debemos usar repositorios externos de muy cuestionable origen, y como Helium y Cromite este Ungoogled Chromium, no tiene Widevine por lo que no podremos acceder a servicios de streaming.
