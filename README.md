<h1 align="center"> The project that protects your devices </h1>

The <strong>SacureDNS</strong> project is an initiative that aims to lock down and secure the entire network through its own hardware. In this repository, it is installed via Docker®. Pi-hole® and Adguard Home® are DNS sinkholes that protect your devices from unwanted content without the need to install any software on client devices.

<div align="center">
    <a href="https://github.com/juanico10/Pihole_list">
        <img src="https://github.com/juanico10/Pihole_list/blob/main/assets/pihole.png" alt="Pi-hole" width="280">
        <img src="https://cdn.adtidy.org/website/github.com/AdguardFilters/viking.svg" alt="AdGuard Home" width="420">
    </a>
    <br>
    <h3>Network-wide ad blocking via its own hardware.</h3>
</div>

&nbsp;

![GitHub last commit (by committer)](https://img.shields.io/github/last-commit/juanico10/SacureDNS?style=flat&logo=Github&logoColor=white&label=last-commit&labelColor=253B80&color=253B80)
<a href="https://github.com/juanico10/SacureDNS/commits/master" >
    <img src="https://img.shields.io/github/commit-activity/m/juanico10/SacureDNS?style=flat&logo=Github&logoColor=white&label=Commit%20Activity&labelColor=253B80&color=253B80" alt="commit activity" >
  <a/>

## Links to installation or developer
| PROJECT | INSTALLER LINK | DEVELOPER LINK |
| :-- | :--: | :--: |
| <img src="https://github.com/juanico10/Pihole_list/blob/main/assets/AdGuard_Logo.png" alt="AdGuard Home" width="26"/> Adguard Home® | [INSTALLATION](https://github.com/juanico10/AdGuardHome) | [DEVELOPER](https://adguard.com/es/adguard-home/overview.html) |
| <img src="https://github.com/juanico10/Pihole_list/blob/main/assets/pihole.png" alt="Pi-Hole" width="30"/> Pi-hole® | [INSTALLATION](https://github.com/juanico10/Pihole) | [DEVELOPER](https://pi-hole.net/) |
### Version docker latest Pi-hole®
![Docker Image Version (tag latest)](https://img.shields.io/docker/v/pihole/pihole/latest?style=flat&logo=docker&logoColor=white&labelColor=0088cc&color=0088cc)

### Version docker latest Adguard Home®
![Docker Image Version (tag latest)](https://img.shields.io/docker/v/adguard/adguardhome/latest?style=flat&logo=docker&logoColor=white&labelColor=0088cc&color=0088cc)

> :warning: *This README has been translated into Spanish <img src="https://hatscripts.github.io/circle-flags/flags/es.svg" width="20">. \
>  Este README ha sido traducido a español <img src="https://hatscripts.github.io/circle-flags/flags/es.svg" width="20">.* :arrow_right: [**here**](./docs/README-ES.md).

## Details
These lists were created because I wanted something with a bit more control over what gets blocked. A lot of lists are all-or-nothing. We set out to create lists with more control over what gets blocked, which is why I recommend my lists to you, as they are tested and we block only what is unnecessary.

### Versions:

<details>
<summary>Original version:</summary>

<Original>&nbsp;All urls in this version **are** preceded by an IP address in the txt or host file:</Original>

<p>&nbsp;&nbsp;<code>0.0.0.0 example.com</code> – It will forward the domain example.com to the address 0.0.0.0 (but not for its subdomains).</p>
<p>&nbsp;&nbsp;<code>127.0.0.1 example.com</code> – will return the address 127.0.0.1 for the domain example.com (but not for its subdomains).</p>

</details>
&nbsp;
<details>
<summary>Version without IP on the left:</summary>

<Original>&nbsp;All urls in this version **no** are preceded by an IP address in the txt or host file:</Original>

<p>&nbsp;&nbsp;<code>example.com</code></p>

<sup>Our users have reported to us that some devices give an error if the url is preceded by an IP address.</sup>
</details>
&nbsp;
<details>
<summary>Adguard version:</summary>

<p>&nbsp;All urls from this version of the **AdGuard** list appear in the hosts file as follows:</p>

<p>&nbsp;&nbsp;<code>||example.org^</code> – blocks access to the domain <code>example.org</code> and all its subdomains</p>
<p>&nbsp;&nbsp;<code>@@||example.org^</code> – unlocks access to the <code>example.org</code> domain and all its subdomains.</p>
<p>&nbsp;&nbsp;<code>/REGEX/</code> – blocks access to domains matching the specified regular expression. For example, the rule <code>/example.*/</code> will block hosts matching the <code>example.*</code></p>
<p>&nbsp;&nbsp;<code>$</code> – This is the delimiter, which indicates that the rest of the rule is a modifier. Modifiers must be placed at the end of the rule after the character and separated by commas. For example, the modifiers must be placed at the end of the rule after the character and separated by commas. <code>||example.org^$important</code>.</p>
<p>&nbsp;&nbsp;<code>$important</code> – The modifier applied to a rule increases its priority over any other rule without the modifier. Even above the basic exception rules.</p>
<p>&nbsp;&nbsp;<code>*</code> – the wildcard character. It is used to represent any set of characters. It can also be an empty string or a string of any length.</p>
<p>&nbsp;&nbsp;<code>^</code> – the separator character. Unlike browser ad blocking, there is nothing to separate in a hostname, so the only purpose of this character is to mark the end of the hostname.</p>
<p>&nbsp;&nbsp;<code>|</code> – a pointer to the beginning or end of the host name. The value depends on the location of the character in the mask. For example, the rule <code>ample.org|</code> corresponds to <code>example.org</code>, but not to <code>example.org.com</code>. <code>|example</code> corresponds to <code>example.org</code> but not to <code>test.example.org</code></p>

<sup>The instructions are current as of [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome/wiki/Hosts-Blocklists#special-characters) v0.107.2. AdGuard supports older versions.</sup>
<sup>The instructions it supports [AdGuard Home](https://kb.adguard.com/en/general/how-to-create-your-own-ad-filters).</sup>
</details>
&nbsp;
<details>
<summary>Comments on the lists:</summary>

<p>&nbsp;All urls for this version of the list appear in the hosts file in the following way</p>

<p>&nbsp;&nbsp;<code># comment</code> – just a comment</p>
<p>&nbsp;&nbsp;<code>! comment</code> – just a comment</p>

</details>
&nbsp;

### Use:
<details>
    <summary>Use with Pi-Hole <img src="https://github.com/juanico10/Pihole_list/blob/main/assets/pihole.png" alt="Pi-Hole" width="30"/>:</summary>

## Instructions for use with Pi-Hole:

1. Copy the link to the Pi-hole format of the desired list (from the corresponding table below).
2. Add the URL to your Pi-hole block lists (**Login** > **Groups management** > **Lists** > **Paste the URL of the list in the "Address" field, add a comment** > **Click "Add "**).
3. Update Gravity (**Tools** > **Update Gravity** > **Click on "Update "** )

&nbsp;
<sup>Current instructions as of Pi-hole 5.2.4. Instructions may be slightly different at present. Instructions will be updated when version 6 is released.</sup>
</details>
&nbsp;

<details>
    <summary>Use with AdGuard Home <img src="https://github.com/juanico10/Pihole_list/blob/main/assets/AdGuard_Logo.png" alt="AdGuard Home" width="22"/>:</summary>

## Instructions for use with AdGuard Home:

1. copy the link to the AdGuard format corresponding to the desired list (from the corresponding table below).
2. Add the URL to your AdGuard block list (**Login** > **Filters** > **DNS block lists** > **Add block list** > **Add a custom list** > **Enter name** > **Paste the URL of the copied link**).
3. The list is automatically activated and is ready to start blocking.

&nbsp;
<sup>Instructions are current as of AdGuard Home v0.107.54</sup>
</details>
&nbsp;

# Adguard Home®  <img src="https://github.com/juanico10/Pihole_list/blob/main/assets/adguard_home_lightmode.svg" alt="AdGuard Home" width="100"/>

## General configuration
- One of the recommendations, in AdGuard settings, General configuration, Filter update interval in 1 hour. It will update the rules every hour.

### Change password in Adguard
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

## DNS Cache Configuration
After two years of use, I have collected the data from the Adguard cache with very optimal values. I recommend these usage values:

- We recommend that the **cache size** be greater than 64 megabytes. If you leave it at 0, you disable it.
- I recommend a **minimum TTL** value of **600**
- I recommend a **maximum TTL** value of **21600**

And I recommend **enabling optimistic caching**, which allows serving old cached responses while they are updated in the background.

## Add domain for DoH and DoT:

### Create the certificate with Let's Encrypt
<details>
    <summary>Create the self-signed personal certificate with Let's Encrypt:</summary>

#### Create the self-signed personal certificate with Let's Encrypt:
Installing a free SSL certificate with CertBot:

:one: We update the list of packages.
```shell
sudo apt update && sudo apt upgrade
```

:two: Install the Certbot package
```shell
sudo apt install certbot
```
<p>Cerbot Documentation: <a href="https://eff-certbot.readthedocs.io/en/latest/"><img src="https://img.shields.io/badge/-Certbot-3849b8?style=flat&labelColor=3849b8" alt="Certbot"></a></p>

:three: In this section we are going to see the most important options of the command. You can choose the options that you consider most convenient.

Certbot supports a lot of command line options. Here’s the full list, from `certbot --help all`:

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

 :point_right: 3.3. `--csr` The csr variable and a `.cnf` file can perform the following functions. Currently --csr only works with the `certonly` subcommand.
  - Follow this tutorial that I have added separately to create the csr [![Link](https://img.shields.io/badge/Create_CSR-green.svg?style=flat)](./docs/create-csr.md)

 :point_right: 3.4. `--config-dir` You can configure the configuration file with the variable.
  - The certificate specific configuration options must be set in the `.conf` and I attach an example: [![example.org.conf](https://img.shields.io/badge/example.org.conf-3849b8?style=flat&labelColor=3849b8)](./docs/example.org.conf)

 :point_right: 3.5. `--test-cert, --staging` Use the Let's Encrypt staging server to obtain or revoke test (invalid) certificates; equivalent to `--server acme-staging`

 :point_right: 3.6. `--hsts` Add the Strict-Transport-Security header to every HTTP response. Force the browser to always use SSL for the domain.

 :point_right: 3.7. `--key-type {rsa,ecdsa}`. Type of generated private key. Only *ONE* per invocation can be provided at this time.

 :point_right: 3.8. `--quiet` Silence all output except errors.

 :point_right: 3.9. `--cert-name` Certificate name to apply. This name is used by Certbot for housekeeping and in file paths; it doesn't affect the content of the certificate itself.

 :point_right: 3.10 `--debug` Show tracebacks in case of errors

 :point_right: 3.11 `--dry-run` Perform a test run against the Let's Encrypt staging server, obtaining test (invalid) certificates but not saving them to disk.

 :point_right: 3.12 `--dns-cloudflare` Obtain certificates using a DNS TXT record (if you are using Cloudflare for DNS).

 :point_right: 3.13. `--server` Choose the ACME Directory Resource URI for your server.
  | Description | Server |
  | :--: | :-- |
  | Certificate for production server | https://acme-v02.api.letsencrypt.org/directory |
  | Certificate for test server | https://acme-staging-v02.api.letsencrypt.org/directory |

 :point_right: 3.14. `--elliptic-curve` (default: secp256r1) The SECG elliptic curve name to use.
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

 For the choice of the key to be chosen the difference in the definition of the base point has two important consequences:
  * **The secpXXXk1 curve has a higher computational efficiency than the secpXXXr1 curve.** This is because the base point of the secpXXXk1 curve is a generation point, which means that it can be used to generate all the other points of the curve. The base point of the secpXXXr1 curve, on the other hand, is not a generation point, so more operations need to be calculated to generate all the other points of the curve.
  * **The secpXXXr1 curve has higher security than the secpXXXk1 curve.** This is because the base point of the secpXXXr1 curve is a more random point than the base point of the secpXXXk1 curve. This makes it more difficult for attackers to find points on the curve that are not in the set of generation points.
 In general, the secpXXXXk1 curve is a good choice for applications that require computational efficiency, while the secpXXXr1 curve is a good choice for applications that require security.

 Examples of applications that could use each curve:
  | Feature | secpXXXk1 | secpXXXr1 |
  |---|---|---|
  | base point | Lower | Higher |
  | Type | Computational | Security |
  | Computational Efficiency | Higher | Basic |
  | Security | Basic | Higher |
  | Common uses | Digital signature, Cryptocurrencies, public keys encryption | Public key encryption for critical applications, encryption, Public Key Infrastructure (PKI) |

Run the following command modifying the valid email and options as you see fit for your example.

This example is for acquiring a Wildcard certificate:
```shell
certbot certonly --manual --preferred-challenges=dns --rsa-key-size 4096 --email usuario@ejemplo.com --agree-tos
--server https://acme-v02.api.letsencrypt.org/directory -d "*.your_domain"
```

:four: Finally, it will ask to make an <code>_acme-challenge</code> TXT record in our name server provider with the content it tells us:
With cerbot, when using the dns challenge, certbot will ask you to place a` TXT DNS` record with specific contents under the domain name consisting of the hostname for which you want a certificate issued, prepended `_acme-challenge`.
For example, for the domain `example.com`, a zone file entry would look like:
```shell
_acme-challenge.example.com. 300 IN TXT "gfj9Xq...Rg85nM"
```

It creates the following files, in the directory <code>/etc/letsencrypt/live/</code>:
 - <code>fullchain.pem</code> – your SSL certificate encrypted in PEM.
 - <code>privkey.pem</code> – your private key encrypted in PEM.

#### Configuración de Lets encrypt
To check if the certificate will self-renew:
* Renewal test (simulación):<code>certbot renew --dry-run</code>
* Check the status of the Certbot timer service: <code>systemctl status certbot.timer</code>
* To renew a certificate: <code>certbot renew</code>
	* To force self-renewal: <code>--force-renewal</code>
* To list jobs: <code>systemctl list-timers --all</code> Debe aparecer el siguiente configurado para la renovación automática: <code>certbot.timer - certbot.service</code>
* Listing certificates: <code>certbot certificates</code>

To revoke a certificate:
* Delete a certificate completely: <code>certbot delete --cert-name example.com --reason keycompromise</code>
* From the account for which the certificate was issued: <code>certbot revoke --cert-path /etc/letsencrypt/archive/${YOUR_DOMAIN}/cert1.pem --reason keycompromise</code>
* Using the certificate's private key: <code>certbot revoke --cert-path /PATH/TO/cert.pem --key-path /PATH/TO/key.pem --reason keycompromise</code>

<p>If you do not want to follow all these steps, you can obtain the certificate with <code>ZeroSSL</code>, but the wildcard certificate is charged.</p>
<p><a href="https://zerossl.com/"><img src="https://img.shields.io/badge/-ZeroSSL-3849b8?style=flat&labelColor=3849b8" alt="ZeroSSL"></a></p>

</details>

### Create the self-signed personal certificate with OPENSSL:
<details>
    <summary>Create the self-signed personal certificate:</summary>

#### Create a self-signed personal certificate:
<p>Steps you can follow to create a self-signed RSA certificate using OpenSSL with SHA-512 and Subject Alternative Names (SAN).</p>
<p>To learn more about on useful openssl commands for certificates:</p>
<p><a href="https://www.busindre.com/comandos_openssl_utiles_para_certificados"><img src="https://img.shields.io/badge/-Link-df8a47?style=flat&labelColor=df8a47" alt="Link"></a></p>

1. We update the list of packages.
```shell
sudo apt update && sudo apt upgrade
```
2. Make sure you have OpenSSL installed on your system before proceeding. Install the openssl package:
```shell
sudo apt install openssl
```
3. Create the directory where we want to store the certificates:
```shell
mkdir certs &&\
cd certs/
```
4. Create certificate with the following command, changing the certificate path or leave the name of the .key and dot crt to store it in the directory:

	4.1 Generate an RSA private key:
	```shell
	openssl genpkey -algorithm RSA -out privkey.key -pkeyopt rsa_keygen_bits:2048
	```
	4.2 Next, we will create a certificate request (CSR) which will contain the certificate information:
	```shell
	vi csrconfig.cnf
	```
	```shell
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
	```
	4.3 We generate the self-signed certificate with the CSR data:
	```
	openssl req -new -key privkey.key -out chain.csr -sha512 -config csrconfig.cnf
	```
	4.4 Create self-signed certificate in PEM format:
	```
	openssl x509 -req -in chain.csr -signkey privkey.key -out fullchain.pem -sha512 -days 365 -extfile csrconfig.cnf -extensions v3_req
	```
	4.5 After creating the self-signed certificate, we can verify the content of the certificate if it has been created correctly:
	```shell
	openssl x509 -in fullchain.pem -text -noout
	```
</details>


### Configure certificate in AdGuard Home:
1. Open the AdGuard Home web interface and go to configuration.
2. Scroll down the menu to settings: <code>Encryption settings</code>.
3. Enable check<code>Enable encryption (HTTPS, DNS via HTTPS and DNS via TLS)</code>.
4. Enable <code>Redirect to HTTPS automatically</code>.
5. Enter your domain name in <code>Server name</code>. If you are entering a wildcard, enter the domain name only<code>"example.com"</code>.
6. Copy/paste the contents of the file `fullchain.pem` in <code>Certificados</code>.
7. Copy / paste the contents of the file `privkey.pem` in <code>Private key</code>.
8. Click <code>Save configuration</code>.

### Configure the domain to allow private DNS DoH and DoT clients:
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

# List for Pihole <img src="https://github.com/juanico10/Pihole_list/blob/main/assets/pihole.png" alt="Pi-Hole" width="40"/> and AdGuard Home <img src="https://github.com/juanico10/Pihole_list/blob/main/assets/AdGuard_Logo.png" alt="AdGuard Home" width="32"/>

## Main safelist

| List | Link | Description |
| :-- | :--: | :-- |
| safelist repository | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/juanico10/Pihole_list/main/Listas/whitelist.txt) | safelist juanico10 |
| safelist hagezi | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/hagezi/dns-blocklists/main/whitelist.txt) | safelist hagezi (Not tested) |


## Main BlockLists
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
| Gambling-porn | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/juanico10/Pihole_list/main/List/Gambling.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://github.com/blocklistproject/Lists/blob/master/adguard/gambling-ags.txt) | To Block Gambling and porn |
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
| Adblock_Plus | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/notracking/hosts-blocklists/master/adblock/adblock.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/juanico10/Pihole_list/main/List/Adblock_Plus_Ads.txt) | To Block Tracking AdBlock |
| Android tracking | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://github.com/juanico10/Pihole_list/blob/main/Listas/android-tracking.txt) | Android tracking for AdGuard Home |
| Disconnect.me | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://s3.amazonaws.com/lists.disconnect.me/simple_tracking.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://s3.amazonaws.com/lists.disconnect.me/simple_ad.txt) | To Block disconnect.me |

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
| Mozilla | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/juanico10/Pihole_list/main/List/mozilla.txt) &#124; [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/juanico10/Pihole_list/main/List/mozilla_adguard.txt) | To Block Mozilla tracking |
| Microsoft | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/microsoft/all) | To Block Microsoft |
| VideoGamesAdiction | [![Link](https://img.shields.io/badge/Link-green.svg?style=flat)](https://raw.githubusercontent.com/juanico10/Pihole_list/main/List/VideoGamesAdiction.txt) | To Block VideoGames Adiction |


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

<p>&nbsp;&nbsp;<a href="https://blockads.fivefilters.org/"><img src="https://img.shields.io/badge/fivefilters-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>d3ward:</summary>

<Original>&nbsp;Page to check your selfhosted from [d3ward](https://d3ward.github.io/toolz/)</Original>

<p>&nbsp;&nbsp;<a href="https://d3ward.github.io/toolz/adblock.html"><img src="https://img.shields.io/badge/d3ward-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>canyoublockit:</summary>

<Original>&nbsp;Page to check your selfhosted from canyoublockit</Original>

<p>&nbsp;&nbsp;<a href="https://canyoublockit.com/"><img src="https://img.shields.io/badge/CanYouBlockit-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>No more ads:</summary>

<Original>&nbsp;Page to check your selfhosted from No more ads</Original>

<p>&nbsp;&nbsp;<a href="https://ads-blocker.com/es/pruebas/"><img src="https://img.shields.io/badge/Nomoreads-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;


<details>
<summary>AdBlock Tester:</summary>

<Original>&nbsp;Page to check your selfhosted from AdBlock Tester</Original>

<p>&nbsp;&nbsp;<a href="https://adblock-tester.com/"><img src="https://img.shields.io/badge/AdBlocktester-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

### Check DoH, DoT and DDNSSEC:

<details>
<summary>1.1.1.1 de Cloudflare:</summary>

<Original>&nbsp;Page to check encryption of 1.1.1.1 de Cloudflare</Original>

<p>&nbsp;&nbsp;<a href="https://1.1.1.1/help"><img src="https://img.shields.io/badge/Cloudflare-1.1.1.1-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>Tenta VPN Browser:</summary>

<Original>&nbsp;Page to check encryption of Tenta VPN Browser</Original>

<p>&nbsp;&nbsp;<a href="https://tenta.com/test/"><img src="https://img.shields.io/badge/Tenta-Browser-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>Cloudflare:</summary>

<Original>&nbsp;Page to check encryption of Cloudflare</Original>

<p>&nbsp;&nbsp;<a href="https://www.cloudflare.com/es-es/ssl/encrypted-sni/"><img src="https://img.shields.io/badge/cloudflare-encryptedsni-2aa8ff.svg?style=flat" alt="Link"></a></p>

#### The technologies analysed are:
1. Secure DNS: a technology that encrypts DNS queries and includes DNS-over-TLS and DNS-over-HTTPS.
2. DNSSEC: a technology designed to verify the authenticity of DNS queries.
3. TLS 1.3: the latest version of the TLS protocol that includes many improvements and closes security holes from previous versions.
4. Encrypted SNI: stands for Server Name Indication encryption that reveals the hostname during a TLS connection. This technology aims to ensure that only the IP address can be leaked.
<p><sup>The only browser that supports all four technologies is Firefox.</sup></p>

#### To activate the technologies, go to `about:config` and activate:
<p>&nbsp;&nbsp;<code>network.security.esni.enabled</code> - pulsamos en el <code>+</code> y se ponga en <code>true</code>.</p>
<p>&nbsp;&nbsp;<code>network.trr.mode</code> – (valor 2)</p>
<p>&nbsp;&nbsp;<code>network.trr.uri</code> – <a href="https://mozilla.cloudflare-dns.com/dns-query">valor en la web Mozilla.</a></p>
<p>&nbsp;&nbsp;<code>HTTPS-Only Mode</code> - pulsamos en el <code>+</code> y se ponga en <code>true</code>.</p>
</details>
&nbsp;

<details>
<summary>DNSSEC Resolver Test:</summary>

<Original>&nbsp;Page to check DNSSEC</Original>

<p>&nbsp;&nbsp;<a href="http://dnssec.vs.uni-due.de/"><img src="https://img.shields.io/badge/dnssec-unidue-2aa8ff.svg?style=flat" alt="Link"></a></p>
<p>&nbsp;&nbsp;<a href="http://www.dnssec-or-not.com/"><img src="https://img.shields.io/badge/dnssec-ornot-2aa8ff.svg?style=flat" alt="Link"></a></p>
<p>&nbsp;&nbsp;<a href="http://en.conn.internet.nl/connection/"><img src="https://img.shields.io/badge/connection-internet-2aa8ff.svg?style=flat" alt="Link"></a></p>
<p>&nbsp;&nbsp;<a href="https://wander.science/projects/dns/dnssec-resolver-test/"><img src="https://img.shields.io/badge/wander-project-2aa8ff.svg?style=flat" alt="Link"></a></p>

<Original>&nbsp;Page to check DNSSEC encryption</Original>
<p>&nbsp;&nbsp;<a href="https://rootcanary.org/test.html"><img src="https://img.shields.io/badge/rootcanary-2aa8ff.svg?style=flat" alt="Link"></a></p>
</details>
&nbsp;

<details>
<summary>DNS leak test:</summary>

<Original>&nbsp;Page to check DNS leakage</Original>

<p>&nbsp;&nbsp;<a href="https://www.dnsleaktest.com/"><img src="https://img.shields.io/badge/DNSleak-test-2aa8ff.svg?style=flat" alt="Link"></a></p>

</details>
&nbsp;

## Applications for Pi-hole® or Adguard Home®.
Link to the developer of the application:
[![GitHub](https://img.shields.io/badge/-JGeek00-171515?style=flat&logo=Github&logoColor=black&labelColor=ffffff&color=ffffff)](https://github.com/JGeek00/)
#### Pi-hole® android application
<p><a><a href="https://play.google.com/store/apps/details?id=com.jgeek00.droid_hole" target="_blank" rel="noopener noreferrer"><img src="https://github.com/juanico10/Pihole_list/blob/main/assets/get_google_play.png" width="120px"></a></p>

#### Adguard Home® android application
<p><a><a href="https://play.google.com/store/apps/details?id=com.jgeek00.adguard_home_manager" target="_blank" rel="noopener noreferrer"><img src="https://github.com/juanico10/Pihole_list/blob/main/assets/get_google_play.png" width="120px"></a></p>

## Desktop applications for Adguard Home®.
Link to the developer of the application:
[![GitHub](https://img.shields.io/badge/-Juanico10-171515?style=flat&logo=Github&logoColor=black&labelColor=ffffff&color=ffffff)](https://github.com/juanico10/)
<p><a><a href="https://github.com/juanico10/adguard-home-manager-desktop" target="_blank" rel="noopener noreferrer"><img src="https://github.com/juanico10/Pihole_list/blob/main/assets/get-github.png" width="120px"></a></p>

<p><sub>Any and all rights and responsibilities pertaining thereto remain the property of the respective developer.</sub></p>

## Help me and contribution :raised_hands:
<p> &nbsp;If you want to contribute to improve the lists, open a <code>issue</code> here:</p>
<a href="https://github.com/juanico10/SacureDNS/issues"><img src="https://img.shields.io/badge/issues-green.svg?style=flat" alt="Link"></a>

## Credits :rocket:
This repository is made with all my love and affection.

[![GitHub](https://img.shields.io/badge/-Juanico10-171515?style=flat&logo=Github&logoColor=black&labelColor=ececec&color=ececec)](https://github.com/juanico10/)

## :tada: ¡Ready!

&nbsp;

<p align="center"><img src="https://raw.githubusercontent.com/catppuccin/catppuccin/main/assets/footers/gray0_ctp_on_line.svg?sanitize=true" /></p>

<p><sup>These files/texts are provided "AS IS", without warranties of any kind, express or implied, including, but not limited to, warranties of merchantability, fitness for a particular purpose and non-infringement. In no event shall the authors or copyright holders be liable for any claims, damages or other liability arising out of or relating to the files or the use thereof.</sup></p>
<p><sup>I will be updating with information and adding procedures in my spare time. The author of the content is juanico10. You can contact me at <a href="mailto:juanico1007@gmail.com?Subject=from%20github">mailto</a> and the author's website is <a href="https://github.com/juanico10/">website</a>.</p></sup>
<p><sub>Any and all trademarks are the property of their respective owners.</sub></p>
<p align="center"><a href="https://raw.githubusercontent.com/juanico10/Pihole_list/main/LICENSE"><img src="https://img.shields.io/static/v1.svg?style=for-the-badge&label=License&message=MIT&logoColor=d9e0ee&colorA=302d41&colorB=b7bdf8"/></a></p>
