## Obtain a copy of openssl
You need to create a local copy of the file we are going to use to manage our CSR.
```bash
wget -O - https://raw.githubusercontent.com/openssl/openssl/master/apps/openssl.cnf > openssl.cnf
```
You can also download the `openssl.cnf` file into the directory of your choice: [![openssl.cnf](https://img.shields.io/badge/-openssl.cnf-3849b8?style=flat&labelColor=3849b8)](https://raw.githubusercontent.com/openssl/openssl/master/apps/openssl.cnf)

## Create a key to sign the CSR
It uses key-based authentication and since I am not using the LE client 
client I need to generate my own key. I am using OpenSSL for 
to generate a new 4096 bit RSA key.

```bash
openssl genrsa 4096 -out private.key 
```

It's also a good idea to make a backup copy of this key in a safe place.

## Create a custom OpenSSL conf
When generating the Certificate Signing Request (CSR) for use with LE, download a customized copy of the OpenSSL conf to use for CSR generation to maintain order and make it easier to generate new CSRs in the future. Take a copy of your OpenSSL configuration file.
* Edit your new copy of the file with the following, use nano, vim, vi.... whichever you wish:
````bash
nano openssl.cnf
```

In the file you have to look for the [ req ] section and then find and uncomment the following line. If the line does not exist you can simply add it. This ensures that the next config section we make is included.
````bash
req_extensions = v3_req
```

Once you have done this you have to go to the [ v3_req ] section and add the following line. This indicates that we want to fill the SAN field with the array we are going to create.
```
subjectAltName = @alt_names
```
Finally, you need to create the array of names you want in the SAN. Remember, this includes all domains! You will see that I have example.org and www.example.org. Don't forget to do something similar if necessary. Since all the "example.org" domains are hosted on this server, I'm going to add them all to the SAN so I can manage everything with one certificate from now on, and one renewal. 
Create this new section at the bottom of the configuration file and fill it in according to your needs.
```bash
[ alt_names ]

DNS.1 = www.example.org 
DNS.2 = example.org
DNS.3 = strongssl.example.org
DNS.4 = weakssl.example.org
```

## Generate the new CSR
Now we're all set to generate the CSR that we will use to get LE to sign our new certificates each renewal.
```bash
openssl req -new -key /path/to/your/private.key -out example.csr -config openssl.cnf
```

You don't need to enter a password so just hit enter to pass through the prompts.
```bash
Please enter the following 'extra' attributes to be sent with your certificate request
A challenge password []:
An optional company name []:
```

You can check the CSR with the following command:
```
openssl req -in example.csr -noout -text
```

In the output look for the following sections and check they are correct:
```
X509v3 Subject Alternative Name:
DNS:www.example.org, DNS:example.org, ...etc
```