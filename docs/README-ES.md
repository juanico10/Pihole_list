<h1 align="center"> El proyecto que protege tus dispositivos </h1>

The <strong>Pi-hole_list</strong> es una iniciativa que pretende bloquear y asegurar toda la red a través de su propio hardware. En este repositorio, se instala a través de Docker®. Pi-hole® y Adguard Home® son sumideros DNS que protegen tus dispositivos de contenidos no deseados sin necesidad de instalar ningún software en los dispositivos cliente.

<div align="center">
    <a href="https://github.com/JuanRodenas/Pihole_list">
        <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/pihole.png" alt="Pi-hole" width="280">
        <img src="https://cdn.adtidy.org/website/github.com/AdguardFilters/viking.svg" alt="AdGuard Home" width="420">
    </a>
    <br>
    <h3>Bloqueo de anuncios en toda la red a través de su propio hardware.</h3>
</div>

![GitHub last commit (by committer)](https://img.shields.io/github/last-commit/JuanRodenas/Pi-hole_list?style=flat&logo=Github&logoColor=white&label=last-commit&labelColor=253B80&color=253B80)

## Enlaces al instalador o al desarrollador
| PROYECTO | ENLACE INSTALADOR | ENLACE DESARROLLADOR |
| :-- | :--: | :--: |
| <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/AdGuard_Logo.png" alt="AdGuard Home" width="26"/> Adguard Home® | [INSTALLATION](https://github.com/JuanRodenas/AdGuardHome) | [DEVELOPER](https://adguard.com/es/adguard-home/overview.html) |
| <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/pihole.png" alt="Pi-Hole" width="30"/> Pi-hole® | [INSTALLATION](https://github.com/JuanRodenas/Pihole) | [DEVELOPER](https://pi-hole.net/) |
### Versión docker latest Pi-hole®
![Docker Image Version (tag latest)](https://img.shields.io/docker/v/pihole/pihole/latest?style=flat&logo=docker&logoColor=white&labelColor=0088cc&color=0088cc)

### Versión docker latest Adguard Home®
![Docker Image Version (tag latest)](https://img.shields.io/docker/v/adguard/adguardhome/latest?style=flat&logo=docker&logoColor=white&labelColor=0088cc&color=0088cc)

## Detalles

Estas listas fueron creadas porque quería tener un poco más de control sobre lo que se bloquea. Muchas listas son de todo o nada. Nos propusimos crear listas con más control sobre lo que se bloquea, por eso te recomiendo mis listas, ya que están probadas y bloqueamos solo lo que es innecesario.

### Versiones:

<details>
<summary>Versión original:</summary>

<Original>&nbsp;Todas las URL en esta versión **están** precedidas por una dirección IP en el archivo txt o de hosts:</Original>

<p>&nbsp;&nbsp;<code>0.0.0.0 ejemplo.com</code> – redirige el dominio ejemplo.com a la dirección 0.0.0.0 (pero no para sus subdominios).</p>
<p>&nbsp;&nbsp;<code>127.0.0.1 ejemplo.com</code> – devolverá la dirección 127.0.0.1 para el dominio ejemplo.com (pero no para sus subdominios).</p>

</details>
&nbsp;
<details>
<summary>Versión sin IP a la izquierda:</summary>

<Original>&nbsp;Todas las URL en esta versión **no** están precedidas por una dirección IP en el archivo txt o de hosts:</Original>

<p>&nbsp;&nbsp;<code>ejemplo.com</code></p>

<sup>Nuestros usuarios nos han informado que algunos dispositivos dan un error si la URL está precedida por una dirección IP.</sup>
</details>
&nbsp;
<details>
<summary>Versión de AdGuard:</summary>

<p>&nbsp;Todas las URL de esta versión de la lista de **AdGuard** aparecen en el archivo hosts de la siguiente manera:</p>

<p>&nbsp;&nbsp;<code>||ejemplo.org^</code> – bloquea el acceso al dominio <code>ejemplo.org</code> y todos sus subdominios</p>
<p>&nbsp;&nbsp;<code>@@||ejemplo.org^</code> – desbloquea el acceso al dominio <code>ejemplo.org</code> y todos sus subdominios.</p>
<p>&nbsp;&nbsp;<code>/REGEX/</code> – bloquea el acceso a los dominios que coinciden con la expresión regular especificada. Por ejemplo, la regla <code>/ejemplo.*/</code> bloqueará los hosts que coincidan con el <code>ejemplo.*</code></p>
<p>&nbsp;&nbsp;<code>$</code> – Este es el delimitador, que indica que el resto de la regla es un modificador. Los modificadores deben colocarse al final de la regla después del carácter y separados por comas. Por ejemplo, los modificadores deben colocarse al final de la regla después del carácter y separados por comas. <code>||ejemplo.org^$importante</code>.</p>
<p>&nbsp;&nbsp;<code>$importante</code> – El modificador aplicado a una regla aumenta su prioridad sobre cualquier otra regla sin el modificador. Incluso por encima de las reglas de excepción básicas.</p>
<p>&nbsp;&nbsp;<code>*</code> – el carácter comodín. Se utiliza para representar cualquier conjunto de caracteres. También puede ser una cadena vacía o una cadena de cualquier longitud.</p>
<p>&nbsp;&nbsp;<code>^</code> – el carácter separador. A diferencia del bloqueo de anuncios del navegador, no hay nada que separar en un nombre de host, por lo que el único propósito de este carácter es marcar el final del nombre de host.</p>
<p>&nbsp;&nbsp;<code>|</code> – un indicador del principio o final del nombre de host. El valor depende de la ubicación del carácter en la máscara. Por ejemplo, la regla <code>ejemplo|^</code> corresponde a <code>ejemplo.org</code>, pero no a <code>ejemplo.org.com</code>. <code>|ejemplo</code> corresponde a <code>ejemplo.org</code> pero no a <code>test.ejemplo.org</code></p>
    
<sup>Las instrucciones son actuales a partir de [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome/wiki/Hosts-Blocklists#special-characters) v0.107.41. AdGuard admite versiones más antiguas.</sup>
<sup>Las instrucciones que admite [AdGuard Home](https://kb.adguard.com/en/general/how-to-create-your-own-ad-filters).</sup>
</details>
&nbsp;
<details>
<summary>Comentarios sobre las listas:</summary>

<p>&nbsp;Todas las urls de esta versión de la lista aparecen en el archivo hosts de la siguiente forma</p>

<p>&nbsp;&nbsp;<code># comentario</code> – sólo un comentario</p>
<p>&nbsp;&nbsp;<code>! comentario</code> – sólo un comentario</p>

</details>
&nbsp;

### Uso:
<details>
    <summary>Utilizar con Pi-Hole <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/pihole.png" alt="Pi-Hole" width="30"/>:</summary>

## Instrucciones para usar con Pi-Hole:

1. Copia el enlace al formato de Pi-hole de la lista deseada (de la tabla correspondiente a continuación).
2. Agrega la URL a las listas de bloqueo de tu Pi-hole (**Inicio de sesión** > **Administración de grupos** > **Listas** > **Pega la URL de la lista en el campo "Dirección", agrega un comentario** > **Haz clic en "Agregar"**).
3. Actualiza Gravity (**Herramientas** > **Actualizar Gravity** > **Haz clic en "Actualizar"**).

&nbsp;
<sup>Instrucciones actuales a partir de Pi-hole 5.2.4. Las instrucciones pueden ser ligeramente diferentes en la actualidad. Las instrucciones se actualizarán cuando se publique la versión 6.</sup>
</details>
&nbsp;

<details>
    <summary>Utilizar con AdGuard Home <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/AdGuard_Logo.png" alt="AdGuard Home" width="22"/>:</summary>

## Instrucciones de uso con AdGuard Home:

1. Copie el enlace al formato de AdGuard correspondiente a la lista deseada (de la tabla correspondiente a continuación).
2. Añada la URL a su lista de bloqueo de AdGuard (**Inicio de sesión** > **Filtros** > **Listas de bloqueo DNS** > **Añadir lista de bloqueo** > **Añadir una lista personalizada** > **Introduzca el nombre** > **Pegue la URL del enlace copiado**).
3. La lista se activa automáticamente y está lista para empezar a bloquear.

&nbsp;
<sup>Instrucciones actualizadas a partir de AdGuard Home v0.107.41</sup>
</details>
&nbsp;

# Adguard Home®  <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/adguard_home_lightmode.svg" alt="AdGuard Home" width="100"/>

## Configuración general
- Una de las recomendaciones, en los ajustes de AdGuard, Configuración general, Intervalo de actualización de filtros en 1 hora. Actualizará las reglas cada hora.

### Cambiar contraseña en Adguard
Para cambiar la contraseña en Adguard podemos acceder a estas webs y crear un usuario y contraseña:

- [![web2generators](https://img.shields.io/badge/-web2generators-c4302b?style=flat&labelColor=c4302b)](https://www.web2generators.com/apache-tools/htpasswd-generator)
- [![ipvoid](https://img.shields.io/badge/-ipvoid-c4302b?style=flat&labelColor=c4302b)](https://www.ipvoid.com/htpasswd-generator/)
- [![wtools](https://img.shields.io/badge/-wtools-c4302b?style=flat&labelColor=c4302b)](https://wtools.io/generate-htpasswd-online)

<p>Creamos el usuario y la contraseña. Una vez creado, tiene este formato:</p>
<p><code>user:$apr1$x4gcjzrl$qSvcJK46C2rQUGRl4z1kl0</code></p>

<p>Una vez creado el usuario y la contraseña, procedemos a acceder al fichero de configuración de adguard, <code>AdGuardHome.yaml</code>.</p>
<p>Buscamos la siguiente línea en el fichero de configuración y sustituimos los datos creados.</p>
<ul>
<li>Para el <code>user</code>: user</li>
<li>Para el <code>password</code>: $qSvcJK46C2rQUGRl4z1kl0</li>
</ul>
<pre><code class="lang-yaml">users:
  - name: <span class="hljs-literal">user</span>
    password: <span class="hljs-variable">$apr1</span><span class="hljs-variable">$x4gcjzrl</span><span class="hljs-variable">$qSvcJK46C2rQUGRl4z1kl0</span>
</code></pre>

Una vez modificados los datos, reinicie adguard.

### Configuración para tener activado DNS sobre TLS o DNS sobre HTTPS
En la configuración de AdGuard, Configuración DNS:
- Upstream DNS servers, copie una de estas URLs:

For Cloudfare DoH-DoT:
```shell
https://dns.cloudflare.com/dns-query
tls://1dot1dot1dot1.cloudflare-dns.com
```
For DoH-DoT de Quad9:
```shell
https://dns.quad9.net/dns-query
tls://dns.quad9.net
```

y marque la opción "**Balanceo de carga**", por defecto esta opción está marcada.

- Arrancar servidores DNS, ponemos los DNS de nuestra elección:

Cloudflared tanto en IPv4 como en IPv6:
```shell
1.1.1.1
1.0.0.1
2606:4700:4700::1111
2606:4700:4700::1001
```
Quad9 in both IPv4 and IPv6:
```shell
9.9.9.9
149.112.112.112
2620:fe::fe
2620:fe::fe:9
```

- Configuración del servidor DNS, marque la opción "**Habilitar DNSSEC**".

## Añadir dominio para DoH y DoT:

### Crear el certificado con Let's Encrypt
<details>
    <summary>Create the self-signed personal certificate with Let's Encrypt:</summary>

#### Crear el certificado personal autofirmado con Let's Encrypt:
Instalar un certificado SSL gratuito con CertBot:

:one: We update the list of packages.
~~~shell
sudo apt update && sudo apt upgrade
~~~

:two: Instalar el paquete Certbot
~~~shell
sudo apt install certbot
~~~

:three: In this section we are going to see the most important options of the command. You can choose the options that you consider most convenient.

 :point_right: 3.1 You can add as many domains as you wish with the `--domain` variable. Example:
  | Description | example |
  | :-- | :-- |
  | --domain | --domain example.com --domain example.org |
  | --domain | --domain example.org,www.example.org |
  | -d | -d example.com -d example.org |
  | -d | -d example.org,www.example.org |

 :point_right: 3.2 You can change the variable `--rsa-key-size` to the size:
  | Bit size | Description |
  | :--: | :-- |
  | 512 | Insecure |
  | 1024 | Basic security |
  | 2048 | Recommended security |
  | 4096 | Increased security |
  | 8192 | Maximum security |

 :point_right: 3.3. `--csr` La variable csr y un archivo `.cnf` pueden realizar las siguientes funciones. Actualmente --csr sólo funciona con el subcomando `certonly`.
  - Siga este tutorial que he añadido por separado para crear el csr [![Link](https://img.shields.io/badge/Create_CSR-green.svg?style=flat)](./assets/create-csr.md)

 :point_right: 3.4. `--config-dir` Se puede configurar el fichero de configuración con la variable.
  - Las opciones de configuración específicas del certificado deben establecerse en el `.conf` y adjunto un ejemplo: [![example.org.conf](https://img.shields.io/badge/example.org.conf-3849b8?style=flat&labelColor=3849b8)](./assets/example.org.conf)

 :point_right: 3.5. `--test-cert, --staging` Utilizar el servidor de preparación de Let's Encrypt para obtener o revocar certificados de prueba (no válidos); equivalente a `--server acme-staging`

 :point_right: 3.6. `--hsts` Añada la cabecera Strict-Transport-Security a cada respuesta HTTP. Obliga al navegador a utilizar siempre SSL para el dominio.

 :point_right: 3.7. `--key-type {rsa,ecdsa}`. Tipo de clave privada generada. Solo se puede proporcionar *UNA* por invocación en este momento.

 :point_right: 3.8. `--quiet` Silencia todas las salidas excepto los errores.

 :point_right: 3.9. `--cert-name` Nombre del certificado a aplicar. Este nombre es utilizado por Certbot para el mantenimiento y en las rutas de archivo; no afecta al contenido del certificado en sí.

 :point_right: 3.10 `--debug` Mostrar seguimiento en caso de error

 :point_right: 3.11. `--server` Elija el URI de recursos de directorio ACME para su servidor.
  | Description | Server |
  | :--: | :-- |
  | Certificado para el servidor de producción | https://acme-v02.api.letsencrypt.org/directory |
  | Certificado para el servidor de ensayo | https://acme-staging-v02.api.letsencrypt.org/directory |

 :point_right: 3.12. `--elliptic-curve` (default: secp256r1) The SECG elliptic curve name to use.
  | Type algorithm | Bit size | Description |
  | :-- | :--: | :-- |
  | secp192r1 | 192 | Insecure |
  | secp224k1 | 224 | Basic security |
  | secp224r1 | 224 | Basic security |
  | secp256k1 | 256 | Recommended security |
  | secp256r1 | 256 | Recommended security |
  | secp283k1 | 283 | Basic security |
  | secp283r1 | 283 | Basic security |
  | secp384r1 | 384 | Recommended security |
  | secp409r1 | 409 | Maximum security |
  | secp409k1 | 409 | Maximum security |
  | secp521r1 | 521 | Maximum security |
  | secp571r1 | 571 | Maximum security |
  | secp571k1 | 571 | Maximum security |
  
 Para la elección de la clave a elegir, la diferencia en la definición del punto base tiene dos consecuencias importantes:
  * **La curva secpXXXk1 tiene una mayor eficiencia computacional que la curva secpXXXr1.** Esto se debe a que el punto base de la curva secpXXXk1 es un punto de generación, lo que significa que puede utilizarse para generar todos los demás puntos de la curva. En cambio, el punto base de la curva secpXXXr1 no es un punto de generación, por lo que es necesario calcular más operaciones para generar todos los demás puntos de la curva.
  * **La curva secpXXXr1 tiene mayor seguridad que la curva secpXXXk1.** Esto se debe a que el punto base de la curva secpXXXr1 es un punto más aleatorio que el punto base de la curva secpXXXk1. Esto hace que sea más difícil para los atacantes encontrar puntos de la curva que no estén en el conjunto de puntos de generación.
 En general, la curva secpXXXXk1 es una buena elección para aplicaciones que requieren eficiencia computacional, mientras que la curva secpXXXr1 es una buena elección para aplicaciones que requieren seguridad.

 Ejemplos de aplicaciones que podrían utilizar cada curva:
  | Característica | secpXXXk1 | secpXXXr1 |
  |---|---|---|
  | Punto base: Más bajo, más alto.
  | Tipo Computacional Seguridad
  | Eficiencia computacional Superior Básico
  | Seguridad | Básica | Superior |
  | Usos comunes | Firma digital, Criptodivisas, cifrado de claves públicas | Cifrado de claves públicas para aplicaciones críticas, cifrado, Infraestructura de Clave Pública (PKI) |

Ejecute el siguiente comando modificando el correo electrónico válido y las opciones que considere oportunas para su ejemplo.

Este ejemplo es para adquirir un certificado Wildcard:
```shell
certbot certonly --manual --preferred-challenges=dns --rsa-key-size 4096 --email usuario@ejemplo.com --agree-tos
--server https://acme-v02.api.letsencrypt.org/directory -d "*.your_domain"
```

:four: Por último, nos pedirá que hagamos un registro <code>_acme-challenge</code> TXT en nuestro proveedor de servidor de nombres con el contenido que nos indique:
Con cerbot, al utilizar el desafío dns, certbot nos pedirá que coloquemos un registro `TXT DNS` con un contenido específico bajo el nombre de dominio consistente en el nombre de host para el que queremos que se emita un certificado, anteponiendo `_acme-challenge`.
Por ejemplo, para el dominio `ejemplo.com`, una entrada en el archivo de zona tendría el siguiente aspecto:
```shell
_acme-challenge.example.com. 300 IN TXT "gfj9Xq...Rg85nM"
```

Crea los siguientes archivos, en el directorio <code>/etc/letsencrypt/live/</code>:
 - <code>fullchain.pem</code> – su certificado SSL cifrado en PEM.
 - <code>privkey.pem</code> – tu clave privada encriptada en PEM.

#### Configuración de Lets encrypt
To check if the certificate will self-renew:
* Prueba de renovación (simulación):<code>certbot renew --dry-run</code>
* Compruebe el estado del servicio de temporizador de Certbot: <code>systemctl status certbot.timer</code>
* Para renovar un certificado: <code>certbot renew</code>
	* Para forzar la autorrenovación: <code>--force-renewal</code>
* Para listar trabajos: <code>systemctl list-timers --all</code> Debe aparecer el siguiente configurado para la renovación automática: <code>certbot.timer - certbot.service</code>
* Certificados de cotización: <code>certbot certificates</code>

Para revocar un certificado:
* Eliminar un certificado por completo: <code>certbot delete --cert-name example.com --reason keycompromise</code>
* De la cuenta para la que se emitió el certificado: <code>certbot revoke --cert-path /etc/letsencrypt/archive/${YOUR_DOMAIN}/cert1.pem --reason keycompromise</code>
* Utilizando la clave privada del certificado: <code>certbot revoke --cert-path /PATH/TO/cert.pem --key-path /PATH/TO/key.pem --reason keycompromise</code>

<p>Si no desea seguir todos estos pasos, puede obtener el certificado con <code>ZeroSSL</code>, pero se carga el certificado comodín.</p>
<p><a href="https://zerossl.com/"><img src="https://img.shields.io/badge/-ZeroSSL-3849b8?style=flat&labelColor=3849b8" alt="ZeroSSL"></a></p>

</details>

### Create the self-signed personal certificate with OPENSSL:
<details>
    <summary>Crear el certificado personal autofirmado:</summary>

#### Crear el certificado personal autofirmado:
<p>Pasos que puedes seguir para crear un certificado RSA autofirmado usando OpenSSL con SHA-512 y Subject Alternative Names (SAN).</p> <p>
<p>Para saber más sobre comandos openssl útiles para certificados:</p>
<p><a href="https://www.busindre.com/comandos_openssl_utiles_para_certificados"><img src="https://img.shields.io/badge/-Link-df8a47?style=flat&labelColor=df8a47" alt="Link"></a></p>

1. Actualizamos la lista de paquetes.
~~~shell
sudo apt update && sudo apt upgrade
~~~
2. Asegúrese de que tiene OpenSSL instalado en su sistema antes de continuar. Instale el paquete openssl:
~~~shell
sudo apt install openssl
~~~
3. Cree el directorio donde queremos almacenar los certificados:
~~~shell
mkdir certs &&\
cd certs/
~~~
4. Cree el certificado con el siguiente comando, cambiando la ruta del certificado o deje el nombre de la `.key` y el `.crt` para almacenarlo en el directorio:

	4.1 Generar una clave privada RSA:
	~~~shell
	openssl genpkey -algorithm RSA -out privkey.key -pkeyopt rsa_keygen_bits:2048
	~~~
	4.2 A continuación, crearemos una solicitud de certificado (CSR) que contendrá la información del certificado:
	~~~shell
	vi csrconfig.cnf
	~~~
	~~~shell
	[req]
	distinguished_name = req_distinguished_name
	req_extensions = v3_req

	[req_distinguished_name]
	commonName = your website domain name
	organizationName = Your Company Name
	countryName = ES

	[v3_req]
	subjectAltName = @alt_names

	[alt_names]
	DNS.1 = example.com
	DNS.2 = www.example.com
	~~~
	4.3 Generamos el certificado autofirmado con los datos de la CSR:
	~~~
	openssl req -new -key privkey.key -out chain.csr -sha512 -config csrconfig.cnf
	~~~
	4.4 Crear certificado autofirmado en formato PEM:
	~~~
	openssl x509 -req -in chain.csr -signkey privkey.key -out fullchain.pem -sha512 -days 365 -extfile csrconfig.cnf -extensions v3_req
	~~~
	4.5 Después de crear el certificado autofirmado, podemos verificar el contenido del certificado si se ha creado correctamente:
	~~~shell
	openssl x509 -in fullchain.pem -text -noout
	~~~
</details>


### Configurar certificado en AdGuard Home:
1. Abre la interfaz web de AdGuard Home y ve a configuración.
2. Desplázate hacia abajo en el menú hasta `Configuración de encriptación`.
3. Habilita la casilla `Habilitar encriptación` (HTTPS, DNS a través de HTTPS y DNS a través de TLS).
4. Habilita `Redireccionar automáticamente a HTTPS`.
5. Ingresa tu nombre de dominio en `Nombre del servidor`. Si estás ingresando un comodín, introduce solo el nombre de dominio `ejemplo.com`.
6. Copia/pega el contenido del archivo `fullchain.pem` en `Certificados`.
7. Copia/pega el contenido del archivo `privkey.pem` en `Clave privada`.
8. Haz clic en `Guardar configuración`.

### Configurar el dominio para permitir clientes privados de DNS DoH y DoT:
Para crear una zona en tu dominio y habilitar clientes, sigue estos pasos:

1. Principalmente, en la sección de encriptación de AdGuard, debes habilitar el dominio `ejemplo.org`.
2. Tienes el certificado comodín `*.example.org` creado.

#### Instrucciones de uso:

1. Inicia sesión en el panel de control de tu proveedor de alojamiento web o registrador de dominios donde compraste el nombre de dominio.
2. Busca la opción `Zonas DNS`.
3. Crea una nueva entrada de `Zonas DNS`. Para agregar la entrada para cada cliente, por ejemplo, `one.example.org`. Esto permitirá que el cliente creado en el panel de `Configuración de clientes` se conecte.
4. Configura `Configuración/Configuración del cliente/Clientes persistentes`. Haz clic en `Agregar clientes` y bajo `Identificador`, crea un nombre.

<sup>Instrucciones actuales en la documentación del desarrollador <a href="https://github.com/AdguardTeam/AdGuardHome/wiki/Clients#clientid">documentación</a>.</sup>


# Lista para Pihole <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/pihole.png" alt="Pi-Hole" width="40"/> y AdGuard Inicio <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/AdGuard_Logo.png" alt="AdGuard Home" width="32"/>

## Principal lista segura

| Lista | Link | Descripción |
| :-- | :--: | :-- |
| safelist repository | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/Listas/whitelist.txt) | safelist JuanRodenas |
| safelist hagezi | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/hagezi/dns-blocklists/main/whitelist.txt) | safelist hagezi (No comprobada) |


## Principal lista bloqueo
<sup>Columna Link: Pi-hole® | Adguard Home®.</sup>

#### Host
| Lista | Link | Descripción |
| :-- | :--: | :-- |
| List oisd | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://dbl.oisd.nl) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://abp.oisd.nl) | To Block host Adguard and domains [dbl.oisd](https://oisd.nl/) |
| The big list | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://big.oisd.nl/domains) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://big.oisd.nl/) | The big list [oisd](https://oisd.nl/) |
| urlhaus-filter-domains | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://malware-filter.gitlab.io/malware-filter/urlhaus-filter-domains.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://malware-filter.gitlab.io/malware-filter/urlhaus-filter-agh.txt) | urlhaus-filter DEV [Link](https://gitlab.com/malware-filter/urlhaus-filter) |
| everything | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://blocklistproject.github.io/Lists/everything.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/everything-ags.txt) | To Block everything |
| energized pro | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://energized.pro/unified/formats/hosts.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://block.energized.pro/ultimate/formats/hosts.txt) | To Block [energized](https://energized.pro/) |
| d3ward | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/d3ward/toolz/master/src/d3host.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/d3ward/toolz/master/src/d3host.adblock) | [d3ward](https://github.com/d3ward) popular list |


#### Malware / Shock / Porn / Adult 
| Lista | Link | Descripción |
| :-- | :--: | :-- |
| The NSFW list | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://nsfw.oisd.nl/domains) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://nsfw.oisd.nl/) | The NSFW list [oisd](https://oisd.nl/) |
| Gambling-porn | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/Gambling.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://github.com/blocklistproject/Lists/blob/master/adguard/gambling-ags.txt) | To Block Gambling and porn |
| Malware | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://blocklistproject.github.io/Lists/malware.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/malware-ags.txt) | To Block malware |
| Ransomware | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/blocklistproject/Lists/master/ransomware.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/ransomware-ags.txt) | To Block ransomware |
| phishing | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://phishing.army/download/phishing_army_blocklist_extended.txt) | To Block phishing |


#### Tracking/Ads
| Lista Tracking/Ads | Link | Descripción |
| :-- | :--: | :-- |
| SmartTV | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/Perflyst/PiHoleBlocklist/master/SmartTV.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/smart-tv-ags.txt) | To Block SmartTV |
| WindowsSpyBlocker | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/crazy-max/WindowsSpyBlocker/master/data/hosts/spy.txt) | To Block WindowsSpyBlocker |
| GoodbyeAds-Ultra | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Hosts/GoodbyeAds-Ultra.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/hagezi/dns-blocklists/main/adblock/pro.plus.txt) | To Block [hagezi](https://github.com/hagezi/dns-blocklists) and [jerryn70](https://github.com/jerryn70/GoodbyeAds) |
| ads-and-tracking-extended | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://www.github.developerdan.com/hosts/lists/ads-and-tracking-extended.txt) | To Block ads-and-tracking-extended |
| Adblock_Plus | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/notracking/hosts-blocklists/master/adblock/adblock.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/Adblock_Plus_Ads.txt) | To Block Tracking AdBlock |
| Android tracking | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://github.com/JuanRodenas/Pihole_list/blob/main/Listas/android-tracking.txt) | Android tracking for AdGuard Home |
| Disconnect.me | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://s3.amazonaws.com/lists.disconnect.me/simple_tracking.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://s3.amazonaws.com/lists.disconnect.me/simple_ad.txt) | To Block disconnect.me |

#### Adguard team filters
| Lista Tracking/Ads | Link | Descripción |
| :-- | :--: | :-- |
| AdGuardSDNSFilter | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://adguardteam.github.io/AdGuardSDNSFilter/Filters/filter.txt) | AdGuard team DNS filter |
| AdAway | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://adaway.org/hosts.txt) | AdAway default blocklist |
| Game Console Adblock List | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/DandelionSprout/adfilt/master/GameConsoleAdblockList.txt) | Game Console Adblock List |
| SmartTV-AGH | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/Perflyst/PiHoleBlocklist/master/SmartTV-AGH.txt) | Smart-TV Blocklist for AdGuard Home |
| Peter Lowe's List | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://pgl.yoyo.org/adservers/serverlist.php?hostformat=adblockplus&showintro=1&mimetype=plaintext) | Blocklist for use with Adblock Plus |

#### Servicios
| Lista Servicios | Link | Descripción |
| :-- | :--: | :-- |
| Youtube | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/blocklistproject/Lists/master/youtube.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/youtube-ags.txt) | To Block youtube |
| Facebook | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://github.com/jmdugan/blocklists/blob/master/corporations/facebook/all) | To Block Facebook/Instagram/Whatsapp |
| Whatsapp open | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/facebook/all-but-whatsapp) | To Block Facebook/Instagram but leave Whatsapp open |
| Google | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/google/all) | To Block Google |
| Mozilla | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/mozilla.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/mozilla_adguard.txt) | To Block Mozilla tracking |
| Microsoft | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/microsoft/all) | To Block Microsoft |
| VideoGamesAdiction | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/VideoGamesAdiction.txt) | To Block VideoGames Adiction |


#### uBlock Origin uAssets
| Lista | Link | Link dev | Descripción |
| :-- | :--: | :--: | :-- |
| uBlock filters | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/filters.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters |
| Badware risks | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/badware.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Badware risks |
| Privacy | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/privacy.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Privacy |
| Quick fixes list | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/quick-fixes.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | Quick fixes list |
| Resource abuse | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/resource-abuse.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Resource abuse |
| Unbreak | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/unbreak.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Unbreak |
| i-dont-care-about-cookies | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/unbreak.txt) | [Link DEV](https://www.i-dont-care-about-cookies.eu/) | i-dont-care-about-cookies |
| urlhaus-filter | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://malware-filter.gitlab.io/malware-filter/urlhaus-filter.txt) | [Link DEV](https://gitlab.com/malware-filter/urlhaus-filter) | urlhaus-filter |

<sup>Se ha añadido una pestaña para AdGuard con listas adaptadas a su formato.</sup>


### Comprueba tu autoalojamiento:

<details>
<summary>fivefilters:</summary>

<Original>&nbsp;Página para comprobar tu autoalojamiento desde fivefilters</Original>

<p>&nbsp;&nbsp;<a href="https://blockads.fivefilters.org/"><img src="https://img.shields.io/badge/fivefilters-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>d3ward:</summary>

<Original>&nbsp;Página para comprobar tu autoalojamiento desde [d3ward](https://d3ward.github.io/toolz/)</Original>

<p>&nbsp;&nbsp;<a href="https://d3ward.github.io/toolz/adblock.html"><img src="https://img.shields.io/badge/d3ward-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>canyoublockit:</summary>

<Original>&nbsp;Página para comprobar tu autoalojamiento desde canyoublockit</Original>

<p>&nbsp;&nbsp;<a href="https://canyoublockit.com/"><img src="https://img.shields.io/badge/CanYouBlockit-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>No more ads:</summary>

<Original>&nbsp;Página para comprobar tu autoalojamiento desde No more ads</Original>

<p>&nbsp;&nbsp;<a href="https://ads-blocker.com/es/pruebas/"><img src="https://img.shields.io/badge/Nomoreads-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;


<details>
<summary>AdBlock Tester:</summary>

<Original>&nbsp;Página para comprobar tu autoalojamiento desde AdBlock Tester</Original>

<p>&nbsp;&nbsp;<a href="https://adblock-tester.com/"><img src="https://img.shields.io/badge/AdBlocktester-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

### Comprobar DoH, DoT y DDNSSEC:

<details>
<summary>1.1.1.1 de Cloudflare:</summary>

<Original>&nbsp;Página para comprobar el cifrado de 1.1.1.1 de Cloudflare</Original>

<p>&nbsp;&nbsp;<a href="https://1.1.1.1/help"><img src="https://img.shields.io/badge/Cloudflare-1.1.1.1-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>Tenta VPN Browser:</summary>

<Original>&nbsp;Página para comprobar el cifrado de Tenta VPN Browser</Original>

<p>&nbsp;&nbsp;<a href="https://tenta.com/test/"><img src="https://img.shields.io/badge/Tenta-Browser-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>Cloudflare:</summary>

<Original>&nbsp;Página para comprobar el cifrado de Cloudflare</Original>

<p>&nbsp;&nbsp;<a href="https://www.cloudflare.com/es-es/ssl/encrypted-sni/"><img src="https://img.shields.io/badge/cloudflare-encryptedsni-2aa8ff.svg?style=flat" alt="Link"></a></p>

#### Las tecnologías analizadas son:
1. Secure DNS: una tecnología que cifra las consultas DNS e incluye DNS-over-TLS y DNS-over-HTTPS.
2. DNSSEC: una tecnología diseñada para verificar la autenticidad de las consultas DNS.
3. TLS 1.3: la última versión del protocolo TLS que incluye muchas mejoras y cierra agujeros de seguridad de versiones anteriores.
4. Encrypted SNI: significa encriptación de Server Name Indication que revela el nombre del servidor durante una conexión TLS. Esta tecnología tiene como objetivo asegurar que solo se pueda filtrar la dirección IP.
<p><sup>El único navegador que admite las cuatro tecnologías es Firefox.</sup></p>

#### Para activar las tecnologías, vaya a *about:config* y active:
<p>&nbsp;&nbsp;<code>network.security.esni.enabled</code> - pulsamos en el <code>+</code> y se ponga en <code>true</code>.</p>
<p>&nbsp;&nbsp;<code>network.trr.mode</code> – (valor 2)</p>
<p>&nbsp;&nbsp;<code>network.trr.uri</code> – <a href="https://mozilla.cloudflare-dns.com/dns-query">valor en la web Mozilla.</a></p>
<p>&nbsp;&nbsp;<code>HTTPS-Only Mode</code> - pulsamos en el <code>+</code> y se ponga en <code>true</code>.</p>
</details>
&nbsp;

<details>
<summary>Prueba de resolución DNSSEC:</summary>

<Original>&nbsp;Página para comprobar DNSSEC</Original>

<p>&nbsp;&nbsp;<a href="http://dnssec.vs.uni-due.de/"><img src="https://img.shields.io/badge/dnssec-unidue-2aa8ff.svg?style=flat" alt="Link"></a></p>
<p>&nbsp;&nbsp;<a href="http://www.dnssec-or-not.com/"><img src="https://img.shields.io/badge/dnssec-ornot-2aa8ff.svg?style=flat" alt="Link"></a></p>
<p>&nbsp;&nbsp;<a href="http://en.conn.internet.nl/connection/"><img src="https://img.shields.io/badge/connection-internet-2aa8ff.svg?style=flat" alt="Link"></a></p>
<p>&nbsp;&nbsp;<a href="https://wander.science/projects/dns/dnssec-resolver-test/"><img src="https://img.shields.io/badge/wander-project-2aa8ff.svg?style=flat" alt="Link"></a></p>

<Original>&nbsp;Página para comprobar el cifrado DNSSEC</Original>
<p>&nbsp;&nbsp;<a href="https://rootcanary.org/test.html"><img src="https://img.shields.io/badge/rootcanary-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>Test DNS leak:</summary>

<Original>&nbsp;Página para comprobar la fuga de DNS</Original>

<p>&nbsp;&nbsp;<a href="https://www.dnsleaktest.com/"><img src="https://img.shields.io/badge/DNSleak-test-2aa8ff.svg?style=flat" alt="Link"></a></p>

</details>
&nbsp;

## Aplicaciones para Pi-hole® o Adguard Home®.
Enlace al desarrollador de la aplicación:
[![GitHub](https://img.shields.io/badge/-JGeek00-171515?style=flat&logo=Github&logoColor=black&labelColor=ffffff&color=ffffff)](https://github.com/JGeek00/)

### Pi-hole®  aplicación android
<p><a><a href="https://play.google.com/store/apps/details?id=com.jgeek00.droid_hole" target="_blank" rel="noopener noreferrer"><img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/google-play.png" width="40px"></a></p>

### Adguard Home® aplicación android
<p><a><a href="https://play.google.com/store/apps/details?id=com.jgeek00.adguard_home_manager" target="_blank" rel="noopener noreferrer"><img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/google-play.png" width="40px"></a></p>

### Aplicaciones de escritorio para Adguard Home®.
<p><a><a href="https://github.com/JGeek00/adguard-home-manager/releases" target="_blank" rel="noopener noreferrer"><img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/get-github.png" width="120px"></a></p>

<p><sub>Todos y cada uno de los derechos y responsabilidades correspondientes seguirán siendo propiedad del promotor respectivo.</sub></p>

## Ayuda y contribución :raised_hands:
<p> &nbsp;Si quieres contribuir a mejorar las listas, abre un <code>issue</code> aquí:</p>
<a href="https://github.com/JuanRodenas/Pi-hole_list/issues"><img src="https://img.shields.io/badge/issues-green.svg?style=flat" alt="Link"></a>

## Créditos :rocket:
Este repositorio está hecho con todo mi amor y cariño.

[![GitHub](https://img.shields.io/badge/-JuanRodenas-171515?style=flat&logo=Github&logoColor=black&labelColor=ececec&color=ececec)](https://github.com/JuanRodenas/)

## :tada: ¡Listo!
&nbsp;

<p><sup>Estos archivos/textos se proporcionan "TAL CUAL", sin garantías de ningún tipo, expresas o implícitas, incluidas, entre otras, las garantías de comerciabilidad, idoneidad para un fin determinado y no infracción. En ningún caso los autores o titulares de los derechos de autor serán responsables de reclamaciones, daños u otras responsabilidades derivadas o relacionadas con los archivos o el uso de los mismos.</sup></p>
<p><sup>Iré actualizando con información y añadiendo procedimientos en mi tiempo libre. El contenido está bajo la licencia Creative Commons Reconocimiento - No comercial - Sin obras derivadas (by-nc-nd). Para más información sobre Creative Commons licensing, visite la <a href="https://creativecommons.org/licenses/by-nc-nd/4.0/deed.es">link to Creative Commons página</a>.</sup></p>
<p><sup>El autor del contenido es JuanRodenas. Puedes contactar conmigo en <a href="mailto:juanrodenas07@gmail.com?Subject=from%20github">mailto</a> y el sitio web del autor es <a href="https://github.com/JuanRodenas/">website</a>.</p></sup>
<p><sub>Todas y cada una de las marcas registradas son propiedad de sus respectivos dueños.</sub></p>