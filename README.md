# Pi-hole_list
El proyecto Pi-hole® es para bloqueo de anuncios en toda la red a través de su propio hardware Linux. Pi-hole® es un sumidero de DNS que protege sus dispositivos de contenidos no deseados sin necesidad de instalar ningún software del lado del cliente.


<p align="center">
    <a href="https://pi-hole.net/">
        <img src="https://github.com/JuanRodenas/Pi-hole_list/blob/main/pihole.png" alt="Pi-hole">
    </a>
    <br>
    <strong>Bloqueo de anuncios en toda la red a través de su propio hardware</strong>
</p>
<!-- markdownlint-enable MD033 -->


## Detalles
Estas listas se crearon porque quería algo con un poco más de control sobre lo que se bloquea. Muchas listas son de todo o nada. Nos propusimos crear listas con más control sobre lo que se bloquea.

## Versiones:

<details>
<summary>Versión original:</summary>

<Original>&nbsp;Todas las urls de la versión de la lista aparecen en el archivo de host de la siguiente manera</Original>

<p>  &nbsp;&nbsp;0.0.0.0 example.com</p>
</details>
&nbsp;
<details>
<summary>Versión sin ceros a la izquierda:</summary>

<p>&nbsp;Todas las urls de esta versión de la lista aparecen en el archivo de hosts de la siguiente manera</p>

<p>  &nbsp;&nbsp;example.com</p>

Nuestros usuarios nos han llamado la atención sobre el hecho de que algunos dispositivos dan error si la url va precedida de una dirección IP.
</details>
&nbsp;
<details>
<summary>Adguard Version:</summary>

<p>&nbsp;Todas las urls de esta versión de la lista aparecen en el archivo de hosts de la siguiente manera</p>

<p>  &nbsp;&nbsp;||example.com^</p>


Se ha solicitado añadir soporte para AdGuard. Actualmente estamos probando nuestras listas. Por favor, proporcione sus comentarios.
</details>
&nbsp;


## Uso:
<details>
    <summary>Utilizar con <a href="https://pi-hole.net" target="_blank">Pi-Hole</a>:</summary>

## Instrucciones de uso con Pi-Hole:

1. Copie el enlace al formato Pi-hole de la lista deseada (de la tabla correspondiente que aparece a continuación).
2. Añade la URL a las listas de bloqueo de tu Pi-hole (**Inicio de sesión** > **Gestión de grupos** > **Listas** > **Pega la URL de la lista en el campo "Dirección", añade un comentario** > **Haz clic en "Añadir "**)
3. Actualizar Gravity (**Herramientas** > **Actualizar Gravity** > **Hacer clic en "Actualizar "** )

&nbsp;
<sup>Instrucciones actuales a partir de Pi-hole 5.2.4. Las instrucciones pueden ser ligeramente diferentes en la actualidad. Las instrucciones se actualizarán cuando se publique la versión 6.</sup>
</details>
&nbsp;

<details>
    <summary>Using with <a href="https://adguard.com/en/adguard-home/overview.html">AdGuard Home</a>:</summary>

## Instrucciones de uso con AdGuard Home:

1. Copie el enlace al formato de AdGuard correspondiente a la lista deseada (de la tabla correspondiente a continuación).
2. Añada la URL a su lista de bloqueo de AdGuard (**Inicio de sesión** > **Filtros** > **Listas de bloqueo DNS** > **Añadir lista de bloqueo** > **Añadir una lista personalizada** > **Introducir nombre** > **Pegar la URL del enlace copiado**)
3. La lista se activa automáticamente y está lista para empezar a bloquear.

&nbsp;
<sup>Las instrucciones son actuales a partir de AdGuard Home v0.107.2</sup>
</details>
&nbsp;


# Listas para Pihole

## Main White Lists

| List | Link | AdGuard | Description |
| -- | :--: | :--: | -- |
| Whitelist | [Link](https://raw.githubusercontent.com/anudeepND/whitelist/master/domains/whitelist.txt) | - | Lista blanca a permitir |


## Main Black Lists

#### Host
| List Host | Link | AdGuard | Description |
| -- | :--: | :--: | -- |
| Listas oisd | [Link](https://dbl.oisd.nl) | [Link](https://abp.oisd.nl) | To Block host Adguard and domains [dbl.oisd](https://oisd.nl/) |
| urlhaus-filter-domains | [Link](https://raw.githubusercontent.com/AzagraMac/PiHoleDocker/master/list/urlhaus-filter-domains.txt) | - | - |
| everything | [Link](https://blocklistproject.github.io/Lists/everything.txt) | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/everything-ags.txt) | To Block everything |
| energized pro | [Link](https://energized.pro/unified/formats/hosts.txt) | [Link]() | To Block [energized](https://energized.pro/) |



#### Malware
| List Malware | Link | AdGuard | Description |
| -- | :--: | :--: | -- |
| Gambling-porn | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/Gambling.txt) | [Link](https://github.com/blocklistproject/Lists/blob/master/adguard/gambling-ags.txt) | To Block Gambling and porn |
| Malware | [Link](https://blocklistproject.github.io/Lists/malware.txt) | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/malware-ags.txt) | To Block malware |
| Ransomware | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/ransomware.txt) | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/ransomware-ags.txt) | To Block ransomware |
| phishing | [Link](https://phishing.army/download/phishing_army_blocklist_extended.txt) | - | To Block phishing |



#### Tracking/Ads
| List Tracking/Ads | Link | AdGuard | Description |
| -- | :--: | :--: | -- |
| SmartTV | [Link](https://raw.githubusercontent.com/Perflyst/PiHoleBlocklist/master/SmartTV.txt) | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/smart-tv-ags.txt) | To Block SmartTV |
| WindowsSpyBlocker | [Link](https://raw.githubusercontent.com/crazy-max/WindowsSpyBlocker/master/data/hosts/spy.txt) | - | To Block WindowsSpyBlocker |
| AndroidTracking | [Link](https://raw.githubusercontent.com/AzagraMac/PiHoleDocker/master/list/AndroidTracking.txt) | - | To Block AndroidTracking |
| TrackingAds | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/TrackingAds.txt) | - | To Block Tracking, Ads and spammers |
| GoodbyeAds-Ultra | [Link](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Hosts/GoodbyeAds-Ultra.txt) | [Link](https://raw.githubusercontent.com/Zelo72/adguard/main/d3host.adblock) | To Block GoodbyeAds |
| ads-and-tracking-extended | [Link](https://www.github.developerdan.com/hosts/lists/ads-and-tracking-extended.txt) | - | To Block ads-and-tracking-extended |
| Adblock_Plus | [Link](https://raw.githubusercontent.com/notracking/hosts-blocklists/master/adblock/adblock.txt) | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/Adblock_Plus_Ads.txt) | To Block Tracking AdBlock |


#### Services
| List Services | Link | AdGuard | Description |
| -- | :--: | :--: | -- |
| Youtube | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/youtube.txt) | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/youtube-ags.txt) | To Block youtube |
| Facebook | [Link](https://github.com/jmdugan/blocklists/blob/master/corporations/facebook/all) | - | To Block Facebook/Instagram/Whatsapp |
| Whatsapp open | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/facebook/all-but-whatsapp) | - | To Block Facebook/Instagram but leave Whatsapp open |
| Google | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/google/all) | - | To Block Google |
| Mozilla | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/mozilla.txt) | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/mozilla_adguard.txt) | To Block Mozilla tracking |
| Microsoft | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/microsoft/all) | - | To Block Microsoft |
| VideoGamesAdiction | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/VideoGamesAdiction.txt) | - | To Block VideoGames Adiction |


## Comprobar tu SelfHosted:

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

## Comprobar DoH, DoT y DDNSSEC:

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

## Ready!
