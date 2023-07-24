<h1 align="center"> The project that protects your devices </h1>

The project <strong>Pi-hole_list</strong> is a project in which we block and protect the entire network through its own hardware. In this repository it is installed with <strong>docker®</strong>. Pi-hole® and Adguard Home® is a DNS sinkhole that protects your devices from unwanted content without the need to install any client-side software.

<div align="center">
    <a href="https://github.com/JuanRodenas/Pihole_list">
        <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/pihole.png" alt="Pi-hole" width="320">
        <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/AdGuard_Logo.png" alt="AdGuard Home" width="280">
    </a>
    <br>
    <h3>Network-wide ad blocking via its own hardware.</h3>
</div>

![GitHub last commit (by committer)](https://img.shields.io/github/last-commit/JuanRodenas/Pi-hole_list?style=flat&logo=Github&logoColor=white&label=last-commit&labelColor=253B80&color=253B80)

## Links to installation or developer
| PROJECT | INSTALLER LINK | DEVELOPER LINK |
| :-- | :--: | :--: |
| <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/AdGuard_Logo.png" alt="AdGuard Home" width="26"/> Adguard Home® | [INSTALLATION](https://github.com/JuanRodenas/AdGuardHome) | [DEVELOPER](https://adguard.com/es/adguard-home/overview.html) |
| <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/pihole.png" alt="Pi-Hole" width="30"/> Pi-hole® | [INSTALLATION](https://github.com/JuanRodenas/Pihole) | [DEVELOPER](https://pi-hole.net/) |
### Version docker latest Pi-hole®
![Docker Image Version (tag latest)](https://img.shields.io/docker/v/pihole/pihole/latest?style=flat&logo=docker&logoColor=white&labelColor=0088cc&color=0088cc)

### Version docker latest Adguard Home®
![Docker Image Version (tag latest)](https://img.shields.io/docker/v/adguard/adguardhome/latest?style=flat&logo=docker&logoColor=white&labelColor=0088cc&color=0088cc)

## Details
These lists were created because I wanted something with a bit more control over what gets blocked. A lot of lists are all-or-nothing. We set out to create lists with more control over what gets blocked, which is why I recommend my lists to you, as they are tested and we block only what is unnecessary.

### Versions:

<details>
<summary>Original version:</summary>

<Original>&nbsp;All urls in this version **are** preceded by an IP address in the txt or host file:</Original>

<p>  &nbsp;&nbsp;<code>0.0.0.0 example.com</code> – It will forward the domain example.com to the address 0.0.0.0 (but not for its subdomains).</p>
<p>  &nbsp;&nbsp;<code>127.0.0.1 example.com</code> – will return the address 127.0.0.1 for the domain example.com (but not for its subdomains).</p>

</details>
&nbsp;
<details>
<summary>Version without IP on the left:</summary>

<Original>&nbsp;All urls in this version **no** are preceded by an IP address in the txt or host file:</Original>

<p>  &nbsp;&nbsp;<code>example.com</code></p>

<sup>Our users have reported to us that some devices give an error if the url is preceded by an IP address.</sup>
</details>
&nbsp;
<details>
<summary>Adguard version:</summary>

<p>&nbsp;All urls from this version of the **AdGuard** list appear in the hosts file as follows:</p>

<p>  &nbsp;&nbsp;<code>||example.org^</code> – blocks access to the domain <code>example.org</code> and all its subdomains</p>
<p>  &nbsp;&nbsp;<code>@@||example.org^</code> – unlocks access to the <code>example.org</code> domain and all its subdomains.</p>
<p>  &nbsp;&nbsp;<code>/REGEX/</code> – blocks access to domains matching the specified regular expression. For example, the rule <code>/example.*/</code> will block hosts matching the <code>example.*</code></p>
<p>  &nbsp;&nbsp;<code>$</code> – This is the delimiter, which indicates that the rest of the rule is a modifier. Modifiers must be placed at the end of the rule after the character and separated by commas. For example, the modifiers must be placed at the end of the rule after the character and separated by commas. <code>||example.org^$important</code>.</p>
<p>  &nbsp;&nbsp;<code>$important</code> – The modifier applied to a rule increases its priority over any other rule without the modifier. Even above the basic exception rules.</p>
<p>  &nbsp;&nbsp;<code>*</code> – the wildcard character. It is used to represent any set of characters. It can also be an empty string or a string of any length.</p>
<p>  &nbsp;&nbsp;<code>^</code> – the separator character. Unlike browser ad blocking, there is nothing to separate in a hostname, so the only purpose of this character is to mark the end of the hostname.</p>
<p>  &nbsp;&nbsp;<code>|</code> – a pointer to the beginning or end of the host name. The value depends on the location of the character in the mask. For example, the rule <code>ample.org|</code> corresponds to <code>example.org</code>, but not to <code>example.org.com</code>. <code>|example</code> corresponds to <code>example.org</code> but not to <code>test.example.org</code></p>
    
<sup>The instructions are current as of [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome/wiki/Hosts-Blocklists#special-characters) v0.107.2. AdGuard supports older versions.</sup>
<sup>The instructions it supports [AdGuard Home](https://kb.adguard.com/en/general/how-to-create-your-own-ad-filters).</sup>
</details>
&nbsp;
<details>
<summary>Comments on the lists:</summary>

<p>&nbsp;All urls for this version of the list appear in the hosts file in the following way</p>

<p>  &nbsp;&nbsp;<code># comment</code> – just a comment</p>
<p>  &nbsp;&nbsp;<code>! comment</code> – just a comment</p>

</details>
&nbsp;

### Use:
<details>
    <summary>Use with Pi-Hole <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/pihole.png" alt="Pi-Hole" width="30"/>:</summary>

## Instructions for use with Pi-Hole:

1. Copy the link to the Pi-hole format of the desired list (from the corresponding table below).
2. Add the URL to your Pi-hole block lists (**Login** > **Groups management** > **Lists** > **Paste the URL of the list in the "Address" field, add a comment** > **Click "Add "**).
3. Update Gravity (**Tools** > **Update Gravity** > **Click on "Update "** )

&nbsp;
<sup>Current instructions as of Pi-hole 5.2.4. Instructions may be slightly different at present. Instructions will be updated when version 6 is released.</sup>
</details>
&nbsp;

<details>
    <summary>Use with AdGuard Home <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/AdGuard_Logo.png" alt="AdGuard Home" width="22"/>:</summary>

## Instructions for use with AdGuard Home:

1. copy the link to the AdGuard format corresponding to the desired list (from the corresponding table below).
2. Add the URL to your AdGuard block list (**Login** > **Filters** > **DNS block lists** > **Add block list** > **Add a custom list** > **Enter name** > **Paste the URL of the copied link**).
3. The list is automatically activated and is ready to start blocking.

&nbsp;
<sup>Instructions are current as of AdGuard Home v0.107.2</sup>
</details>
&nbsp;

## Adguard Home® configuration: <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/adguard_home_lightmode.svg" alt="AdGuard Home" width="100"/>

### Setting to have DNS over TLS or DNS over HTTPS enabled
In AdGuard settings, DNS settings:
- Upstream DNS servers, copy one of these URLs:

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

and check the option: "**Load balancing**", by default this option is checked.

- Boot DNS servers, we put the DNS of our choice:

Cloudflared in both IPv4 and IPv6:
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

- DNS server configuration, check the option "**Enable DNSSEC**".

## Add domain for DoH and DoT:

### Create the certificate with Let's Encrypt
<details>
    <summary>Create the self-signed personal certificate with Let's Encrypt:</summary>

#### Create the self-signed personal certificate with Let's Encrypt:
Installing a free SSL certificate with CertBot:
1. We update the list of packages.
~~~shell
sudo apt update && sudo apt upgrade
~~~
2. Install the Certbot package
~~~shell
sudo apt install certbot
~~~
3. Run the following command modifying the valid email to acquire a Wildcard certificate:
~~~shell
certbot certonly --manual --preferred-challenges=dns --rsa-key-size 4096 --email usuario@ejemplo.com --agree-tos --server https://acme-v02.api.letsencrypt.org/directory -d "*.your_domain"
~~~
4. Finally, it will ask to make an <code>_acme-challenge</code> TXT record in our name server provider with the content it tells us:
It creates the following files, in the directory <code>/etc/letsencrypt/live/</code>:
- <code>fullchain.pem</code> – your SSL certificate encrypted in PEM.
- <code>privkey.pem</code> – your private key encrypted in PEM.

#### Configuración de Lets encrypt
Steps to follow after requesting the certificate:
* You will be prompted to enter the domain to be certified, enter it using <code>*.</code> plus the domain you wish to certify to obtain the Wildcard.
* Finally, it will ask you to register <code>_acme-challenge</code> TXT type in our name server provider with the content you indicate.

To check if the certificate will self-renew:
* Renewal test (simulación):<code>certbot renew --dry-run</code>
* Check the status of the Certbot timer service: <code>systemctl status certbot.timer</code>
* To renew a certificate: <code>certbot renew</code>
	* To force self-renewal: <code>--force-renewal</code>
* To list jobs: <code>systemctl list-timers --all</code> Debe aparecer el siguiente configurado para la renovación automática: <code>certbot.timer - certbot.service</code>
* Listing certificates: <code>certbot certificates</code>

To revoke a certificate:
* Delete a certificate completely: <code>certbot delete --cert-name example.com</code>
* From the account for which the certificate was issued: <code>certbot revoke --cert-path /etc/letsencrypt/archive/${YOUR_DOMAIN}/cert1.pem</code>
* Using the certificate's private key: <code>certbot revoke --cert-path /PATH/TO/cert.pem --key-path /PATH/TO/key.pem</code>

If you don't want to go through all these steps, you can obtain the certificate with [Zero SSL](https://zerossl.com/). but the wildcard certificate is via payment.
</details>

### Create the self-signed personal certificate with OPENSSL:
<details>
    <summary>Create the self-signed personal certificate:</summary>

#### Crear el certificado personal autofirmado:

Info: [INFO](https://www.busindre.com/comandos_openssl_utiles_para_certificados)
1. We update the list of packages.
~~~shell
sudo apt update && sudo apt upgrade
~~~
2. Install the openssl package
~~~shell
sudo apt install openssl
~~~
3. Create the directory where we want to store the certificates:
~~~shell
mkdir certs &&\
cd certs/
~~~
4. Create certificate with the following command, changing the certificate path or leave the name of the .key and dot crt to store it in the directory:

	4.1 Generate an RSA private key:
	~~~shell
	openssl genpkey -algorithm RSA -out privkey.key -pkeyopt rsa_keygen_bits:2048
	~~~
	4.2 Next, we will create a certificate request (CSR) which will contain the certificate information:
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
	4.3 We generate the self-signed certificate with the CSR data:
	~~~
	openssl req -new -key privkey.key -out chain.csr -sha512 -config csrconfig.cnf
	~~~
	4.4 Create self-signed certificate in PEM format:
	~~~
	openssl x509 -req -in chain.csr -signkey privkey.key -out fullchain.pem -sha512 -days 365 -extfile csrconfig.cnf -extensions v3_req
	~~~
	4.5 After creating the self-signed certificate, we can verify the content of the certificate if it has been created correctly:
	~~~shell
	openssl x509 -in fullchain.pem -text -noout
	~~~
</details>


## Configure certificate in AdGuard Home:
1. Open the AdGuard Home web interface and go to configuration.
2. Scroll down the menu to settings: <code>Encryption settings</code>.
3. Enable check<code>Enable encryption (HTTPS, DNS via HTTPS and DNS via TLS)</code>.
4. Enable <code>Redirect to HTTPS automatically</code>.
5. Enter your domain name in <code>Server name</code>. If you are entering a wildcard, enter the domain name only<code>"example.com"</code>.
6. Copy/paste the contents of the file `fullchain.pem` in <code>Certificados</code>.
7. Copy / paste the contents of the file `privkey.pem` in <code>Private key</code>.
8. Click <code>Save configuration</code>.

## Configure the domain to allow private DNS DoH and DoT clients:
To create a zone in your domain to enable clients, follow these steps:

1. Mainly in the encryption Adguard section, you must enable the domain <code>example.org</code>.
2. You have the wildcard <code>*.example.org</code> certificate created.

#### Instructions for use:

1. Log into the control panel of your web hosting provider or domain registrar where you purchased the domain name.
2. Find the `DNS Zones` option.
3. Create a new `DNS Zones` entry. To add the entry for each client, e.g. `one.example.org`.
This will allow the client created in the `Client Configuration` panel to connect.
4. Configure `Settings/Client Configuration/Persistent clients`. Click `Add Clients` and under `Identifier` create a name.

<sup>Current instructions in the developer's documentation <a href="https://github.com/AdguardTeam/AdGuardHome/wiki/Clients#clientid">documentación</a>.</sup>


## Change password in Adguard
In order to change the password in Adguard we can access these websites and create a username and password:

- [![web2generators](https://img.shields.io/badge/-web2generators-c4302b?style=flat&labelColor=c4302b)](https://www.web2generators.com/apache-tools/htpasswd-generator)
- [![ipvoid](https://img.shields.io/badge/-ipvoid-c4302b?style=flat&labelColor=c4302b)](https://www.ipvoid.com/htpasswd-generator/)
- [![wtools](https://img.shields.io/badge/-wtools-c4302b?style=flat&labelColor=c4302b)](https://wtools.io/generate-htpasswd-online)

<p>We create the user and password. Once created, it has this format:</p>
<p><code>user:$apr1$x4gcjzrl$qSvcJK46C2rQUGRl4z1kl0</code></p>

<p>Once the user and password have been created, we proceed to access the adguard configuration file, <code>AdGuardHome.yaml</code>.</p>
<p>We look for the following line in the configuration file and replace the created data.</p>
<ul>
<li>For the <code>user</code>: user</li>
<li>For the <code>password</code>: $qSvcJK46C2rQUGRl4z1kl0</li>
</ul>
<pre><code class="lang-yaml">users:
  - name: <span class="hljs-literal">user</span>
    password: <span class="hljs-variable">$apr1</span><span class="hljs-variable">$x4gcjzrl</span><span class="hljs-variable">$qSvcJK46C2rQUGRl4z1kl0</span>
</code></pre>

Once the data has been changed, restart adguard.

# List for Pihole <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/pihole.png" alt="Pi-Hole" width="40"/> and AdGuard Home <img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/AdGuard_Logo.png" alt="AdGuard Home" width="32"/>

## Main safelist

| List | Link | Description |
| :-- | :--: | :-- |
| safelist repository | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/Listas/whitelist.txt) | safelist JuanRodenas |
| safelist hagezi | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/hagezi/dns-blocklists/main/whitelist.txt) | safelist hagezi (Not tested) |


## Main Black Lists
<sup>Column Link: Pi-hole® | Adguard Home®.</sup>

#### Host
| List Host | Link | Description |
| :-- | :--: | :-- |
| List oisd | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://dbl.oisd.nl) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://abp.oisd.nl) | To Block host Adguard and domains [dbl.oisd](https://oisd.nl/) |
| The big list | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://big.oisd.nl/domains) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://big.oisd.nl/) | The big list [oisd](https://oisd.nl/) |
| urlhaus-filter-domains | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://malware-filter.gitlab.io/malware-filter/urlhaus-filter-domains.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://malware-filter.gitlab.io/malware-filter/urlhaus-filter-agh.txt) | urlhaus-filter DEV [Link](https://gitlab.com/malware-filter/urlhaus-filter) |
| everything | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://blocklistproject.github.io/Lists/everything.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/everything-ags.txt) | To Block everything |
| energized pro | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://energized.pro/unified/formats/hosts.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://block.energized.pro/ultimate/formats/hosts.txt) | To Block [energized](https://energized.pro/) |
| d3ward | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/d3ward/toolz/master/src/d3host.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/d3ward/toolz/master/src/d3host.adblock) | [d3ward](https://github.com/d3ward) popular list |


#### Malware / Shock / Porn / Adult 
| List | Link | Description |
| :-- | :--: | :-- |
| The NSFW list | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://nsfw.oisd.nl/domains) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://nsfw.oisd.nl/) | The NSFW list [oisd](https://oisd.nl/) |
| Gambling-porn | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/Gambling.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://github.com/blocklistproject/Lists/blob/master/adguard/gambling-ags.txt) | To Block Gambling and porn |
| Malware | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://blocklistproject.github.io/Lists/malware.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/malware-ags.txt) | To Block malware |
| Ransomware | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/blocklistproject/Lists/master/ransomware.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/ransomware-ags.txt) | To Block ransomware |
| phishing | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://phishing.army/download/phishing_army_blocklist_extended.txt) | To Block phishing |


#### Tracking/Ads
| List Tracking/Ads | Link | Description |
| :-- | :--: | :-- |
| SmartTV | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/Perflyst/PiHoleBlocklist/master/SmartTV.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/smart-tv-ags.txt) | To Block SmartTV |
| WindowsSpyBlocker | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/crazy-max/WindowsSpyBlocker/master/data/hosts/spy.txt) | To Block WindowsSpyBlocker |
| GoodbyeAds-Ultra | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Hosts/GoodbyeAds-Ultra.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/hagezi/dns-blocklists/main/adblock/pro.plus.txt) | To Block [hagezi](https://github.com/hagezi/dns-blocklists) and [jerryn70](https://github.com/jerryn70/GoodbyeAds) |
| ads-and-tracking-extended | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://www.github.developerdan.com/hosts/lists/ads-and-tracking-extended.txt) | To Block ads-and-tracking-extended |
| Adblock_Plus | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/notracking/hosts-blocklists/master/adblock/adblock.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/Adblock_Plus_Ads.txt) | To Block Tracking AdBlock |
| Android tracking | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://github.com/JuanRodenas/Pihole_list/blob/main/Listas/android-tracking.txt) | Android tracking for AdGuard Home |

#### Adguard team filters
| List Tracking/Ads | Link | Description |
| :-- | :--: | :-- |
| AdGuardSDNSFilter | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://adguardteam.github.io/AdGuardSDNSFilter/Filters/filter.txt) | AdGuard team DNS filter |
| AdAway | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://adaway.org/hosts.txt) | AdAway default blocklist |
| Game Console Adblock List | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/DandelionSprout/adfilt/master/GameConsoleAdblockList.txt) | Game Console Adblock List |
| SmartTV-AGH | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/Perflyst/PiHoleBlocklist/master/SmartTV-AGH.txt) | Smart-TV Blocklist for AdGuard Home |
| Peter Lowe's List | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://pgl.yoyo.org/adservers/serverlist.php?hostformat=adblockplus&showintro=1&mimetype=plaintext) | Blocklist for use with Adblock Plus |

#### Services
| List Services | Link | Description |
| :-- | :--: | :-- |
| Youtube | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/blocklistproject/Lists/master/youtube.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/youtube-ags.txt) | To Block youtube |
| Facebook | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://github.com/jmdugan/blocklists/blob/master/corporations/facebook/all) | To Block Facebook/Instagram/Whatsapp |
| Whatsapp open | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/facebook/all-but-whatsapp) | To Block Facebook/Instagram but leave Whatsapp open |
| Google | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/google/all) | To Block Google |
| Mozilla | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/mozilla.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/mozilla_adguard.txt) | To Block Mozilla tracking |
| Microsoft | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/microsoft/all) | To Block Microsoft |
| VideoGamesAdiction | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/VideoGamesAdiction.txt) | To Block VideoGames Adiction |


#### uBlock Origin uAssets
| List Services | Link | Link dev | Description |
| :-- | :--: | :--: | :-- |
| uBlock filters | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/filters.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters |
| Badware risks | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/badware.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Badware risks |
| Privacy | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/privacy.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Privacy |
| Quick fixes list | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/quick-fixes.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | Quick fixes list |
| Resource abuse | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/resource-abuse.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Resource abuse |
| Unbreak | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/unbreak.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Unbreak |
| i-dont-care-about-cookies | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/unbreak.txt) | [Link DEV](https://www.i-dont-care-about-cookies.eu/) | i-dont-care-about-cookies |
| urlhaus-filter | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://malware-filter.gitlab.io/malware-filter/urlhaus-filter.txt) | [Link DEV](https://gitlab.com/malware-filter/urlhaus-filter) | urlhaus-filter |

<sup>A tab has been added for AdGuard with lists adapted to its format.</sup>


### Check your SelfHosted:

<details>
<summary>fivefilters:</summary>

<Original>&nbsp;Page to check your selfhosted from fivefilters</Original>

<p>  &nbsp;&nbsp;<a href="https://blockads.fivefilters.org/"><img src="https://img.shields.io/badge/fivefilters-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>d3ward:</summary>

<Original>&nbsp;Page to check your selfhosted from [d3ward](https://d3ward.github.io/toolz/)</Original>

<p>  &nbsp;&nbsp;<a href="https://d3ward.github.io/toolz/adblock.html"><img src="https://img.shields.io/badge/d3ward-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>canyoublockit:</summary>

<Original>&nbsp;Page to check your selfhosted from canyoublockit</Original>

<p>  &nbsp;&nbsp;<a href="https://canyoublockit.com/"><img src="https://img.shields.io/badge/CanYouBlockit-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>No more ads:</summary>

<Original>&nbsp;Page to check your selfhosted from No more ads</Original>

<p>  &nbsp;&nbsp;<a href="https://ads-blocker.com/es/pruebas/"><img src="https://img.shields.io/badge/Nomoreads-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;


<details>
<summary>AdBlock Tester:</summary>

<Original>&nbsp;Page to check your selfhosted from AdBlock Tester</Original>

<p>  &nbsp;&nbsp;<a href="https://adblock-tester.com/"><img src="https://img.shields.io/badge/AdBlocktester-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

### Check DoH, DoT and DDNSSEC:

<details>
<summary>1.1.1.1 de Cloudflare:</summary>

<Original>&nbsp;Page to check encryption of 1.1.1.1 de Cloudflare</Original>

<p>  &nbsp;&nbsp;<a href="https://1.1.1.1/help"><img src="https://img.shields.io/badge/Cloudflare-1.1.1.1-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>Tenta VPN Browser:</summary>

<Original>&nbsp;Page to check encryption of Tenta VPN Browser</Original>

<p>  &nbsp;&nbsp;<a href="https://tenta.com/test/"><img src="https://img.shields.io/badge/Tenta-Browser-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>Cloudflare:</summary>

<Original>&nbsp;Page to check encryption of Cloudflare</Original>

<p>  &nbsp;&nbsp;<a href="https://www.cloudflare.com/es-es/ssl/encrypted-sni/"><img src="https://img.shields.io/badge/cloudflare-encryptedsni-2aa8ff.svg?style=flat" alt="Link"></a></p>

#### The technologies analysed are:
1. Secure DNS: a technology that encrypts DNS queries and includes DNS-over-TLS and DNS-over-HTTPS.
2. DNSSEC: a technology designed to verify the authenticity of DNS queries.
3. TLS 1.3: the latest version of the TLS protocol that includes many improvements and closes security holes from previous versions.
4. Encrypted SNI: stands for Server Name Indication encryption that reveals the hostname during a TLS connection. This technology aims to ensure that only the IP address can be leaked.
<p><sup>The only browser that supports all four technologies is Firefox.</sup></p>

#### To activate the technologies, go to `about:config` and activate:
<p>  &nbsp;&nbsp;<code>network.security.esni.enabled</code> - pulsamos en el <code>+</code> y se ponga en <code>true</code>.</p>
<p>  &nbsp;&nbsp;<code>network.trr.mode</code> – (valor 2)</p>
<p>  &nbsp;&nbsp;<code>network.trr.uri</code> – <a href="https://mozilla.cloudflare-dns.com/dns-query">valor en la web Mozilla.</a></p>
<p>  &nbsp;&nbsp;<code>HTTPS-Only Mode</code> - pulsamos en el <code>+</code> y se ponga en <code>true</code>.</p>
</details>
&nbsp;

<details>
<summary>DNSSEC Resolver Test:</summary>

<Original>&nbsp;Page to check DNSSEC</Original>

<p>  &nbsp;&nbsp;<a href="http://dnssec.vs.uni-due.de/"><img src="https://img.shields.io/badge/dnssec-unidue-2aa8ff.svg?style=flat" alt="Link"></a></p>
<p>  &nbsp;&nbsp;<a href="http://www.dnssec-or-not.com/"><img src="https://img.shields.io/badge/dnssec-ornot-2aa8ff.svg?style=flat" alt="Link"></a></p>
<p>  &nbsp;&nbsp;<a href="http://en.conn.internet.nl/connection/"><img src="https://img.shields.io/badge/connection-internet-2aa8ff.svg?style=flat" alt="Link"></a></p>
<p>  &nbsp;&nbsp;<a href="https://wander.science/projects/dns/dnssec-resolver-test/"><img src="https://img.shields.io/badge/wander-project-2aa8ff.svg?style=flat" alt="Link"></a></p>

<Original>&nbsp;Page to check DNSSEC encryption</Original>
<p>  &nbsp;&nbsp;<a href="https://rootcanary.org/test.html"><img src="https://img.shields.io/badge/rootcanary-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>DNS leak test:</summary>

<Original>&nbsp;Page to check DNS leakage</Original>

<p>  &nbsp;&nbsp;<a href="https://www.dnsleaktest.com/"><img src="https://img.shields.io/badge/DNSleak-test-2aa8ff.svg?style=flat" alt="Link"></a></p>

</details>
&nbsp;

## android applications for Pi-hole® or Adguard Home®.
Link to the developer of the application:
[![GitHub](https://img.shields.io/badge/-JGeek00-171515?style=flat&logo=Github&logoColor=black&labelColor=ffffff&color=ffffff)](https://github.com/JGeek00/)

### Pi-hole® android application
<a href="https://play.google.com/store/apps/details?id=com.jgeek00.droid_hole" target="_blank" rel="noopener noreferrer"><img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/google-play.png" width="40px"></a>
### Adguard Home® android application
<a href="https://play.google.com/store/apps/details?id=com.jgeek00.adguard_home_manager" target="_blank" rel="noopener noreferrer"><img src="https://github.com/JuanRodenas/Pihole_list/blob/main/assets/google-play.png" width="40px"></a>

<p><sub>Any and all rights and responsibilities pertaining thereto remain the property of the respective developer.</sub></p>

## HELP ME AND CONTRIBUTION 🙌
<p> &nbsp;If you want to contribute to improve the lists, open a <code>issue</code> here:</p>
<a href="https://github.com/JuanRodenas/Pi-hole_list/issues"><img src="https://img.shields.io/badge/issues-green.svg?style=flat" alt="Link"></a>

## Credits 🚀
This repository is made with all my love and affection.

[![GitHub](https://img.shields.io/badge/-JuanRodenas-171515?style=flat&logo=Github&logoColor=black&labelColor=ececec&color=ececec)](https://github.com/JuanRodenas/)

# 🎉 ¡Ready!
&nbsp;

<p><sup>These files/texts are provided "AS IS", without warranties of any kind, express or implied, including, but not limited to, warranties of merchantability, fitness for a particular purpose and non-infringement. In no event shall the authors or copyright holders be liable for any claims, damages or other liability arising out of or relating to the files or the use thereof.</sup></p>
<p><sub>Any and all trademarks are the property of their respective owners.</sub></p>
<p><sup>I will be updating with information and adding procedures in my spare time. This repository is licensed under the Creative Commons Attribution - Non-Commercial - No Derivative Works (by-nc-nd) license.</sup></p>
