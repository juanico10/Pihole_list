# Pihole_list
El proyecto <strong>Pi-hole_list</strong> es un proyecto en el cual bloqueamos y protegemos en toda la red a través de su propio hardware. En este repositorio se instala con <strong>docker®</strong>. Pi-hole® y Adguard Home® es un sumidero de DNS que protege sus dispositivos de contenidos no deseados sin necesidad de instalar ningún software del lado del cliente.


<p align="center">
        <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/pihole.png" alt="Pi-hole" width="320"/>
        <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/AdGuard_Logo.png" alt="AdGuard Home" width="280"/>
    </a>
    <br>
    <strong>Bloqueo de anuncios en toda la red a través de su propio hardware</strong>
</p>
<!-- markdownlint-enable MD033 -->

![GitHub last commit](https://img.shields.io/github/last-commit/JuanRodenas/Pi-hole_list?color=blue&logo=Github&style=for-the-badge)

## Enlaces a instalación o desarrollador
| PROYECTO | LINK INSTALACIÓN | LINK DESARROLLADOR |
| :-- | :--: | :--: |
| <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/AdGuard_Logo.png" alt="AdGuard Home" width="22"/> Adguard Home® | [INSTALACIÓN](https://github.com/JuanRodenas/AdGuardHome) | [DESARROLLADOR](https://adguard.com/es/adguard-home/overview.html) |
| <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/pihole.png" alt="Pi-Hole" width="30"/> Pi-hole® | [INSTALACIÓN](https://github.com/JuanRodenas/Pihole) | [DESARROLLADOR](https://pi-hole.net/) |
### Versión latest docker Pi-hole®
![Docker Image Version (tag latest)](https://img.shields.io/docker/v/pihole/pihole/latest?color=blue&logo=docker&style=for-the-badge)
### Versión latest docker Adguard Home®
![Docker Image Version (tag latest)](https://img.shields.io/docker/v/adguard/adguardhome/latest?color=blue&logo=docker&style=for-the-badge)

## Detalles
Estas listas se crearon porque quería algo con un poco más de control sobre lo que se bloquea. Muchas listas son de todo o nada. Nos propusimos crear listas con más control sobre lo que se bloquea.

### Versiones:

<details>
<summary>Versión original:</summary>

<Original>&nbsp;Todas las urls de esta versión **van** precedidas de una dirección IP en el archivo txt o host:</Original>

<p>  &nbsp;&nbsp;<code>0.0.0.0 example.com</code> – Enviará el dominio example.com a la dirección 0.0.0.0 (pero no para sus subdominios)</p>
<p>  &nbsp;&nbsp;<code>127.0.0.1 example.com</code> – devolverá la dirección 127.0.0.1 para el dominio example.com (pero no para sus subdominios).</p>

</details>
&nbsp;
<details>
<summary>Versión sin IP a la izquierda:</summary>

<Original>&nbsp;Todas las urls de esta versión **no** van precedidas de una dirección IP en el archivo txt o host:</Original>

<p>  &nbsp;&nbsp;<code>example.com</code></p>

<sup>Nuestros usuarios nos han comunicado que algunos dispositivos dan error si la url va precedida de una dirección IP.</sup>
</details>
&nbsp;
<details>
<summary>Adguard Version:</summary>

<p>&nbsp;Todas las urls de esta versión de la lista **AdGuard** aparecen en el archivo de hosts de la siguiente manera:</p>

<p>  &nbsp;&nbsp;<code>||example.org^</code> – bloquea el acceso al dominio <code>example.org</code> y a todos sus subdominios</p>
<p>  &nbsp;&nbsp;<code>@@||example.org^</code> – desbloquea el acceso al dominio <code>example.org</code> y a todos sus subdominios</p>
<p>  &nbsp;&nbsp;<code>/REGEX/</code> – bloquea el acceso a los dominios que coincidan con la expresión regular especificada. Por ejemplo, la regla <code>/example.*/</code> bloqueará los hosts que coincidan con el <code>example.*</code></p>
<p>  &nbsp;&nbsp;<code>$</code> – Es el delimitador, que indica que el resto de la regla son modificadores. Los modificadores deben ubicarse al final de la regla después del carácter y estar separados por comas. Por ejemplo <code>||example.org^$important</code>.</p>
<p>  &nbsp;&nbsp;<code>$important</code> – El modificador aplicado a una regla aumenta su prioridad sobre cualquier otra regla sin el modificador. Incluso por encima de las reglas básicas de excepción.</p>
<p>  &nbsp;&nbsp;<code>*</code> – el carácter comodín. Se utiliza para representar cualquier conjunto de caracteres. También puede ser una cadena vacía o una cadena de cualquier longitud.</p>
<p>  &nbsp;&nbsp;<code>^</code> – el carácter separador. A diferencia del bloqueo de anuncios del navegador, no hay nada que separar en un nombre de host, por lo que el único propósito de este carácter es marcar el final del nombre de host.</p>
<p>  &nbsp;&nbsp;<code>|</code> – un puntero al principio o al final del nombre de host. El valor depende de la ubicación del carácter en la máscara. Por ejemplo, la regla <code>ample.org|</code> corresponde a <code>example.org</code>, pero no a <code>example.org.com</code>. <code>|example</code> corresponde a <code>example.org</code> pero no a <code>test.example.org</code></p>
    
<sup>Las instrucciones son actuales a partir de [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome/wiki/Hosts-Blocklists#special-characters) v0.107.2. AdGuard admite las versiones anteriores.</sup>
<sup>Las instrucciones que admite [AdGuard Home](https://kb.adguard.com/en/general/how-to-create-your-own-ad-filters).</sup>
</details>
&nbsp;
<details>
<summary>Comentarios en las listas:</summary>

<p>&nbsp;Todas las urls de esta versión de la lista aparecen en el archivo de hosts de la siguiente manera</p>

<p>  &nbsp;&nbsp;<code># comentario</code> – solo un comentario</p>
<p>  &nbsp;&nbsp;<code>! comentario</code> – solo un comentario</p>

</details>
&nbsp;

### Uso:
<details>
    <summary>Utilizar con Pi-Hole <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/pihole.png" alt="Pi-Hole" width="30"/>:</summary>

## Instrucciones de uso con Pi-Hole:

1. Copie el enlace al formato Pi-hole de la lista deseada (de la tabla correspondiente que aparece a continuación).
2. Añade la URL a las listas de bloqueo de tu Pi-hole (**Inicio de sesión** > **Gestión de grupos** > **Listas** > **Pega la URL de la lista en el campo "Dirección", añade un comentario** > **Haz clic en "Añadir "**)
3. Actualizar Gravity (**Herramientas** > **Actualizar Gravity** > **Hacer clic en "Actualizar "** )

&nbsp;
<sup>Instrucciones actuales a partir de Pi-hole 5.2.4. Las instrucciones pueden ser ligeramente diferentes en la actualidad. Las instrucciones se actualizarán cuando se publique la versión 6.</sup>
</details>
&nbsp;

<details>
    <summary>Utilizar con AdGuard Home <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/AdGuard_Logo.png" alt="AdGuard Home" width="22"/>:</summary>

## Instrucciones de uso con AdGuard Home:

1. Copie el enlace al formato de AdGuard correspondiente a la lista deseada (de la tabla correspondiente a continuación).
2. Añada la URL a su lista de bloqueo de AdGuard (**Inicio de sesión** > **Filtros** > **Listas de bloqueo DNS** > **Añadir lista de bloqueo** > **Añadir una lista personalizada** > **Introducir nombre** > **Pegar la URL del enlace copiado**)
3. La lista se activa automáticamente y está lista para empezar a bloquear.

&nbsp;
<sup>Las instrucciones son actuales a partir de AdGuard Home v0.107.2</sup>
</details>
&nbsp;

## Configuración Adguard Home®:<img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/AdGuard_Logo.png" alt="AdGuard Home" width="32"/>

### Configuración para tener habilitado DNS over TLS o DNS over HTTPS
En ajustes de AdGuard, configuración de DNS:
- Servidores DNS de subida, copiar una de estas URLs:

Para DoH-DoT de Cloudfare:
```
https://dns.cloudflare.com/dns-query
tls://1dot1dot1dot1.cloudflare-dns.com
```
Para DoH-DoT de Quad9:
```
https://dns.quad9.net/dns-query
tls://dns.quad9.net
```

y marcar la opcion: "**Balanceo de carga**", por defecto esta marcada.

- Servidores DNS de arranque, metemos las DNS que elijamos:

Cloudflared tanto en IPv4 como IPv6:
```
1.1.1.1
1.0.0.1
2606:4700:4700::1111
2606:4700:4700::1001
```
Quad9 tanto en IPv4 como IPv6:
```
9.9.9.9
149.112.112.112
2620:fe::fe
2620:fe::fe:9
```

- Configuración del servidor DNS, marcamos la opcion de "**Habilitar DNSSEC**"

## Añadir dominio para DoH y DoT:

### Crear el certificado con Let’s Encrypt
<details>
    <summary>Crear el certificado personal autofirmado con Let’s Encrypt:</summary>

#### Crear el certificado personal autofirmado con Let’s Encrypt:
Instalando un certificado SSL gratuito con CertBot:
1. Actualizamos la lista de paquetes..
~~~
sudo apt-get update
~~~
2. Instalamos el paquete de Certbot
~~~
sudo apt-get install certbot
~~~
3. Ejecuta el siguiente comando modificando el correo electrónico válido para adquirir un certificado Wildcard:
~~~
certbot certonly -d '*.your_domain' --manual --preferred-challenges=dns --email usuario@ejemplo.com --server https://acme-v02.api.letsencrypt.org/directory --agree-tos
~~~
4. Por último, pedirá realizar un registro _acme-challenge tipo TXT en nuestro proveedor de servidores de nombres con el contenido que nos indica:
Nos crea los siguientes archivos, en el directorio <code>/etc/letsencrypt/live/</code>:
- <code>fullchain.pem</code> – su certificado SSL codificado en PEM.
- <code>privkey.pem</code> – su clave privada codificada en PEM.

#### Configuración de Lets encrypt
Pasos a seguir tras solicitar el certificado:
* Pedirá la introducción del dominio a certificar, indícalo utilizando <code>*.</code> más el dominio que deseas certificar para obtener el Wildcard.
* Por último, pedirá realizar un registro <code>_acme-challenge</code> tipo TXT en nuestro proveedor de servidores de nombres con el contenido que nos indica.

Para comprobar si el certificado se autorenovará:
* Prueba de renovación (simulación):<code>certbot renew --dry-run</code>
* Comprueba el estado del servicio de temporizador de Certbot: <code>systemctl status certbot.timer</code>
* Para renovar un certificado: <code>certbot renew</code>
	* Para forzar la autorenovación: <code>--force-renewal</code>
* Para listar los trabajos: <code>systemctl list-timers --all</code> Debe aparecer el siguiente configurado para la renovación automática: <code>certbot.timer - certbot.service</code>
* Listando certificados: <code>certbot certificates</code>

Para revocar un certificado:
* Eliminar por completo un certificado: <code>certbot delete --cert-name example.com</code>
* Desde la cuenta para la que se emitió el certificado: <code>certbot revoke --cert-path /etc/letsencrypt/archive/${YOUR_DOMAIN}/cert1.pem</code>
* Usando la clave privada del certificado: <code>certbot revoke --cert-path /PATH/TO/cert.pem --key-path /PATH/TO/key.pem</code>

Si no quieren realizar todo estos pasos, pueden obtener el certificado con [Zero SSL](https://zerossl.com/). pero el certificado wildcard es vía pago.
</details>

### Crear el certificado personal autofirmado con OPENSSL:
<details>
    <summary>Crear el certificado personal autofirmado:</summary>

#### Crear el certificado personal autofirmado:

Info: [INFO](https://www.busindre.com/comandos_openssl_utiles_para_certificados)
1. Actualizamos la lista de paquetes..
~~~
sudo apt-get update
~~~
2. Instalamos el paquete de openssl
~~~
sudo apt-get install openssl
~~~
3. Creamos el directorio donde queremos almacenar los certificados:
~~~
mkdir certs 
cd certs/
~~~
4. Creamos certificado con el siguiente comando, cambiando la ruta del certificado o dejamos el nombre del .key y punto crt para almacenarlo en el directorio:
~~~
sudo openssl req -x509 -nodes -days 1825 -sha512 -newkey ec -pkeyopt ec_paramgen_curve:prime256v1 -subj "/CN=localhost/O=Tech/C=ES" -addext "subjectAltName = DNS:*.example.org" -keyout privkey.key -out privcert.pem
~~~

* Puede que nos pregunte estas preguntas:
<ul><code>Country Name (2 letter code) [AU]: US</code></ul>
<ul><code>State or Province Name (full name) [Some-State]: New York</code></ul>
<ul><code>Locality Name (eg, city) []: New York City</code></ul>
<ul><code>Organization Name (eg, company) [Internet Widgits Pty Ltd]: Bouncy Castles, Inc.</code></ul>
<ul><code>Organizational Unit Name (eg, section) []: Ministry of Water Slides</code></ul>
<ul><code>Common Name (e.g. server FQDN or YOUR name) []: server_IP_address or domain</code></ul>
<ul><code>Email Address []: admin@your_domain.com</code></ul>

* Notas para el asunto/emisor
<p><ul><code>/C=ES/ST=Spain/L=Madrid/O=Juan Tech/OU=Tech/CN=localhost</code></ul></p>
<p><ul><code>C = ES</code></ul></p>
<p><ul><code>ST = Bayern</code></ul></p>
<p><ul><code>L = Munich</code></ul></p>
<p><ul><code>O = Inventos</code></ul></p>
<p><ul><code>OU = Tech</code></ul></p>
<p><ul><code>CN = localhost</code></ul></p>

</details>


## Configurar certificado en AdGuard Home:
1. Abra la interfaz web de AdGuard Home y vaya a configuración.
2. Desplácese en el menú hasta la configuración: <code>Configuración de cifrado</code>.
3. Habilitar el check <code>Habilitar cifrado (HTTPS, DNS mediante HTTPS y DNS mediante TLS)</code>.
4. Habilitar <code>Redireccionar a HTTPS automáticamente</code>.
5. Ingrese su nombre de dominio en <code>Nombre del servidor</code>. Si vas a ingresar un wildcard, ingresar con <code>"*."</code>.
6. Copie/pegue el contenido del archivo `fullchain.pem` en <code>Certificados</code>.
7. Copie / pegue el contenido del archivo `privkey.pem` en <code>Clave privada</code>.
8. Haga clic en <code>Guardar configuración</code>.

## Configurar el dominio para permitir clientes en DNS privado DoH y DoT:
Para crear una zona en tu dominio tanto para <code>*.example.org</code> para permitir los clientes, sigue estos pasos:

#### Instrucciones de uso:

1. Accede al panel de control de tu proveedor de alojamiento web o del registrador de dominios donde hayas adquirido el nombre de dominio.
2. Busca la opción de `Zonas DNS`.
3. Crea una nueva entrada de `Zonas DNS`. Para agregar la entrada `*.example.org`, crea un registro de tipo `CNAME` (Alias) y haz que apunte a `*.example.org`. Esto permitirá que cualquier subdominio que comience con un asterisco, como `subdominio.example.org`.
4. Configuración de `Configuración/Clientes/Clientes persistentes`. Pulsamos `Añadir clientes` y en `Identificador` creamos un nombre.

<sup>Instrucciones actuales en la documentación del desarrollador <a href="https://github.com/AdguardTeam/AdGuardHome/wiki/Clients#clientid">documentación</a>.</sup>



# Listas para Pihole <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/pihole.png" alt="Pi-Hole" width="40"/> y AdGuard Home <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/AdGuard_Logo.png" alt="AdGuard Home" width="32"/>

## Main safelist

| List | Link | Description |
| :-- | :--: | :-- |
| safelist repositorio | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/Listas/whitelist.txt) | safelist JuanRodenas |
| safelist hagezi | [Link](https://raw.githubusercontent.com/hagezi/dns-blocklists/main/whitelist.txt) | safelist hagezi |


## Main Black Lists
<sup>Columna Link: Pi-hole® | Adguard Home®.</sup>

#### Host
| List Host | Link | Description |
| :-- | :--: | :-- |
| List oisd | [Link](https://dbl.oisd.nl) &#124; [Link](https://abp.oisd.nl) | To Block host Adguard and domains [dbl.oisd](https://oisd.nl/) |
| The big list | [Link](https://big.oisd.nl/domains) &#124; [Link](https://big.oisd.nl/) | The big list [oisd](https://oisd.nl/) |
| urlhaus-filter-domains | [Link](https://malware-filter.gitlab.io/malware-filter/urlhaus-filter-domains.txt) &#124; [Link](https://malware-filter.gitlab.io/malware-filter/urlhaus-filter-agh.txt) | urlhaus-filter DEV [Link](https://gitlab.com/malware-filter/urlhaus-filter) |
| everything | [Link](https://blocklistproject.github.io/Lists/everything.txt) &#124; [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/everything-ags.txt) | To Block everything |
| energized pro | [Link](https://energized.pro/unified/formats/hosts.txt) &#124; [Link](https://block.energized.pro/ultimate/formats/hosts.txt) | To Block [energized](https://energized.pro/) |
| d3ward | [Link](https://raw.githubusercontent.com/d3ward/toolz/master/src/d3host.txt) &#124; [Link](https://raw.githubusercontent.com/d3ward/toolz/master/src/d3host.adblock) | [d3ward](https://github.com/d3ward) popular list |


#### Malware / Shock / Porn / Adult 
| List | Link | Description |
| :-- | :--: | :-- |
| The NSFW list | [Link](https://nsfw.oisd.nl/domains) &#124; [Link](https://nsfw.oisd.nl/) | The NSFW list [oisd](https://oisd.nl/) |
| Gambling-porn | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/Gambling.txt) &#124; [Link](https://github.com/blocklistproject/Lists/blob/master/adguard/gambling-ags.txt) | To Block Gambling and porn |
| Malware | [Link](https://blocklistproject.github.io/Lists/malware.txt) &#124; [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/malware-ags.txt) | To Block malware |
| Ransomware | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/ransomware.txt) &#124; [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/ransomware-ags.txt) | To Block ransomware |
| phishing | [Link](https://phishing.army/download/phishing_army_blocklist_extended.txt) | To Block phishing |


#### Tracking/Ads
| List Tracking/Ads | Link | Description |
| :-- | :--: | :-- |
| SmartTV | [Link](https://raw.githubusercontent.com/Perflyst/PiHoleBlocklist/master/SmartTV.txt) &#124; [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/smart-tv-ags.txt) | To Block SmartTV |
| WindowsSpyBlocker | [Link](https://raw.githubusercontent.com/crazy-max/WindowsSpyBlocker/master/data/hosts/spy.txt) | To Block WindowsSpyBlocker |
| GoodbyeAds-Ultra | [Link](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Hosts/GoodbyeAds-Ultra.txt) &#124; [Link](https://raw.githubusercontent.com/hagezi/dns-blocklists/main/adblock/pro.plus.txt) | To Block [hagezi](https://github.com/hagezi/dns-blocklists) and [jerryn70](https://github.com/jerryn70/GoodbyeAds) |
| ads-and-tracking-extended | [Link](https://www.github.developerdan.com/hosts/lists/ads-and-tracking-extended.txt) | To Block ads-and-tracking-extended |
| Adblock_Plus | [Link](https://raw.githubusercontent.com/notracking/hosts-blocklists/master/adblock/adblock.txt) &#124; [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/Adblock_Plus_Ads.txt) | To Block Tracking AdBlock |
| Android tracking | [Link](https://github.com/JuanRodenas/Pihole_list/blob/main/Listas/android-tracking.txt) | Android tracking for AdGuard Home |

#### Adguard team filters
| List Tracking/Ads | Link | Description |
| :-- | :--: | :-- |
| AdGuardSDNSFilter | [Link](https://adguardteam.github.io/AdGuardSDNSFilter/Filters/filter.txt) | AdGuard team DNS filter |
| AdAway | [Link](https://adaway.org/hosts.txt) | AdAway default blocklist |
| Game Console Adblock List | [Link](https://raw.githubusercontent.com/DandelionSprout/adfilt/master/GameConsoleAdblockList.txt) | Game Console Adblock List |
| SmartTV-AGH | [Link](https://raw.githubusercontent.com/Perflyst/PiHoleBlocklist/master/SmartTV-AGH.txt) | Smart-TV Blocklist for AdGuard Home |
| Peter Lowe's List | [Link](https://pgl.yoyo.org/adservers/serverlist.php?hostformat=adblockplus&showintro=1&mimetype=plaintext) | Blocklist for use with Adblock Plus |

#### Services
| List Services | Link | Description |
| :-- | :--: | :-- |
| Youtube | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/youtube.txt) &#124; [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/youtube-ags.txt) | To Block youtube |
| Facebook | [Link](https://github.com/jmdugan/blocklists/blob/master/corporations/facebook/all) | To Block Facebook/Instagram/Whatsapp |
| Whatsapp open | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/facebook/all-but-whatsapp) | To Block Facebook/Instagram but leave Whatsapp open |
| Google | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/google/all) | To Block Google |
| Mozilla | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/mozilla.txt) &#124; [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/mozilla_adguard.txt) | To Block Mozilla tracking |
| Microsoft | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/microsoft/all) | To Block Microsoft |
| VideoGamesAdiction | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/VideoGamesAdiction.txt) | To Block VideoGames Adiction |


#### uBlock Origin uAssets
| List Services | Link | Link dev | Description |
| :-- | :--: | :--: | :-- |
| uBlock filters | [Link](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/filters.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters |
| Badware risks | [Link](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/badware.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Badware risks |
| Privacy | [Link](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/privacy.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Privacy |
| Quick fixes list | [Link](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/quick-fixes.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | Quick fixes list |
| Resource abuse | [Link](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/resource-abuse.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Resource abuse |
| Unbreak | [Link](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/unbreak.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Unbreak |
| i-dont-care-about-cookies | [Link](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/unbreak.txt) | [Link DEV](https://www.i-dont-care-about-cookies.eu/) | i-dont-care-about-cookies |
| urlhaus-filter | [Link](https://malware-filter.gitlab.io/malware-filter/urlhaus-filter.txt) | [Link DEV](https://gitlab.com/malware-filter/urlhaus-filter) | urlhaus-filter |

<sup>Se ha añadido una pestaña para AdGuard con listas adaptadas a su formato.</sup>


### Comprobar tu SelfHosted:

<details>
<summary>fivefilters:</summary>

<Original>&nbsp;Pagina para comprobar tu selfhosted de fivefilters</Original>

<p>  &nbsp;&nbsp;https://blockads.fivefilters.org/</p>
</details>
&nbsp;

<details>
<summary>d3ward:</summary>

<Original>&nbsp;Pagina para comprobar tu selfhosted de [d3ward](https://d3ward.github.io/toolz/)</Original>

<p>  &nbsp;&nbsp;https://d3ward.github.io/toolz/adblock.html</p>
</details>
&nbsp;

<details>
<summary>canyoublockit:</summary>

<Original>&nbsp;Pagina para comprobar tu selfhosted de canyoublockit</Original>

<p>  &nbsp;&nbsp;https://canyoublockit.com/</p>
</details>
&nbsp;

<details>
<summary>No more ads:</summary>

<Original>&nbsp;Pagina para comprobar tu selfhosted de No more ads</Original>

<p>  &nbsp;&nbsp;https://ads-blocker.com/es/pruebas/</p>
</details>
&nbsp;


<details>
<summary>AdBlock Tester:</summary>

<Original>&nbsp;Pagina para comprobar tu selfhosted de AdBlock Tester</Original>

<p>  &nbsp;&nbsp;https://adblock-tester.com/</p>
</details>
&nbsp;

### Comprobar DoH, DoT y DDNSSEC:

<details>
<summary>1.1.1.1 de Cloudflare:</summary>

<Original>&nbsp;Pagina para comprobar cifrado de 1.1.1.1 de Cloudflare</Original>

<p>  &nbsp;&nbsp;https://1.1.1.1/help</p>
</details>
&nbsp;

<details>
<summary>Tenta VPN Browser:</summary>

<Original>&nbsp;Pagina para comprobar cifrado de Tenta VPN Browser</Original>

<p>  &nbsp;&nbsp;https://tenta.com/test/</p>
</details>
&nbsp;

<details>
<summary>Cloudflare:</summary>

<Original>&nbsp;Pagina para comprobar cifrado de Cloudflare</Original>

<p>  &nbsp;&nbsp;https://www.cloudflare.com/es-es/ssl/encrypted-sni/</p>

#### Las tecnologías analizadas son:
1. Secure DNS: una tecnología que cifra las consultas DNS e incluye DNS-over-TLS y DNS-over-HTTPS.
2. DNSSEC: tecnología diseñada para verificar la autenticidad de las consultas DNS.
3. TLS 1.3: la última versión del protocolo TLS que incluye muchas mejoras y cierra brechas de seguridad de las anteriores.
4. Encrypted SNI: siglas de Server Name Indication cifrado que desvela el nombre del hostname durante una conexión TLS. Esta tecnología busca asegurar que sólo pueda filtrarse la dirección IP.
<p><sup>El único navegador que soporta las cuatro tecnologías es Firefox.</sup></p>

#### Para activar las tecnologías debemos acceder a `about:config` y activar:
<p>  &nbsp;&nbsp;<code>network.security.esni.enabled</code> - pulsamos en el <code>+</code> y se ponga en <code>true</code>.</p>
<p>  &nbsp;&nbsp;<code>network.trr.mode</code> – (valor 2)</p>
<p>  &nbsp;&nbsp;<code>network.trr.uri</code> – <a href="https://mozilla.cloudflare-dns.com/dns-query">valor en la web Mozilla.</a></p>
<p>  &nbsp;&nbsp;<code>HTTPS-Only Mode</code> - pulsamos en el <code>+</code> y se ponga en <code>true</code>.</p>
</details>
&nbsp;

<details>
<summary>DNSSEC Resolver Test:</summary>

<Original>&nbsp;Pagina para comprobar cifrado DNSSEC por Matthäus Wander</Original>

<p>  &nbsp;&nbsp;http://dnssec.vs.uni-due.de/</p>
<p>  &nbsp;&nbsp;http://www.dnssec-or-not.com/</p>
<p>  &nbsp;&nbsp;http://en.conn.internet.nl/connection/</p>
</details>
&nbsp;

<details>
<summary>DNS leak test:</summary>

<Original>&nbsp;Pagina para comprobar fuga de DNS</Original>

<p>  &nbsp;&nbsp;https://www.dnsleaktest.com/</p>

</details>
&nbsp;

## Aplicaciones android para Pi-hole® o Adguard Home®
Link al desarrollador de la aplicacion: [![GitHub](https://img.shields.io/static/v1.svg?color=blue&labelColor=555555&logoColor=ffffff&style=social&label=JGeek00&message=GitHub&logo=github)](https://github.com/JGeek00 "view the source for all of our repositories.")
### Aplicacion android Pi-hole®
<a href="https://play.google.com/store/apps/details?id=com.jgeek00.droid_hole" target="_blank" rel="noopener noreferrer"><img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/google-play.png" width="60px"></a>
### Aplicacion android Adguard Home®
<a href="https://play.google.com/store/apps/details?id=com.jgeek00.adguard_home_manager" target="_blank" rel="noopener noreferrer"><img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/google-play.png" width="60px"></a>

<p><sub>Todos y cada uno de los derechos y responsabilidades correspondientes son propiedad del respectivo desarrollador.</sub></p>

## HELP ME 🙌
<p> &nbsp;If you want to contribute to improve the lists, open a <code>issue</code> here:  <A HREF="https://github.com/JuanRodenas/Pi-hole_list/issues"> ISSUE </A></p>
<sup>Si deseas contribuir a mejorar las listas, ábreme un problema aquí.</sup>

## Credits 🚀
This repository is made with all my love and affection.
#
[![GitHub](https://img.shields.io/static/v1.svg?color=blue&labelColor=555555&logoColor=ffffff&style=social&label=JuanRodenas&message=GitHub&logo=github)](https://github.com/JuanRodenas "view the source for all of our repositories.")

# 🎉 ¡Ready!
&nbsp;

<sup>Estos archivos/textos se proporcionan "TAL CUAL", sin garantías de ningún tipo, expresas o implícitas, incluidas, entre otras, las garantías de comerciabilidad, idoneidad para un fin determinado y no infracción. En ningún caso los autores o los titulares de los derechos de autor serán responsables de ninguna reclamación, daño u otra responsabilidad derivada de, o relacionada con los archivos o el uso de los mismos.</sup>

<sub>Todas y cada una de las marcas registradas son propiedad de sus respectivos dueños.</sub>

<p><sup>Iré actualizando con información y añadiendo procedimientos en mi tiempo libre.</sup></p>
